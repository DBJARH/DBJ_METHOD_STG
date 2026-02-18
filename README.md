
# Iron Code Labs (Enterpise) Architecture Methodology
## Staging repository

>[!TIP]
Theis is not code developers repository. This repository is hosting 'mark down' documents, presenting the ICL Method, blog posts, and such. No code and no software development.

Main web site: **[From Legacy Lock-in to AI Velocity](https://ironcodelabs.com/)**

This repo GitHub [Link](github.com/ironcodelabs-com/EA_STG/).

## GH Repositories are two: 'EA_STG' for staging and 'EA' for published pages

- Private [Staging Repository](https://github.com/IRONCODELABS-COM/EA_STG)
  - only what is under `docs` folder gets published as 'site'
  - when copied to public twin 'EA', `docs` folder
- Public  [Published Site](https://ironcodelabs-com.github.io/EA)
  - https://ea.ironcodelabs.com is pointing to that site.
  - it is used as a link from the main ICL site

<details markdown="1">
<summary><b>Explanations</b></summary>
<p>

- What is `github.io`?
  - `github.io` is the domain for **GitHub Pages**, a service that automatically turns code stored in a GitHub repository into a live, functional website. In your specific links, it acts as the "host" that tells the internet to look inside the `ironcodelabs-com` account to find the files for the **EA** and **EA_STG** projects.
- What is `https:`?
  - The `https:` at the start of a web address means the connection (aka `link`) is private and protected by **encryption**, essentially turning web site data into a secret code that only you and the website can read. This keeps your personal information, like passwords or login details, safe from hackers who might try to "eavesdrop" on your internet activity.
- ## Staging vs. Production
  - **Staging** is a private "rough draft" version of the website where we test new features to make sure nothing breaks. **Production** is the final, live version that is actually "on air" and ready for the public to use.

</p>  
</details>

## Content

- [docs/](docs/) — Published site pages (methodology vault)
- [blog/](blog/) — Posts staging area
- [research/](research/) — Research notes and taxonomy
  - [Taxonomy (single source of truth)](research/TAXONOMY_FINAL/taxonomy_final.md)
  - [Architecture of LLM Adoption](research/architecture-of-llm-adoption/)
  - [Implementation notes](research/implementation/)
  - [Liquid Foundation Models](research/lfm/liquid_foundation_models.md)
- [custom_styling_guide.md](custom_styling_guide.md) — Jekyll CSS extensions
- [PLAN.md](PLAN.md) — Docs index rework plan
- [AGENTS.md](AGENTS.md) — Rules for AI agents

---

>[!NOTE]
> Unless otherwise declared &copy; Iron Code Labs Ltd & dbj@dbj.org  | CC BY SA 4.0
