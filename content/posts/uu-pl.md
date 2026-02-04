---
title: "Announcing the UU Power & Light Simulator: Teaching OT security without exploding any turbines"
date: 2026-02-04
description: "Or: How we turned Ponder Stibbons' industrial security nightmares into your educational opportunity"
tags:
  - simulation
  - OT
  - ICS
  - Security
  - pentesting
  - proactive defence
draft: false
cover:
  image: "/images/ot-company-location.png"
  alt: "UU P&L location" 
  caption: "The Unseen University Power & Light Co. (UU P&L) facilities in Ankh-Morpork."
  relative: false 
---

There's a fundamental problem with learning operational technology security: the things you need to test are the things you absolutely must not break. This creates what educational theorists call "a bit of a pickle" and what facility operators call "no, you're definitely not touching the production turbines with your laptop."

It's rather like learning to defuse bombs. The theory is straightforward, the practise is somewhat more stressful, and mistakes tend to be memorable for everyone in the vicinity. In OT security, mistakes might not result in explosions (usually), but they can shut down production, trigger safety systems, or cause equipment damage. These outcomes are suboptimal for learning environments and remarkably unpopular with operations teams who prefer their turbines spinning at correct speeds rather than serving as expensive educational exhibits.

This is why most OT security training involves a lot of PowerPoint slides about industrial protocols and very little actual industrial protocol testing. You learn what Modbus is, why it's insecure, and how attacks might theoretically work. What you don't learn is what Modbus exploitation actually looks like, what happens when you send unexpected commands to a PLC, or why reconnaissance of industrial systems requires different techniques than network pentesting.

We wish to solve this problem. Specifically, Ponder Stibbons is solving it through several years of industrial control system security assessments at facilities that were occasionally cooperative, frequently concerned, and universally reluctant to let him actually exploit anything important. His solution: build a simulated facility where mistakes have educational value rather than evacuation requirements.

## Introducing the UU Power & Light simulator

The UU Power & Light simulator is a fully functional industrial control system environment that doesn't control anything physical. It simulates a university power generation facility complete with turbine control PLCs, reactor safety systems, SCADA supervisory control, and all the protocol-level security failures typical of actual OT environments.

What it simulates:

Three turbine control PLCs:
- Modbus TCP protocol (ports 10502-10504)
- EtherNet/IP protocol (port 44818)
- Unauthenticated access to control registers
- Ability to modify speed setpoints, trigger emergency stops, and generally cause chaos

Reactor and safety PLCs:
- S7comm protocol (ports 102-103)
- Complete memory access without authentication
- Programme logic extraction capabilities
- Safety system vulnerabilities

SCADA supervisory control:
- OPC UA protocol (ports 4840-4841)
- Anonymous access allowing complete tag enumeration
- Historical data accessible
- System architecture revealed through tag structure

Supporting infrastructure:
- Four HMI operator workstations
- Engineering workstation with programming access
- Network architecture representative of real facilities
- All the security mistakes you've read about, available for testing

What makes it valuable:

Actual protocols, actual vulnerabilities: This isn't a simplified training environment with artificial flags to capture. It's a realistic implementation of industrial protocols with the security characteristics (or lack thereof) of real OT systems. The Modbus PLCs don't require authentication because real Modbus doesn't support authentication. The S7 systems allow memory reading because that's how S7 works. The OPC UA server permits anonymous access because someone configured it that way, just like in production.

Comprehensive testing scripts: We have included the actual reconnaissance, vulnerability assessment, and exploitation scripts Ponder developed during facility assessments. These aren't theoretical examples. They're working tools that demonstrate real attack techniques:

- Network reconnaissance scripts for device discovery
- Protocol-specific enumeration tools
- Vulnerability assessment utilities
- Proof of concept exploitation demonstrations
- Detection testing capabilities
- Complete attack scenario walkthroughs

Safe learning environment: Mistakes don't cause incidents. Aggressive scanning doesn't affect production. Writing incorrect values to PLCs doesn't damage equipment or trigger safety systems. You can learn what breaking things looks like without actually breaking things, which is rather the point.

Realistic constraints without physical consequences: The simulator teaches you that industrial protocols lack authentication, that PLCs expose complete memory, that SCADA systems reveal operational secrets, and that network segmentation is frequently theoretical. It teaches you what these vulnerabilities mean through practical exploitation. What it doesn't teach you is the organisational complexity of fixing these problems in production, but that's documented separately because some things require actual experience rather than simulation.

## The workshop programme

The simulator is valuable for self-directed learning. It is more valuable when structured into a comprehensive 
training programme. Hence the UU Power & Light OT Security Workshop: a 2-3 day hands-on training course teaching 
operational technology security through practical exercises.

Workshop structure:

Day 1: Reconnaissance and understanding:  You learn industrial protocol fundamentals not through lectures (well, some lectures) but through actual reconnaissance of the simulated facility. You discover what's listening, identify protocols, enumerate devices, and map the attack surface. By lunchtime you understand how Modbus differs from S7. By end of day you've mapped the entire facility architecture through protocol-level reconnaissance.

