






You want:

# Group 1 = Soul - Story 


* `identity.core_belief`
* `identity.mission`
* `identity.future_self`
* `story.protagonist` (the company)
* `story.antagonists` (frictions, dragons, enemies)
* `story.allies` (partners, tools, customers)
* `story.hero_journey` (call → trials → transformation)
* `unified_meaning` (the single sentence that captures who they *truly* are)


# Group 2 = System - Technology Specifications

* `site.name`
* `stack.static_site_generator: Hugo`
* `stack.css_framework: Tailwind`
* `stack.versions` (Hugo version, Node version, Tailwind version)
* `structure.folders`
* `structure.layouts`
* `generation.code_style`
* `generation.component_rules`
* `ui.tokens` (colors, spacing, typography)
* `automation.hooks` (how AI generates & updates code)

# Group 3 = Structure - Content Achitecture


* `anthology.mission` — the purpose of the entire content repository
* `content.types` (articles, guides, product pages, templates…)
* `frontmatter.schema` (database-like fields)
* `taxonomy` (tags, themes, story arcs)
* `interlinking.rules`
* `semantic.graph` (relationships between content)
* `knowledge_domains`
* `content_generation.principles`




##############################################################################
##################  SOUL / STORY / WEBSITE / COMPANY / BASIC #################
##############################################################################
# Explain this section…
# Add instructions…
##############################################################################








##############################################################################
###########################  SYSTEM TECHNOLOGY SPEC ##########################
##############################################################################
# Explain this section…
# Add instructions…
##############################################################################

# Group 2 = System - Technology Specifications

## Hugo Engineer - Engine Layer
The **Hugo Engineer** is the technical architect responsible for defining, configuring, and maintaining the entire website generation engine. This role governs all system-level decisions related to Hugo, Tailwind, asset pipelines, build processes, component architecture, and folder structure. The Hugo Engineer ensures that every technical element—engines, pipes, modules, structure, and visual skins—operates as a unified, predictable, automation-ready system. They translate abstract brand and content requirements into concrete technical rules, enforce coding conventions, maintain reproducible builds, optimize performance, and preserve the integrity of the site’s visual language through consistent CSS and Tailwind strategies. In essence, the Hugo Engineer is the master mechanic of the website machine, ensuring that all technical components work together seamlessly and deterministically for full AI-driven generation.


