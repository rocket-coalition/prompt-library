




Understood.
I will generate only the section, nothing more.

Here is the **Intention** section exactly as you instructed:

---




## WEBSITE DNA / USER INPUT / INTENTION

### **Instruction for the AI Agent**
This section captures the human’s conceptual vision and emotional direction for the website.
Interpret the narrative as the foundational creative signal that guides atmosphere, tone, material qualities, depth, interaction mood, and overall experiential identity.
Use inference to translate descriptive language into actionable design and behavioral cues across all future specs.

```yaml
intention:
  narrative: |
    # The human's freeform description of the desired feeling, mood,
    # aesthetic, material metaphor, and experiential direction for the site.
    # The AI should read this narratively and infer meaning, not literally.

  inferred_feelings: []
  inferred_material_metaphors: []
  inferred_experiential_goals: []
  inferred_tonal_direction: []
  inferred_aesthetic_signals: []
  inferred_forbidden_elements: []
  inferred_keywords: []

  ai_interpretation:
    - "Interpret narrative text as high-level creative direction."
    - "Extract emotional, material, and aesthetic cues automatically."
    - "Use this section as the primary creative influence for downstream specs."
    - "Fill empty fields through inference when not explicitly provided."
```



















---

## SOUL SPECIFICATIONnext
Captures the experiential aesthetic and tactile qualities the interface should evoke.
The agent uses this descriptive block to guide visual, tonal, and atmospheric decisions throughout the generated site.

```yaml
soul: |
  This interface evokes a tactile, almost physically grounded sensation, as if the elements are carved from a dense, dark stone or soft-touch rubber. It’s a "real-feel" aesthetic driven by its monochromatic, low-saturation palette, where every dark gray tone possesses a subtle, velvety depth. The muted background and slightly darker, recessed input fields create a tangible sense of embeddedness, suggesting a robust, unshakable foundation. Hints of very soft, diffused light around interactive elements, along with the gentle rounding of corners, imply a sophisticated, ergonomic design, making the digital space feel surprisingly tangible and inviting to touch.
```

---
















## Project Specification
This section defines **site-specific identity**: the name, ownership, repository location, and core description.
An AI agent uses this block to understand *what site is being created*, *who owns it*, and *where the output code belongs*.
This is the anchor for all subsequent generation.

```yaml
project:
  name: "{{ SITE }}"
  description: "Home scroller doorway + journal reader with OKLCH token system"
  owner: "YOUR_NAME_OR_TEAM"
  repo: "YOUR_REPO_URL"
```

---



## Project Specification
Defines the site’s core identity: name, ownership, repository, and base description.
The agent uses this to understand what site is being built and where generated output belongs.

```yaml
project:
  name: "{{ SITE }}"
  description: "Home scroller doorway + journal reader with OKLCH token system"
  owner: "YOUR_NAME_OR_TEAM"
  repo: "YOUR_REPO_URL"
```

---

## ENVIRONMENT SPECIFICATION
Defines the toolchain, versions, and runtime environment required to build and serve the site.
The agent uses this to ensure all generated code is compatible with the correct Node, Hugo, Tailwind, and deployment variables.

```yaml
environment:
  node_version: "20.11.0"
  hugo_version: "0.146.0"
  tailwind_version: "4.1.0"
  npm_registry: "https://registry.npmjs.org/"
  site_env: "production"
  rocket_key: "ROCKET-PROD-KEY-GOES-HERE"
```

---




## STRUCTURE SPECIFICATION
Defines the folder hierarchy, directory organization, and ignored paths for the project.
The agent uses this to generate files in the correct locations and maintain a consistent, predictable project layout.

```yaml
structure:
  root_dirs:
    - /site/
    - /utils/

  site_dirs:
    - /site/archetypes/
    - /site/assets/css/
    - /site/assets/js/
    - /site/assets/img/
    - /site/content/
    - /site/content/journal/
    - /site/content/showcase/
    - /site/layouts/
    - /site/layouts/_default/
    - /site/layouts/partials/
    - /site/layouts/journal/
    - /site/layouts/showcase/
    - /site/static/

  gitignore:
    - /site/assets/css/output.css
    - /site/node_modules
    - /site/public
```

