---
title: 'Multilingual search in Hugo with Docsy — offline and ever so slightly sane'
subtitle: "Activists' humanitarian mission ends in detention, but not in spirit."
date: 2025-06-24T05:00:00.000Z
draft: false
tags: 
  - multilingual search
  - Hugo
  - Docsy
  - offline search
  - lunr.js
  - privacy
  - javascript
  - indexing
  - stemmer problems
  - static site search
  - tutorial
  - airgapped
---

This guide walks you through setting up multilingual search in Hugo (v0.147.3) using the Docsy theme, **without relying on any CDNs**. No dodgy remote JS includes, no API keys, no Algolia. Just good old-fashioned files, language-specific `index.json`, and some actual control over what your search does. This is based on a working implementation that uses Lunr.js and works entirely offline — useful for privacy-focused or air-gapped deployments. It also assumes you're not here for quick hacks but for a Hugo-friendly setup.

### Prerequisites

You're running Hugo 0.147.3 in production mode, with multilingual content properly structured (e.g. `content/en/`, `content/de/`, etc.), and you're using the Docsy theme — extended version preferred. You will also need to be using Hugo Pipes (which Docsy does), and you are comfortable customising `layouts/` and `assets/`.

---

## 1. JSON index creation per language

In the root of your `layouts/` directory, create a file called:

### `layouts/index.json.json`

```
{{- $index := slice -}}
{{- $lang := .Site.Language.Lang -}}
{{- range where .Site.RegularPages "Lang" .Site.Language.Lang -}}
  {{- $isSearch := or (eq .Type "search") (eq .Layout "search") -}}
  {{- if and (not .Params.excludeFromSearch) (not $isSearch) -}}
    {{- $title := .Title | default "" -}}
    {{- $description := .Params.description | default "" -}}
    {{- $content := .Plain | default "" -}}

    {{- $index = $index | append (dict
      "title" $title
      "description" $description
      "content" $content
      "permalink" (.Permalink | default "")
      "original_title" (.Title | default "")
    ) -}}
  {{- end -}}
{{- end -}}
{{- $index | jsonify -}}
```

This generates a per-language JSON index file at `/[lang]/index.json`. Hugo will render this automatically when the user navigates to the language subdirectory, e.g., `/en/index.json`, `/de/index.json`, etc.

---

## 2. Search results page template

In your `layouts/` root, add:

### `layouts/search.html`

This renders the search results page. It includes the search input and a container where JavaScript will inject the results.

```
{{ define "main" }}
<section class="row td-search-result">
  <div class="col-12 col-md-8 offset-md-2">
    <h2 class="ms-4">{{ .Title }}</h2>
    <div id="search-results" class="col-12 mt-4">
      {{ if .Params.q }}
        <div class="px-3">{{ i18n "loading_results" }} "{{ .Params.q }}"...</div>
      {{ else }}
        <div class="px-3">{{ i18n "search_prompt" }}</div>
      {{ end }}
    </div>
  </div>
</section>
<script src="/js/search-i18n.js"></script>
<script src="/js/search-page.js"></script>
{{ end }}
```

Your multilingual search result pages will live at `/en/search/`, `/de/search/`, etc. Hence create a search.md in the 
root of each `[lang]` directory in `content` with only this frontend matter:

```
---
title: Arama Sonuçları
layout: search
type: search
excludeFromSearch: true
---
```

---

## 3. Required JavaScript files

All the JavaScript should be local. Place these in your `assets/js/` or `static/js/` folder as needed. Source: https://github.com/olivernn/lunr.js

### `static/js/lunr.js`

The core Lunr.js library (v2.x preferred). Download from the Lunr.js repo.

### `static/js/lunr.*.js`

Language-specific stemmers and tokenizers:

* `lunr.de.js` — German
* `lunr.es.js` — Spanish
* `lunr.fr.js` — French
* `lunr.nl.js` — Dutch
* `lunr.tr.js` — Turkish
* `lunr.stemmer.support.js` — Required by all language plugins

These are all available from the Lunr-languages project, available at: https://github.com/MihaiValentin/lunr-languages. Include only the ones you need, based on the languages in your site.

### `static/js/search-i18n.js`

Shared language utilities:

```js
// Shared language resources and utilities for search
window.searchI18n = {
  translations: {
    noResults: {
      en: 'No results for',
      es: 'No hay resultados para',
      fr: 'Aucun résultat pour',
      de: 'Keine Ergebnisse für',
      nl: 'Geen resultaten voor',
      tr: 'Sonuç bulunamadı'
    },
    untitled: {
      en: 'Untitled',
      es: 'Sin título',
      fr: 'Sans titre',
      de: 'Ohne Titel',
      nl: 'Zonder titel',
      tr: 'Başlıksız'
    },
    searchError: {
      en: 'Search currently unavailable',
      es: 'Búsqueda no disponible',
      fr: 'Recherche indisponible',
      de: 'Suche nicht verfügbar',
      nl: 'Zoeken is niet beschikbaar',
      tr: 'Arama şu anda kullanılamıyor'
    },
    minimumChars: {
      en: 'Enter at least 2 characters',
      es: 'Ingrese al menos 2 caracteres',
      fr: 'Entrez au moins 2 caractères',
      de: 'Mindestens 2 Zeichen eingeben',
      nl: 'Voer minimaal 2 tekens in',
      tr: 'En az 2 karakter girin'
    },
    searchPrompt: {
      en: 'Please use the search box in the navigation bar',
      es: 'Por favor use el cuadro de búsqueda en la barra de navegación',
      fr: 'Veuillez utiliser la barre de recherche dans la barre de navigation',
      de: 'Bitte verwenden Sie das Suchfeld in der Navigationsleiste',
      nl: 'Gebruik het zoekvak in de navigatiebalk',
      tr: 'Lütfen gezinme çubuğundaki arama kutusunu kullanın'
    },
    loading: {
      en: 'Loading results for',
      es: 'Cargando resultados para',
      fr: 'Chargement des résultats pour',
      de: 'Lade Ergebnisse für',
      nl: 'Resultaten laden voor',
      tr: 'Sonuçlar yükleniyor'
    }
  },

  // Get translation for current language
  t: function(key, lang) {
    return this.translations[key]?.[lang] || this.translations[key]?.en || '';
  },

  // Case normalization based on language
  normalizeTerm: function(term, lang) {
    // Special handling for case-sensitive languages
    if (['tr', 'nl'].includes(lang)) {
      return term.toLowerCase();
    }
    return term;
  },

  // Language detection
  detectLanguage: function() {
    const lang = window.location.pathname.split('/')[1];
    return ['en', 'es', 'fr', 'de', 'nl', 'tr'].includes(lang) ? lang : 'en';
  }
};
```

### `static/js/search-page.js`

This is the actual page script used to trigger search behaviour. It is loaded via your search page template. If you're only including one search script, this is the one to include.

```js
document.addEventListener('DOMContentLoaded', function() {
  // Only run on search page
  const resultsContainer = document.getElementById('search-results');
  if (!resultsContainer) return;

  // Get language and translations
  const lang = window.searchI18n.detectLanguage();
  const t = (key) => window.searchI18n.t(key, lang);

  // Get query from URL
  const urlParams = new URLSearchParams(window.location.search);
  const query = urlParams.get('q') || '';

  // Show appropriate initial message
  if (!query) {
    resultsContainer.innerHTML = `<div class="px-3">${t('searchPrompt')}</div>`;
    return;
  }

  // Show loading message
  if (query) {
    resultsContainer.innerHTML = `<div class="px-3">${t('loading')} "${query}"...</div>`;
  }

  // ===== NEW HELPER FUNCTIONS ===== //
  function highlightMatches(text, query) {
    if (!text || !query) return text || '';
    const terms = query.trim().split(/\s+/).filter(term => term.length > 2);
    if (!terms.length) return text;
    return terms.reduce((result, term) => {
      const regex = new RegExp(`(${escapeRegExp(term)})`, 'gi');
      return result.replace(regex, '<span class="search-highlight">$1</span>');
    }, text);
  }

  function getContentPreview(content, query) {
    if (!content) return '';
    const terms = query.trim().split(/\s+/).filter(term => term.length > 2);
    if (!terms.length) return content.substring(0, 150) + '...';

    // Find first matching term position
    const firstMatchPos = terms.reduce((pos, term) => {
      const termPos = content.toLowerCase().indexOf(term.toLowerCase());
      return termPos > -1 && (pos === -1 || termPos < pos) ? termPos : pos;
    }, -1);

    if (firstMatchPos > -1) {
      const start = Math.max(0, firstMatchPos - 300);
      const end = Math.min(content.length, firstMatchPos + terms[0].length + 300);
      let preview = content.slice(start, end);
      if (start > 0) preview = '...' + preview;
      if (end < content.length) preview += '...';
      return highlightMatches(preview, query);
    }
    return highlightMatches(content.substring(0, 150) + '...', query);
  }

  function escapeRegExp(string) {
    return string.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
  }

  // ===== UPDATED DISPLAY FUNCTION ===== //
  function displayResults(results, docs, query) {
    resultsContainer.innerHTML = '';

    if (!results.length) {
      resultsContainer.innerHTML = `
        <div class="search-no-results px-3 py-2">
          ${t('noResults')} "<span class="search-highlight">${query}</span>"
        </div>`;
      return;
    }

    results.forEach(result => {
      const doc = docs.find(d => d.permalink === result.ref);
      if (!doc) return;

      const item = document.createElement('div');
      item.className = 'search-result p-3 border-bottom';
      item.innerHTML = `
        <a href="${doc.permalink}" class="d-block h5 mb-1 text-primary">
          ${highlightMatches(doc.title || t('untitled'), query)}
        </a>
        ${doc.description ? `
          <p class="mb-1 text-muted">
            ${highlightMatches(doc.description, query)}
          </p>` : ''}
        <div class="search-content small">
          ${getContentPreview(doc.content, query)}
        </div>
      `;
      resultsContainer.appendChild(item);
    });
  }

  // Load index for current language
  fetch(`/${lang}/index.json`)
    .then(response => {
      if (!response.ok) throw new Error('Failed to load index');
      return response.json();
    })
    .then(data => {
      // Initialize search
      const idx = lunr(function() {
        this.ref('permalink');
        this.field('title', { boost: 10 });
        this.field('description', { boost: 5 });
        this.field('content');

        // Special pipeline for case-sensitive languages
        if (['tr', 'nl'].includes(lang)) {
          this.pipeline.remove(lunr.stemmer);
          this.pipeline.remove(lunr.stopWordFilter);
        }

        // Add documents
        const docs = Array.isArray(data) ? data : Object.values(data);
        docs.forEach(doc => {
          if (doc.permalink && !doc.permalink.includes('/search/')) {
            this.add(doc);
          }
        });
      });

      // Perform search if query exists
      if (query) {
        const normalizedQuery = window.searchI18n.normalizeTerm(query, lang);
        const results = idx.search(normalizedQuery);
        displayResults(results, data, query);
      }
    })
    .catch(err => {
      console.error('Search results failed:', err);
      resultsContainer.innerHTML = `
        <div class="px-3 py-2 text-danger">
          ${t('searchError')}
        </div>`;
    });
});
```