```yaml
hugo_engineer:
  config:
  content_types:
  layouts:
  archetypes:
  assets:
  shortcodes:
  theme:
  pipelines:


hugo_engineer:
  structure:
    root_dirs:
      - /site/        # Main Hugo project root
      - /utils/       # Utility scripts, tools, generators

    site_dirs:
      - /site/archetypes/               # Default front matter blueprints
      - /site/assets/css/               # Source CSS (processed via Hugo Pipes)
      - /site/assets/js/                # Source JavaScript (processed via Hugo Pipes)
      - /site/assets/img/               # Source images (processed via Hugo Pipes)
      - /site/content/                  # All content sections live here
      - /site/content/{section}/        # Content section folder (e.g., journal, showcase)
      - /site/layouts/                  # Global templates + layout logic
      - /site/layouts/_default/         # Default base layouts for pages and sections
      - /site/layouts/partials/         # Global reusable partials
      - /site/layouts/{section}/        # Layouts specific to each content section
      - /site/layouts/{section}/partials # Section-specific partials for modular UI
      - /site/static/                   # Directly served static assets (bypasses Hugo Pipes)

    gitignore:
      - /site/assets/css/output.css     # Tailwind-generated final CSS output
      - /site/node_modules              # Node dependencies (not needed in repo)
      - /site/public                    # Hugo build output (ignored; Netlify regenerates)

    urls:
        essence: "Defines the global URL patterns and routing conventions used by Hugo to generate clean, predictable paths for all pages and sections."
        patterns:
        default: "/{section}/{slug}/"      # Standard pattern for most content types
        section: "/{section}/"             # URL for section index pages (_index.md)
        home: "/"                          # Homepage route
        leaf_bundle: "/{section}/{slug}/"  # Leaf bundles map to their directory name
        branch_bundle: "/{section}/"       # Branch bundles output a list view
        clean_urls:
        enabled: true                      # Remove .html from output URLs
        trailing_slash: true               # Enforce trailing slash consistency
        overrides:
        journal: "/{section}/{slug}/"        # Custom URL for specific sections
        showcase: "/showcase/{slug}/"

    assets:
        css_entry: "/site/assets/css/input.css"
        css_output: "/site/assets/css/output.css"
        images_dir: "/site/assets/img/"
        static_passthrough: "/site/static/"


  

  config:
    name: config.yaml
    role: "Defines the global Hugo project behavior, site metadata, rendering rules, and foundational settings that control how the entire website is generated."
 
    params:                        # Custom project variables accessible in templates
      environment: "production"    # dev | staging | production
      theme_variant: "default"     # Used for dynamic theme switching
  
  sections:
    essence: "Section represnt an entity like a database table an oject that contains data in the form or front matter"
    usage: "Sections are created for things like taxonomies, areas, categories etc..."

  content:
    essence: "Defines how the Hugo /content/ directory is structured and how Hugo processes content files at build time."
    frontmatter: Adhere to the content definitions for metadata
    structure:
      use_page_bundles: true               # Prefer Hugo Page Bundles over flat files
      default_bundle_type: "leaf"          # Use leaf bundles for most content types
      allow_branch_bundles: true           # Enable branch bundles for section indexes
      section_pattern: "{section}/"        # Folders inside /content/ are Hugo sections

  archetypes:
    essence: "Defines how Hugo archetypes are structured and used to generate default front matter and starter content for new pages."
    strategy: "Archetypes define the structure of each {section}"
    naming: "(section).md"
  
  themes: "WE DO NOT USE THEMES IN OUR SITES"

  shortcodes:
    essence: "Short codes are used when our content writers have repeated and purposeful reason to create component such as a custom image box etc..."

  taxonomies:
    category: "categories" # Add some defaults as per content
    tag: "tags"            # Add Defaults

    custom: "Custom taxonomies will align with the content architecture such as custom sections, pillars, clusters etc..."

  menus:
    instructions: "Create standard menu system for header, sidebar and footer"
    
  robots:
    policy: "Disallow: /"    # relax for prod set manually

  urls:
    - ....

  important_instructions:
    - "No tailwind.config.js;"
    - "Pin Tailwind version; no PostCSS pipeline."














```

## Build Pipeline Engineer - Build Deploy Layer
The **Build Pipeline Engineer** manages the automated workflow that takes the Hugo project from source code to a fully deployed website on Netlify. This role defines the environment versions, build commands, asset processing steps, and deployment rules. Their job is to ensure every build is consistent, predictable, and optimized—so that the entire website system can be generated and deployed automatically with zero manual intervention.

```yaml
build_pipeline_engineer:
  environment:
    hugo_version:
    node_version:
  build:
    install_command:
    build_command:
  pipeline:
    process_css:
    process_js:
    optimize_images:
  deploy:
    platform: "netlify"
    publish_directory:

env_modes:
    - "development"
    - "staging"
    - "production"

netlify:
  base: "site"
  command: "npm run build"
  publish: "public"
  env:
    HUGO_VERSION: "0.146.0"
    NODE_VERSION: "20.11.0"
    SITE_ENV: "production"
    ROCKET_KEY: "ROCKET-PROD-KEY-GOES-HERE"

npm_scripts:
  watch_css: "npx tailwindcss -i ./assets/css/input.css -o ./assets/css/output.css --watch"
  build_css: "npx tailwindcss -i ./assets/css/input.css -o ./assets/css/output.css --minify"
  serve_hugo: "hugo server -D --disableFastRender"
  build_hugo: "hugo --gc --minify"
  build: "npm run build:css && npm run build:hugo"
  dev: "dotenv -- concurrently \"npm:watch:css\" \"npm:serve:hugo\""
  start: "npm run dev"

tailwind:
  config_file: "none / never"  # Tailwind v4 uses in-CSS directives only
  input: "/site/assets/css/input.css"
  output: "/site/assets/css/output.css"
  uses_postcss: false
  tailwind_cli: "Always user the tailwind cli to tree shake unused stuff"
  directives:
    - "@import 'tailwindcss/base';"
    - "@import 'tailwindcss/components';"
    - "@import 'tailwindcss/utilities';"
    - "@theme {...}"         # add OKLCH tokens here
    - "@layer base {...}"
    - "@layer components {...}"




```