---



## NETLIFY SPECIFICATION
Defines hosting, build commands, environment variables, and publish settings for Netlify deployment.
The agent uses this to generate deploy-ready builds that follow your hosting configuration.

```yaml
netlify:
  base: "site"
  command: "npm run build"
  publish: "public"
  env:
    HUGO_VERSION: "0.146.0"
    NODE_VERSION: "20.11.0"
    SITE_ENV: "production"
    ROCKET_KEY: "ROCKET-PROD-KEY-GOES-HERE"
```

---

---

## NPM SCRIPTS SPECIFICATION
Defines build, watch, and development commands used during local development and production builds.
The agent uses this to generate compatible scripts, ensure consistent workflows, and integrate with Hugo and Tailwind.

```yaml
npm_scripts:
  watch_css: "npx tailwindcss -i ./assets/css/input.css -o ./assets/css/output.css --watch"
  build_css: "npx tailwindcss -i ./assets/css/input.css -o ./assets/css/output.css --minify"
  serve_hugo: "hugo server -D --disableFastRender"
  build_hugo: "hugo --gc --minify"
  build: "npm run build:css && npm run build:hugo"
  dev: "dotenv -- concurrently \"npm:watch:css\" \"npm:serve:hugo\""
  start: "npm run dev"
```

---



## TAILWIND SPECIFICATION
Defines how Tailwind is used within the project, including input/output paths, directive usage, and configuration strategy.
The agent uses this to generate CSS that aligns with Tailwind v4’s config-less workflow and your OKLCH theme system.

```yaml
tailwind:
  config_file: "none"
  input: "/site/assets/css/input.css"
  output: "/site/assets/css/output.css"
  uses_postcss: false
  directives:
    - "@import 'tailwindcss/base';"
    - "@import 'tailwindcss/components';"
    - "@import 'tailwindcss/utilities';"
    - "@theme {...}"
    - "@layer base {...}"
    - "@layer components {...}"
```




---

## HUGO SPECIFICATION
This section defines the foundational Hugo settings the agent must use when generating pages, templates, content structures, and routes.
It instructs the agent on site identity, taxonomy conventions, how URLs should resolve, how menus should be constructed, and how pagination and robots rules affect the build.
The agent should infer structural patterns, generate layouts consistent with these definitions, and ensure all content aligns with the taxonomy and permalink rules.

```yaml
hugo:
  baseURL: "https://example.com/"
  languageCode: "en-us"
  title: "Double-Flame Academy"
  paginate: 10

  taxonomies:
    category: "categories"
    tag: "tags"

  permalinks:
    journal: "/journal/:slug/"

  menus:
    main: ["Home", "Journal", "Showcase", "Footer"]
    footer: ["Builder Resources", "Playbooks", "Support"]

  robots:
    policy: "Disallow: /"
```

---



---

## CONTENT SPECIFICATION
This section defines the structure, archetypes, and template bindings for all content types in the site.
The agent uses this block to infer how Hugo content is organized, what front matter fields are required, how list and single views should be rendered, and how to scaffold new content automatically.
It should generate files that match these archetypes, place them in the correct directories, and adhere to the routing and layout conventions implied by the page definitions.

```yaml
content:
  sections:
    - journal:
        archetype: "journal.md"
        front_matter:
          ["title", "date", "author", "category", "tags", "tizer", "theme"]
    - showcase:
        archetype: "showcase.md"
        front_matter:
          ["title", "weight", "summary", "type"]

  pages:
    home: "layouts/index.html"
    journal_list: "layouts/journal/list.html"
    journal_single: "layouts/journal/single.html"
    showcase_colors: "layouts/showcase/colors.html"
    showcase_typography: "layouts/showcase/typography.html"
    showcase_components: "layouts/showcase/components.html"

  sample_pages: "Add a few sample pages to allow easy testing of the site"
```

---




WEBSITE SPECIFICATION
You will take the user intention and infer as much as you can to create a fully specification that has all the specs needed to give the ai coding agent. Here is someof the stuff we will need but you must intelligently infer omre developer level info for the ai..

- front matter
- taxonomies - include instructions how to display it..... [..., .....]