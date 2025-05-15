# The Broomstick Brief (but hardly brief)

A lightweight, privacy-respecting blog built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme. Deployed on [Netlify](https://www.netlify.com/). Posts are managed locally using [TinaCMS](https://tina.io/), but not exposed in production.

## Features

- Fast, static site built with Hugo modules
- PaperMod theme with custom styling
- Local WYSIWYG post editing via TinaCMS
- Clean, minimal Markdown content in `content/posts/`
- Netlify deployment with Hugo build

## Local Development

```bash
git clone https://github.com/ninabarzh/broomstick.git
cd broomstick
npm install
hugo server
```

To run TinaCMS locally:

```bash
npx tinacms dev -c "hugo server"
```

## Deployment

Handled by Netlify with the build command:

```bash
hugo --gc --minify --cleanDestinationDir
```

Output is served from the public/ directory.

## License

The Unlicense