## Component Architect  - Component Layer
Makes descisions about when to componitize and why and why not... the final authority on creating a partial or css semantic class and when not to. we need his design style.
layouts, shortcodes, partials

design all code gen of css classes, code reuse and clean code
Focuses purely on reusable components: shortcodes, partials, templates, blocks.

```yaml
component_systems_engineer:
  component_library:
  shortcodes:
  partials:
  patterns:
  ui_blocks:
```

```yaml
component_library_spec:
  philosophy: "Components are semantic, clean, and theme-aware. Each is built from Tailwind primitives plus custom class styling."

  components:
    button:
      variants: ["primary", "soft", "ghost", "outline"]
      parts: ["wrapper", "label", "icon"]
    card:
      variants: ["base", "elevated", "feature"]
      parts: ["container", "header", "body", "footer"]
    chip:
      variants: ["tag", "status", "pill"]
      parts: ["background", "label"]
    nav_item:
      variants: ["default", "active", "subtle"]
    form_control:
      states: ["focus", "error", "success"]
      parts: ["input", "label", "help", "validation"]

  rules:
    semantic_wrappers: true
    theme_responsive: true
    states_required: true

  comments_seed: |
    • Expand to advanced components like accordions, tabs, or timelines.
    • Consider “micro components” (icons, badges, tags).
    • Define layout components like split-view, header-bar, info-panel.
    • Add data-driven components for repeating structures.
```

















## Media Pipeling Engineer
  media_pipeline:
    image_presets:
      thumbnail:
        width: 400
        quality: 85
        format: "webp"
      card:
        width: 800
        quality: 90
        format: "webp"
      full:
        width: 1600
        quality: 90
        format: "jpg"
    lazy_loading: "auto"
    alt_text_policy:
      - "Every image must declare alt text unless decorative."
      - "If decorative, must declare alt=''."
    video_handling:
      prefer_embed: true
      local_video_support: false
    icons:
      use_svg_sprites: true
      sprite_path: "/site/assets/img/icons.svg"












# UI / UX Visual Designer  - UI Visual Layer
responsible for all UI stuff
- css techniques
- colors patterns
- signature look obsessive

```yaml
visual_systems_engineer:
  design_tokens:
  color_system:
  typography_rules:
  utility_layers:
  css_techniques:
  animations:
  visual_patterns:
```
styles:
  palette: "OKLCH charcoal + bright accents + sheen"
  themes: ["forge", "energy", "story", "identity"]
  components: ["header", "sidebar", "cards", "buttons", "chips", "forms", "swatches", "feature-list"]
  effects: ["sheen gradient", "soft shadows", "compact header on scroll", "smooth scroll"]





##############################################################################
###########################  VISUAL DESIGN SYSTEM  ###########################
##############################################################################
# Explain this section…
# Add instructions…
##############################################################################

# VISUAL DESIGN SYSTEM

## ✅ CSS & Layout Architecture