Day 2: Vulnerability assessment and exploitation: You systematically assess security controls (spoiler: they're mostly absent) and develop proof of concept exploits. You extract PLC programmes, read SCADA databases, modify turbine setpoints, and trigger emergency stops. You learn what these attacks look like, what they achieve, and crucially, what makes them detectable or undetectable.

Day 3: Detection and reporting (optional advanced day): You test whether your attacks would be detected, identify monitoring gaps, and learn to write reports that communicate technical findings to non-technical stakeholders. You discover that generating alerts is easy but generating useful alerts is hard, and that writing "this is vulnerable" is straightforward whilst writing "here's why this matters and what to do about it" is rather more difficult.

Capstone exercise: You conduct a complete security assessment: reconnaissance through reporting, simulating an actual consultant engagement. You deliver technical findings, executive summaries, and stakeholder presentations. If you can successfully explain to a simulated Archchancellor why they should care about Modbus authentication failures, you're ready for actual facility assessments.

Workshop variations: We have designed multiple formats because not everyone needs or has time for three days of hands-on exploitation training:

- Two-day intensive: Core technical skills for security practitioners
- Three-day comprehensive: Complete programme including detection and reporting
- One-day introduction: Reconnaissance and enumeration only, suitable for OT engineers learning security
- Advanced workshop: For experienced practitioners who want detection evasion and red team techniques
- Executive workshop: Half-day demonstration for non-technical stakeholders who need to understand risks and budget implications

Who could benefit:

Security professionals transitioning to OT: If you know IT security and penetration testing but industrial control systems are mysterious, this workshop translates your existing knowledge into OT context. You'll learn what's different (protocols, consequences, constraints) and what's similar (reconnaissance methodology, exploitation principles, reporting requirements).

IT security teams supporting OT: If you're responsible for OT security but don't understand industrial protocols, this provides practical foundation. You'll learn what Modbus is by actually using it, understand S7 by reading PLC memory, and comprehend OPC UA by enumerating SCADA tags. Theory with practise is considerably more valuable than theory alone.

OT engineers learning security: If you understand PLCs and SCADA but security is unfamiliar, this shows what attackers can do with the protocols you use daily. You'll discover that the "temporary" laptop connected to the OT network three years ago is actually a significant security concern, and why "it's fine, nobody knows it's there" isn't actually a security control.

Penetration testers expanding into industrial systems: If you conduct network and application security testing but haven't assessed OT environments, this teaches industrial protocol testing methodologies. You'll learn that the techniques work (reconnaissance, exploitation, reporting) but the protocols, constraints, and consequences are different. And you can make convincing PoC's without touching the production systems!

Incident response teams preparing for OT incidents: If you respond to security incidents and need to understand OT compromise scenarios, this demonstrates what attacks look like, what evidence they leave, and how to distinguish malicious activity from operational anomalies.

## What makes this different from other OT security training

There are several excellent OT security training programmes. What makes the UU Power & Light approach distinctive:

Actual tools, not demonstrations: You don't watch instructors demonstrate exploitation whilst you take notes. You run the actual scripts, see the actual results, and make actual mistakes. The tools are yours to keep, practise with, and eventually use (responsibly and with authorisation) in real assessments.

Realistic vulnerabilities: This isn't a capture-the-flag competition with artificial challenges. These are the actual vulnerabilities Ponder found in real facility assessments. The Modbus PLCs don't require authentication because real Modbus implementations don't require authentication. The challenges are realistic because the vulnerabilities are realistic.

Emphasis on practical methodology: The workshop doesn't just teach "Modbus is insecure." It teaches how to discover Modbus devices, how to enumerate registers, how to identify control parameters, how to test write access safely, how to develop proof of concept exploits, and how to document findings effectively. Methodology matters more than memorising vulnerability lists.

Understanding constraints and consequences: Every exploitation exercise includes discussion of "what would happen in production?" You learn that the emergency stop attack you just demonstrated would shut down power generation for 50,000 people. You learn that the PLC firmware vulnerability you found can't be patched because the vendor's official response is "buy new hardware for €600,000." You learn that budget constraints, operational requirements, and stakeholder concerns matter as much as technical vulnerabilities.

From reconnaissance to reporting: Most training focuses on technical exploitation. This workshop includes writing executive summaries, developing remediation roadmaps, and presenting findings to stakeholders who care about budgets and compliance rather than CVE numbers. You learn that "I can read all the Modbus registers" is technically accurate whilst "unauthorised access could cause operational disruption" is more useful for driving security improvements.

Ponder's perspective throughout: The workshop is built on Ponder Stibbons' actual assessment methodology. The documentation includes his testing notes, his observations about what worked and what didn't, and his perspective on balancing technical security testing with operational realities. You're learning from someone who's actually done this work, made these mistakes, and refined these techniques through real facility assessments.

## Getting started

The UU Power & Light simulator and workshop materials are open source and freely available.

For self-directed learning:

1. Clone the repository: `git clone https://github.com/ninabarzh/power-and-light-sim.git`
2. Install dependencies: `pip install -r requirements.txt`
3. Start the simulator: `python -m src.main`
4. Begin with reconnaissance scripts in `scripts/recon/`
5. Progress through vulnerability assessment in `scripts/vulns/`
6. Explore exploitation scripts in `scripts/exploitation/`
7. Read the documentation in `docs/` for methodology and context

For workshop delivery, the complete workshop materials are included:
- Workshop guide with detailed lesson plans
- Exercise descriptions with learning objectives
- Assessment criteria and evaluation rubrics
- Instructor notes and facilitation guidance
- Slide templates and reference materials

If you're an instructor interested in delivering the workshop, everything you need is provided. If you're an 
organisation interested in hosting the workshop, the materials support both self-delivery and external instruction. 
Mind the licensing though.

For contributions: The simulator is open source because OT security education benefits from community involvement:
- Report issues and bugs via GitHub issues
- Contribute additional scenarios and attack scripts
- Improve documentation and exercise materials
- Share your experience and lessons learned
- Help others learn through the community

## Why this matters

Industrial control system security isn't optional. Critical infrastructure, manufacturing facilities, power generation, 
water treatment, and countless other essential systems depend on OT security. The consequences of failure aren't just 
data breaches and system downtime. They're equipment damage, environmental incidents, and potentially injuries.

Yet OT security expertise is scarce. Many security professionals don't understand industrial protocols. Many OT 
engineers don't understand security. The gap between IT security practise and OT security requirements is significant, 
and crossing that gap requires practical experience that's difficult to obtain safely.

The UU Power & Light simulator provides that experience. It lets security professionals learn industrial protocols 
through actual use. It shows OT engineers what attacks look like through safe demonstrations. It bridges the gap 
between theory and practise by providing an environment where you can make mistakes, learn from them, and develop 
competence without risking actual infrastructure.

This isn't just educational content. It's a tool for improving critical infrastructure security by making OT 
security expertise more accessible, more practical, and more grounded in realistic assessment methodology.

## Ponder's final thoughts

Ponder Stibbons' testing journal, written after several years of OT security assessments, concluded:

"I've assessed power generation facilities, manufacturing plants, water treatment systems, and building automation 
infrastructure. The vulnerabilities are remarkably consistent: protocols designed for reliability rather than security, 
devices configured for convenience rather than protection, and networks architected for operational simplicity rather 
than security segmentation.

"The challenge isn't discovering vulnerabilities. Basic reconnaissance reveals most of them. The challenge is 
understanding what they mean in operational context, communicating their significance to stakeholders who care 
about production rather than protocols, and developing remediation approaches that acknowledge budget constraints 
and operational requirements.

"I've built this simulator because the only way to learn these lessons is through practice, and practising on 
production systems is both dangerous and unpopular. The simulator provides the practice environment. The workshop 
provides the structured curriculum. The documentation provides the methodology and context.

"Use them to learn what OT security actually looks like. Then apply that knowledge carefully, responsibly, and with 
full awareness that real facilities have consequences that simulators cannot replicate.

"Learn safely. Test thoroughly. Implement carefully. These principles matter more in OT than anywhere else in security.

"Start with the simulator. Progress to the workshop. Apply to production with caution and authorisation. This is the 
path to competent OT security work."

## Resources

Repository: [https://github.com/ninabarzh/power-and-light-sim](https://github.com/ninabarzh/power-and-light-sim)

Documentation mostly in [Ponder's narrative built from his notes](https://red.tymyrddin.dev/docs/power/).

Scripts: All reconnaissance, vulnerability assessment, and exploitation scripts can be found in the repo's 
[scripts/ directory](https://github.com/ninabarzh/power-and-light-sim/tree/main/scripts) with comprehensive README files.

Workshop materials: [Complete workshop curriculum, exercises, and facilitation guide](https://red.tymyrddin.dev/docs/services/uu-pl).

Community: GitHub issues for questions, bug reports, and contributions.

Licence: Open source for educational, research, and non-commercial security testing. Commercial use (paid workshops, consultancy, commercial training) requires a commercial licence. See [SECURITY-RESEARCH-EXCEPTION.md](https://github.com/ninabarzh/power-and-light-sim/blob/main/SECURITY-RESEARCH-EXCEPTION.md) and [COMMERCIAL-LICENSE.md](https://github.com/ninabarzh/power-and-light-sim/blob/main/COMMERCIAL-LICENSE.md) for details.

## Contact and support

For simulator issues, bug reports, or technical questions: [GitHub Issues](https://github.com/ninabarzh/power-and-light-sim/issues)

For workshop delivery inquiries, training coordination, or consulting services: See repository README for current contact information.

For general OT security discussion and community support: [Contact us](https://tymyrddin.dev/contact).

*The UU Power & Light Simulator: Teaching you what can go wrong in OT security without anything actually going wrong.*

*Because the best way to learn about turbine overspeed attacks is in an environment where overspeeding turbines doesn't result in expensive mechanical failures, safety incidents, or strongly worded memos from facilities management.*

*Learn safely. Test thoroughly. Implement carefully.*

*This is the UU Power & Light way.*