### `static/js/search.js`

Can be omitted if you're using `search-page.js`. If you include both, you may have conflicts. Prefer `search-page.js` unless you have a strong reason.

### `static/js/jquery-3.7.1.min.js`

Just in case you need it for compatibility, download from https://code.jquery.com/, but if you're writing plain JS as above, it may not be necessary. Still, Docsy uses it, so it’s often there. I chose to anyway, otherwise the CDN stays and is a security risk.

---

## 4. Hooking up the search box in your header

### `layouts/_partials/searchbox.html`

This is your top-bar search field.

```
<form action="/{{ .Site.Language.Lang }}/search/">
  <input id="search-input" name="q" class="form-control" type="search" placeholder="Search..." />
</form>
```

Make sure it points to the correct language path — that's crucial.

### `layouts/_partials/navbar.html`

At the end:

```
...
  </div>
  <div>
    {{ partial "searchbox.html" . }}
  </div>
</div>
</nav>
```

---

## 5. Stemming and tokenisation problems in Turkish and Dutch

Lunr.js doesn’t handle every language with equal elegance, and Turkish and Dutch are prime examples. Turkish is agglutinative and context-sensitive, making its tokenisation notoriously tricky. The default stemmer can lead to wildly inaccurate search matches or no matches at all. Dutch, for its part, suffers from compound words and over-aggressive stemming. Searching for "veilig" (safe) might unhelpfully also return pages about "veiligheidscamera" (security camera), even when the original word wasn’t mentioned.

If these languages are essential to your site, consider tweaking the tokenizer or disabling stemming entirely. You may get more predictable results using `this.pipeline.remove(lunr.stemmer)` after loading the language plugin. Or consider preprocessing the content to break down compound words. For now, accept that precision in these languages is an ongoing compromise — not your fault, just linguistics being awkward.

---

## Conclusion

Search in Hugo’s multilingual environment is fiddly, underdocumented, and weirdly resistant to common sense. 
But with local Lunr, no CDNs, and one index per language, it becomes not only possible, but *reasonable*. 
You now have complete control over content indexing, no runtime dependencies on cloud services, and full 
compatibility with air-gapped deployments or sites needing strong privacy guarantees. If not, copy stuff from the 
working code at github: https://github.com/ninabarzh/ipa

If only the rest of Hugo's multilingual features were this straightforward. But that’s another story.

Happy searching.