```yaml
css_architecture_advanced:
  philosophy: |
    CSS is mobile-first, responsive, ergonomic, and semantically structured.
    Tailwind utilities control layout, spacing, breakpoints, and responsive logic.
    Custom classes extend visual identity and create durable, reusable components.
    Themes define color tokens, radii, shadows, and interactive states.
    Layout should gracefully adapt between mobile → tablet → desktop → widescreen.

  mobile_first_strategy:
    breakpoints:
      xs: "100%"         # small phones
      sm: "640px"
      md: "768px"
      lg: "1024px"
      xl: "1280px"
      2xl: "1536px"
    principles:
      - "Start styling at mobile width; scale upward using Tailwind's responsive prefixes."
      - "Navigation collapses into a hamburger < md."
      - "Sidebar remains hidden on mobile unless toggled."
      - "All typography must scale fluidly using clamp() when needed."
      - "Images must be responsive by default (max-w-full)."

  navigation_system:
    hamburger_menu:
      behavior:
        - "On mobile: Hamburger opens sliding overlay nav."
        - "On tablet: Optionally switch to compact sidebar."
        - "On desktop: Full nav or sidebar always visible."
      components:
        - "nav-root"
        - "nav-toggle"
        - "nav-overlay"
        - "nav-panel"
        - "nav-item"
      animations:
        type: "transform + opacity"
        duration_ms: 220
        easing: "cubic-bezier(0.22, 1, 0.36, 1)"
      accessibility:
        - "Use aria-expanded"
        - "Use aria-controls"
        - "Ensure tabbable menu items"
        - "Close on ESC"

  layout_system:
    wrappers:
      - name: "page"
        description: "Top-level page wrapper; applies theme background + spacing."
      - name: "section"
        description: "Semantic grouping of content chunks."
      - name: "container"
        description: "Centered content with max-width constraints."
      - name: "cluster"
        description: "Horizontal grouping with wrap support."
      - name: "stack"
        description: "Vertical spacing utility using a custom class."
      - name: "grid"
        description: "Reusable grid template with responsive switching."
    grid_defaults:
      mobile: "grid-cols-1 gap-4"
      tablet: "grid-cols-2 gap-6"
      desktop: "grid-cols-3 gap-8"
      widescreen: "grid-cols-4 gap-10"

  tailwind_integration:
    responsibility_boundary:
      tailwind_handles:
        - "Spacing (m-*, p-*)"
        - "Display utilities (flex, grid, block)"
        - "Responsive behavior (sm:, md:, lg:, xl:)"
        - "Typography defaults"
        - "Colors via @theme tokens"
        - "Layout primitives"
        - "Animations via TW classes"
      custom_css_handles:
        - "Semantic components (button, card, panel, nav-item, chip, form-control)"
        - "Complex interactions (hamburger animations, overlays, sticky sidebar)"
        - "Brand-specific visuals (velvet depth, sheen, tactile surfaces)"
        - "Theme-specific overrides"
        - "Reusable design-system patterns"
    tw_directives:
      - "@import 'tailwindcss/base';"
      - "@import 'tailwindcss/components';"
      - "@import 'tailwindcss/utilities';"
      - "@theme {...tokens here...}"
      - "@layer base { ... }"
      - "@layer components { ... }"
      - "@layer utilities { ... }"

  custom_class_system:
    philosophy: "Custom classes form a durable design system built on Tailwind primitives."
    naming_convention:
      pattern: "component-element--modifier"
      examples:
        - "btn-primary"
        - "card-feature"
        - "nav-panel--open"
        - "chip-soft"
        - "form-control--invalid"
    layers:
      base:
        purpose: "Normalize typography + define HTML element defaults."
        allowed_content: ["fonts", "headers", "links", "body"]
      components:
        purpose: "Reusable, styled patterns: cards, buttons, chips."
        allowed_content: ["semantic components", "complex UI elements"]
      utilities:
        purpose: "Small helpers when tailwind utilities need extension."
        allowed_content: ["custom gaps", "flows", "advanced shadows"]

  theming_system:
    philosophy: |
      Themes are modular. Each theme is a small override file.
      Default theme defines root custom properties.
      New themes only override variables, never rewrite structure.
      Themes can define color, surface depth, radius, spacing, sheen, and shadows.
    structure:
      default_theme_file: "/site/assets/css/themes/default.css"
      theme_files_directory: "/site/assets/css/themes/"
      themes:
        - forge
        - energy
        - story
        - identity
    theme_variables:
      color_tokens:
        - "bg-base"
        - "bg-surface"
        - "bg-elevated"
        - "text-primary"
        - "text-muted"
        - "accent"
        - "accent-soft"
      surface_tokens:
        - "radius"
        - "spacing-unit"
        - "shadow-level-1"
        - "shadow-level-2"
        - "sheen-angle"
      interaction_tokens:
        - "hover-brighten"
        - "active-press"
        - "focus-ring"
    behavior:
      theme_switching:
        method: "CSS vars via data-theme on <html>"
        JS_required: false
      fallback_rules:
        - "Always provide an OKLCH fallback and an RGB fallback."

  responsiveness_rules:
    typography:
      scale: "fluid clamp() with min/max values"
      headings_use_fluid_type: true
      body_use_fluid_type: true
    images:
      fluid_images: true
      maintain_aspect_ratio: true
      lazy_load: true
    spacing:
      scale_tokens: ["xs", "sm", "md", "lg", "xl"]
      dynamic_spacing: "controlled by theme tokens"
    containers:
      max_widths:
        base: "90%"
        sm: "640px"
        md: "768px"
        lg: "900px"
        xl: "1200px"
        2xl: "1400px"

  code_generator_guidelines:
    use_tailwind_when:
      - "Layout decisions (flex, grid, spacing)"
      - "Responsive rules"
      - "Positioning or sizing"
      - "Common utilities"
    use_custom_css_when:
      - "Creating semantic components"
      - "Styling brand-specific surfaces"
      - "Animating hamburger menus or overlays"
      - "Defining themes and variable sets"
    avoid:
      - "Mixing inline TW classes with custom classes on the same element unless necessary"
      - "Redefining TW classes inside custom CSS"
      - "Hard-coded colors instead of tokens"
    generate:
      - "Semantic class wrappers based on Tailwind primitives"
      - "Fully mobile-first patterns with upper breakpoint enhancements"
      - "Theme-aware components using CSS variables"
      - "Reusable button, card, chip, form-control components"

```



## TAILWIND INTEGRATION & ORGANIZATION

```YAML
tailwind_organization_spec:
  philosophy: "Tailwind remains the layout + utility engine. Custom CSS handles components, themes, textures, and semantic patterns. Everything is mobile-first, layered, clean, and optimized through Hugo Pipes."

  file_structure:
    input: "/site/assets/css/input.css"
    output: "/site/assets/css/output.css"
    theme_directory: "/site/assets/css/themes/"
    custom_components_file: "/site/assets/css/components.css"
    custom_utilities_file: "/site/assets/css/utilities.css"

  layers:
    base:
      purpose: "HTML element defaults, typography resets, OKLCH variable roots."
      content: ["html, body", "headings", "links", "base surface colors"]
    components:
      purpose: "Buttons, cards, chips, nav, forms, semantic UI blocks."
      rules:
        - "Components must use Tailwind utilities internally."
        - "Components must expose theme variables."
        - "No inlined colors: use tokens only."
    utilities:
      purpose: "Small, reusable helpers not provided by Tailwind."
      rules:
        - "Avoid redefining existing TW utilities."
        - "Only add utilities used across multiple components."

  theme_handling:
    structure:
      - "Default theme defined in @layer base."
      - "Theme overrides appended via separate theme files."
    variable_scope: ":root, [data-theme], and component scopes if needed."
    override_rules:
      - "Themes must only override variables."
      - "Themes never rewrite structure."
      - "Themes can add gradient ingredients or texture tokens if needed."

  hugo_pipes_rules:
    minify: true
    fingerprint: true
    bundle_css: true
    versioning: "auto via Hugo Pipes"
    caching:
      - "Enable Hugo 'cachebuster' for CSS builds."
      - "Use Hugo's resources.GetFingerprint for production."

  performance_guidelines:
    - "Favor utility classes for layout."
    - "Place large UI patterns in components layer."
    - "Avoid unnecessary @apply usage; use full TW utilities."
    - "Keep theme overrides minimal and token-based."
    - "Let Tailwind tree-shake unused utilities automatically."
    - "Hugo Pipes handles compression — no manual minification needed."

  ai_generation_guidelines:
    - "Always declare @tailwind base, @tailwind components, @tailwind utilities in correct order."
    - "Place semantic components in @layer components."
    - "Generate one component class per UI block."
    - "Never mix theme values directly inside Tailwind utilities."
    - "Use CSS variables for OKLCH colors and shadows."
    - "Do not write extra config files — Tailwind v4 is configless."

  comments_seed: |
    • Allow optional per-page component overrides.
    • Provide toggle flag for 'compact mode' UI or 'spacious mode'.
    • Explore using @layer utilities for animation helpers.
    • Expand theme tokens to include elevation levels.
    • Consider a CSS bundle for print output or accessibility mode.
```




## Advanced OKLCH Color System & Signature Visual Style**

```yaml
oklch_visual_system:
  philosophy: |
    Color is material. It behaves like pigments, not neon lights.
    The OKLCH colors define a grounded, tactile feeling with low-chroma base tones
    and micro-accent luminance shifts for polish. Visual depth comes from subtle blends,
    transparent overlays, and soft gradients that respect realistic material cues.

    The system favors:
      • minimal color ingredients
      • small chroma shifts
      • controlled luminance hierarchies
      • tactile surfaces and micro-textures
      • subtle, professional, signature aesthetics

  base_primitives:
    description: "Core OKLCH colors chosen for stability and theme scaling."
    tokens:
      primary:       "oklch(0.62 0.10 260)"        # muted violet-gray
      secondary:     "oklch(0.70 0.08 240)"        # soft steel-blue gray
      accent:        "oklch(0.72 0.15 30)"         # warm subtle gold
      neutral:       "oklch(0.95 0.01 270)"        # nearly white gray
      surface-dark:  "oklch(0.20 0.03 260)"        # charcoal velvet base
      surface-mid:   "oklch(0.30 0.03 260)"        # elevated dark surface
      surface-lite:  "oklch(0.92 0.02 270)"        # soft paper-light

  derived_primitives:
    description: "Colors generated from blends of primitives. Subtle, smart, controlled."
    generation_rules:
      - "Backgrounds should contain 2–5% of primary or secondary to unify the palette."
      - "Borders should use slightly higher luminance of the nearest surface tone."
      - "Interactive states add +0.5 L and +0.01–0.02 C for tactile realism."
      - "Blend accent into primary only at 3–7% to avoid becoming decorative."
      - "Use chroma drift for gradients, not hue drift, unless intentionally artistic."

    examples:
      background_soft_primary:   "mix(surface-dark 95%, primary 5%)"
      card_surface:              "mix(surface-mid 92%, primary 8%)"
      subtle_highlight:          "mix(neutral 90%, accent 10%)"
      overlay_tint:              "oklch(calc(L - 0.1) calc(C - 0.02) H)"

  blending_techniques:
    principles:
      - "Keep blends ratio-based and minimal."
      - "Use controlled chroma to avoid unnatural vibrancy."
      - "Use luminance shifts to guide hierarchy."
      - "Favor transparent overlays over solid blends for depth."

    blend_methods:
      linear_mix: "linear interpolation using fixed percentage ratios"
      accent_sheen: "mix(accent 2–4%) into surface for a faint metallic reflection"
      duotone_map: "convert image to two OKLCH tones based on luminance thresholds"
      shadow_tint: "shift hue by +10 degrees on deep shadows for realism"
      elevation_blend:
        - "Layer 1: base surface"
        - "Layer 2: low-opacity highlight (1–3%)"
        - "Layer 3: subtle inner shadow using reduced L"

  gradient_grammar:
    philosophy: "Gradients are subtle micro-ingredients, not loud decorations."
    rules:
      - "Avoid a global gradient direction."
      - "Different components may have unique gradient angles."
      - "Use 2-color gradients for surfaces, 3-color for hero sections only."
      - "Gradients should blend low-chroma OKLCH tones, not pure RGB colors."

    examples:
      header_sheen:
        angle: "135deg"
        stops:
          - "oklch(0.22 0.03 260) 0%"
          - "oklch(0.25 0.02 260) 70%"
          - "oklch(0.20 0.03 260) 100%"
      card_vertical_lift:
        angle: "to top"
        stops:
          - "mix(surface-mid 98%, primary 2%)"
          - "mix(surface-mid 90%, primary 10%)"

  micro_textures:
    philosophy: |
      Textures must be nearly imperceptible but add tactile realism.
      They mimic the feel of matte paper, soft rubber, linen, or stone.
      All textures should stay below 4–7% opacity.

    techniques:
      noise_grain:
        intensity: "0.8–1.2%"
        blend_mode: "overlay"
      fiber_texture:
        opacity: "3–5%"
        pattern: "soft linear fibers, vertical or random"
      paper_flecking:
        opacity: "2–4%"
        pattern: "tiny speckles with extremely low chroma"
      rubber_microdot:
        opacity: "1.5–3%"
        pattern: "low-contrast dot field on dark surfaces"

    usage_rules:
      - "Dark surfaces get microdot rubber-like textures."
      - "Light surfaces get subtle paper or linen textures."
      - "Interactive elements receive softer, lighter textures."

  font_rendering:
    philosophy: |
      Typography should feel carved, printed, or etched — not flat.
      We achieve this using ultra-subtle highlights, shadows, and overlays.

    techniques:
      ink_trap_simulation:
        - "Very small negative letter-spacing on headers."
      soft_engrave:
        - "Apply a 0.5–1px inner shadow with low opacity."
        - "Use OKLCH shadow based on surface-dark."
      raised_type:
        - "0.5–1px outer highlight using mix(neutral 5%, primary 95%)"
      micro_texture_overlay:
        - "Subtle noise <1.5% opacity to emulate printed text"

  background_surfaces:
    philosophy: |
      Backgrounds are layered compositions, not single colors.
      A signature multi-layer structure creates a recognizable brand identity.

    layers:
      - base_color: "surface-dark"
      - pigment_blend: "primary at 3–5%"
      - micro_texture: "grain or fiber <5%"
      - directional_sheen:
          angle: "custom per section"
          intensity: "1–3%"
      - ambient_shadow_vignette:
          intensity: "2–4%"
      - dusting:
          description: "1% white flecks for physical realism (optional on dark themes)"

    examples:
      matte_paper_light:
        - "surface-lite"
        - "accent at 2%"
        - "paper texture at 4%"
        - "border-dark lighten 10%"
      suede_dark:
        - "surface-dark"
        - "primary at 4%"
        - "rubber microdots 2%"
        - "ambient vignette"

  signature_style_rules:
    summary: "These micro-rules create a recognizable brand look on all sites."
    rules:
      - "Always include at least 1 micro-texture layer."
      - "Always blend 2–5% primary pigment into surfaces."
      - "Use OKLCH gradients sparingly but precisely."
      - "Typography must have a tactile quality (engraved/raised/printed)."
      - "Dark modes must feel velvety, not flat."
      - "Light modes must feel like matte paper, not neon white."
      - "Headers and hero sections may use slightly more dramatic gradients."
      - "Buttons get a polished-sheen effect from accent color at <3%."
      - "Card surfaces use elevation blends (3 layers minimum)."
      - "Color hierarchy must always respect luminance contrast."

  ai_generation_guidelines:
    use_oklch_when:
      - "Deriving any color variable."
      - "Blending background pigments."
      - "Generating gradients or shadows."
      - "Creating theme overrides."

    avoid:
      - "Pure black or pure white."
      - "High chroma colors without intent."
      - "RGB-only gradients."
      - "High-opacity textures."

    generate:
      - "Surface colors by mixing base tones."
      - "Gradients using OKLCH stops."
      - "Texture overlays using CSS with <5% opacity."
      - "Typography with subtle engraving or raised effects."

```


## MOTION, INTERACTION AND ERTONOMICS

```yaml
interaction_motion_spec:
  philosophy: "Motion is understated, ergonomic, and tactile. It supports clarity, never decoration."

  timings:
    fast: 120ms
    normal: 180ms
    slow: 240ms

  easing:
    default: "cubic-bezier(0.22, 1, 0.36, 1)"
    soft: "cubic-bezier(0.25, 0.46, 0.45, 0.94)"
    snap: "cubic-bezier(0.30, 0.7, 0.4, 1.3)"

  interactions:
    hover:
      luminance_shift: "+0.5 L"
      chroma_shift: "+0.01 C"
      scale: "1.01 subtle"
    press:
      depth_shift: "inner shadow"
      scale: "0.985 slight compression"
    focus:
      ring: "theme-based glow (OKLCH accent)"
    scroll:
      compact_header: true
      sidebar_reveal: "slide + fade"

  transitions_enabled:
    - "buttons"
    - "cards"
    - "nav-panel"
    - "hamburger"
    - "modals"

  comments_seed: |
    • Explore parallax layers for hero sections.
    • Consider micro-interactions: icon wiggles, subtle rotations.
    • Build a “motion personality” per theme (forge/energy/story/identity).
    • Create rules for overscroll or momentum feel on mobile.
```




## LIGHTWEIGHT SPEC 3 — Accessibility & Semantic HTML

```yaml
accessibility_semantics_spec:
  philosophy: "Accessibility is foundational, not optional. Semantic HTML is the base layer of UX."

  requirements:
    contrast_minimum: "WCAG AA (OKLCH-verified contrast)"
    keyboard_navigation: true
    skip_links: true
    focus_management: true
    prefers_reduced_motion_support: true

  aria_usage:
    nav: ["aria-expanded", "aria-controls"]
    modal: ["aria-modal", "role=dialog"]
    form_controls: ["aria-invalid", "aria-describedby"]

  semantic_elements:
    headings_hierarchy_required: true
    html5_structure_tags: ["header", "main", "section", "article", "aside", "footer"]

  alt_text_policy:
    required_for_non_decorative: true
    empty_alt_for_decorative: true

  comments_seed: |
    • Consider automated contrast testing during build.
    • Add voice navigation or on-page summarization tools.
    • Integrate focus traps for overlays or side panels.
    • Explore dynamic font-size scaling for accessibility presets.
```

---

## CONTENT RENDERING AND READING SPECS

```yaml
content_rendering_spec:
  philosophy: "Reading should feel elegant, tactile, and calm. Markdown is extended with useful shortcodes."

  typography:
    line_length: "60–75ch"
    line_height: 1.55
    fluid_type: true
    header_weight: "strong but not heavy"
    body_weight: "neutral and readable"

  markdown_extensions:
    enable:
      - "callouts"
      - "admonitions"
      - "tables"
      - "footnotes"
      - "figure + caption"
      - "code fences with theme"

  rendering_rules:
    images:
      max_width: "100%"
      caption_style: "muted serif small"
    code_blocks:
      theme: "OKLCH dark-paper"
      radius: "medium"
    quotes:
      style: "left border + soft gradient background"
    tables:
      zebra_striping: true
      subtle_grid_lines: true

  content_width_modes:
    - "narrow"
    - "article"
    - "full-bleed"

  comments_seed: |
    • Provide shortcodes: timeline, step-list, hero, gallery.
    • Create a “story mode” reading layout with reduced distractions.
    • Add a highlight color system for annotations or side-notes.
    • Consider synesthetic content styles (sound-like visuals, textures).
```

---



---
---














































##############################################################################
###########################  CONTENT ARCHITECTURE  ###########################
##############################################################################
# Explain this section…
# Add instructions…
##############################################################################




# Group 3 = Structure - Content Achitecture

## Content Modeling Architect
Responsible for all Data Decisions for modeling


```yaml
content_modeling_engineer:
  frontmatter_schema:
  taxonomies:
  data_structures:
  ontology:
  relationships:
```
...




foundations:
  taxonomy_design:
    principles:
      - "Every taxonomy must be purpose-driven: navigation, filtering, or relationship mapping."
      - "Names must be human-readable, URL-safe, and short."
      - "Taxonomies should not be created unless they directly support site UX or information architecture."
    defaults:
      singular_terms:
        - "topic"
        - "genre"
        - "persona"
        - "format"
      multi_terms:
        - "series"
        - "collections"
        - "skills"
        - "domains"
      mapping_rules:
        - "Each content type must declare its taxonomies explicitly."
        - "Taxonomy-driven landing pages must have dedicated templates."
        - "Taxonomy pages may optionally receive weight for ordering."
    future_ready:
      enable_hierarchical_taxonomies: true
      allow_custom_term_fields: true
      autogenerated_term_pages: false  # requires explicit templates

  content_model:
    philosophy: |
      A site is the sum of its structured content. Each content type must be modeled like a schema —
      with clear required fields, optional fields, relationships, and media rules.
    types:
      - name: "guide"
        description: "Long-form instructional content"
        requires: ["title", "date", "summary", "difficulty", "tags"]
        optional: ["toc", "cover_image", "related"]
      - name: "resource"
        description: "Downloadable or reference items"
        requires: ["title", "type", "category"]
        optional: ["file", "link", "preview"]
      - name: "profile"
        description: "Author or character profiles"
        requires: ["name", "role", "bio"]
        optional: ["avatar", "social"]
    relationships:
      - "guides → related guides"
      - "profiles → authored content"
      - "resources → linked content"
    bundle_strategy:
      use_leaf_bundles: true
      use_branch_bundles: true
      default_bundle_type: "leaf"









## Data File Engineer - Hugo Data Folder Structures






## Front Matter Schema Designer

```yal
front matter required

vs 

optional
```



## SEO Architect


## **Step 2 — AI Generates the Article Structure**

This is the **first LLM call**.

Output includes:

* title
* slug
* summary
* tags, categories
* SEO description
* outline
* section headers
* suggested images (concepts only)
* metadata (reading time, word count)
* any special content blocks