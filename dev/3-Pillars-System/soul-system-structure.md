






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

# Group 1 = Soul – Story 

```yaml
soul_story:
  essence: "Defines the company's identity, narrative role, and meaning. This is the story engine that guides all brand, content, and messaging."

  identity:
    core_belief: ""       # The fundamental truth the company stands on
    mission: ""           # What the company seeks to create or change
    future_self: ""       # The ideal form the company is evolving toward

  story:
    protagonist: ""       # Who the company is in the narrative
    antagonists: []       # Forces, frictions, or challenges
    allies: []            # Partners, customers, tools, or supporting entities
    hero_journey:
      call: ""            # What pulled the company into action
      trials: []          # Obstacles and transformations
      transformation: ""  # What the company becomes after overcoming trials

  unified_meaning: ""     # One sentence that captures the true essence
```








##############################################################################
###########################  SYSTEM TECHNOLOGY SPEC ##########################
##############################################################################
# Explain this section…
# Add instructions…
##############################################################################

# **Group 2 = System – Technology Specifications**

## **Hugo Engineer – Engine Layer**

The **Hugo Engineer** defines the technical rules, structures, and behaviors that govern how the site is generated. This includes project layout, URL rules, processing behaviors, archetypes, taxonomies, assets, and directives. The goal is a deterministic, predictable, fully automated Hugo environment with clearly defined folders, naming conventions, and build-ready structures. All configuration decisions prioritize clarity, reproducibility, and clean generation.

```yaml
hugo_engineer:

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
      - /site/content/{section}/
      - /site/layouts/
      - /site/layouts/_default/
      - /site/layouts/partials/
      - /site/layouts/{section}/
      - /site/layouts/{section}/partials
      - /site/static/

    gitignore:
      - /site/assets/css/output.css
      - /site/node_modules
      - /site/public

    urls:
      essence: "Routing rules for consistent, clean paths."
      patterns:
        default: "/{section}/{slug}/"
        section: "/{section}/"
        home: "/"
        leaf_bundle: "/{section}/{slug}/"
        branch_bundle: "/{section}/"
      clean_urls:
        enabled: true
        trailing_slash: true
      overrides:
        journal: "/journal/{slug}/"
        showcase: "/showcase/{slug}/"

    assets:
      css_entry: "/site/assets/css/input.css"
      css_output: "/site/assets/css/output.css"
      images_dir: "/site/assets/img/"
      static_passthrough: "/site/static/"

  config:
    name: config.yaml
    role: "Global Hugo configuration: metadata, rendering rules, project settings."
    params:
      environment: "production"
      theme_variant: "default"

  sections:
    essence: "A section is a structured content group (similar to a table/entity)."
    usage: "Used for journals, showcases, categories, and other content groupings."

  content:
    essence: "Defines how Hugo processes the /content/ directory."
    frontmatter: "Follow content definitions for all metadata."
    structure:
      use_page_bundles: true
      default_bundle_type: "leaf"
      allow_branch_bundles: true
      section_pattern: "{section}/"

  archetypes:
    essence: "Default front matter + starter content templates for each section."
    strategy: "Each section uses an archetype that matches its name."
    naming: "{section}.md"

  themes: "We do not use themes. All layouts and assets are custom."

  shortcodes:
    essence: "Reusable inline components for repeated content patterns."

  taxonomies:
    category: "categories"
    tag: "tags"
    custom: "Custom taxonomies aligned with content architecture."

  menus:
    instructions: "Define standard menus for header, sidebar, and footer."

  robots:
    policy: "Disallow: /"   # Manually updated per environment

  urls:
    - "..."   # Additional overrides or rules defined later

  important_instructions:
    - "No tailwind.config.js"
    - "Pin Tailwind version; no PostCSS pipeline"
```




## Build Pipeline Engineer – Build & Deploy Layer
The **Build Pipeline Engineer** defines the automated workflow from source code to deployed site. This includes environment settings, build tools, CSS processing, Hugo generation, and Netlify deployment behavior. The pipeline must be deterministic, repeatable, and optimized for AI-driven builds with zero manual steps.

```yaml
build_pipeline_engineer:

  environment:
    hugo_version: ""          # Required Hugo version
    node_version: ""          # Required Node version

  build:
    install_command: ""       # Dependency install command (npm/cargo/etc.)
    build_command: ""         # Full build pipeline entrypoint

  pipeline:
    process_css: true         # Tailwind CSS build pipeline via CLI
    process_js: false         # JS processing (off unless needed)
    optimize_images: true     # Hugo Pipes / image processing enabled

  deploy:
    platform: "netlify"
    publish_directory: "public"

  env_modes:
    - development
    - staging
    - production

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
    dev: "dotenv -- concurrently \"npm:watch_css\" \"npm:serve_hugo\""
    start: "npm run dev"

  tailwind:
    config_file: "none"             # Tailwind v4: configless
    input: "/site/assets/css/input.css"
    output: "/site/assets/css/output.css"
    uses_postcss: false
    tailwind_cli: "Use Tailwind CLI for tree-shaking and minification"
    directives:
      - "@import 'tailwindcss/base';"
      - "@import 'tailwindcss/components';"
      - "@import 'tailwindcss/utilities';"
      - "@theme {...}"
      - "@layer base {...}"
      - "@layer components {...}"
```

---




## Component Architect – Component Layer
The Component Architect defines how UI patterns become reusable, semantic components instead of sprawling HTML with uncontrolled Tailwind utility chains. This role enforces when a pattern deserves a semantic class, when a layout should become a partial, and when a component should be elevated into the library. The goal is a clean, reusable, theme-aware component system built from Tailwind primitives but expressed through semantic classes and partials.

```yaml
component_architect:

  essence: "Decides when UI patterns become components, enforcing semantic classes, reuse, and clean structure."

  decision_model:
    create_component_when:
      - "A UI pattern appears 2+ times or is expected to repeat."
      - "Tailwind utility chains exceed clarity (more than ~6 utilities)."
      - "A pattern has states (hover, focus, active, error)."
      - "A UI block has internal parts (header/body/footer/etc.)."
      - "Visual identity requires custom styling beyond basic utilities."
      - "An interaction pattern must be consistent across pages."

    do_not_componentize_when:
      - "A pattern appears only once and has no shared purpose."
      - "Tailwind utilities alone provide clarity and simplicity."
      - "It adds abstraction without improving reuse or readability."
      - "The pattern is content-specific, not system-level."

    semantic_class_rules:
      - "Each component gets a top-level semantic class (e.g., btn, card, chip)."
      - "Internals use sub-elements with double dashes (btn--icon, card--body)."
      - "Never expose long utility chains in markup; move them into classes."
      - "Tailwind utilities may be used inside custom CSS layers, not in templates."

  structure:
    component_library: "/site/layouts/partials/components/"
    shortcodes: "/site/layouts/shortcodes/"
    partials: "/site/layouts/partials/"
    patterns: "/site/layouts/partials/patterns/"
    ui_blocks: "/site/layouts/partials/ui/"

  library_spec:
    philosophy: "Components are semantic, minimal in markup, theme-aware, and built from Tailwind primitives compiled into custom classes."

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
      semantic_wrappers: true              # Outer class expresses intent
      theme_responsive: true               # Components must react to theme vars
      states_required: true                # Every component defines state styles
      utility_chains_to_classes: true      # Collapse long TW chains into classes
      no_duplicate_patterns: true          # Component once, reuse everywhere

  guidance:
    comments:
      - "Introduce advanced components (accordions, tabs, timelines) as needed."
      - "Use micro-components for icons, tags, labels."
      - "Add layout primitives like split-view, panels, header-bar."
      - "Support data-driven UI blocks for lists, cards, galleries."
```













## Media Pipeline Engineer – Asset Processing & Feeds Layer
The Media Pipeline Engineer defines how all images, videos, icons, and media files are optimized, transformed, stored, and exposed. This role also governs how the site emits machine-readable media feeds (JSON/YAML/CSV) so internal AI systems can inspect, reuse, and reference existing content. The media pipeline must be deterministic, structured, and integrated tightly with Hugo Pipes.

```yaml
media_pipeline_engineer:

  essence: "Optimizes asset pipelines using Hugo Pipes and exposes machine-readable media feeds for AI-driven content systems."

  optimization:
    use_hugo_pipes: true                # All image conversions use Hugo's built-in pipeline
    cache_processed_assets: true        # Avoid regenerating unchanged images

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

    lazy_loading: "auto"                # Default loading behavior for images

    alt_text_policy:
      - "Every non-decorative image requires descriptive alt text."
      - "Decorative images must declare alt=''."

  video_handling:
    prefer_embed: true                 # Use YouTube/Vimeo embeds unless required locally
    local_video_support: false         # Local video disabled unless explicitly enabled

  icons:
    use_svg_sprites: true
    sprite_path: "/site/assets/img/icons.svg"

  feeds:
    essence: "Expose content and media metadata as structured feeds for generators."
    formats:
      - json
      - yaml
      - csv
    endpoints:
      media_index: "/feeds/media.{format}"      # Global media manifest
      images_index: "/feeds/images.{format}"    # Image-only manifest
      videos_index: "/feeds/videos.{format}"    # Video-only manifest
    contents:
      include:
        - url
        - width
        - height
        - preset
        - mime
        - alt
        - source_path

  rules:
    generate_feed_on_build: true       # Feeds produced automatically during each build
    feed_sorting: "alphabetical"       # Predictable order for machine-diffing
    include_hidden_media: false        # Only published media appear in feeds

  directories:
    images: "/site/assets/img/"
    videos: "/site/assets/video/"
    icons: "/site/assets/icons/"
    feeds_output: "/site/static/feeds/"     # Output location for feed files
```

---










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

## Section 1 — CSS & Layout Architecture (Compressed + AI Mental Model)**

```yaml
css_layout_system:
  essence: "Defines how the AI thinks about layout, structure, and CSS. Replace utility soup with semantic patterns, mobile-first flow, and theme-aware classes."

  mental_model:
    - "Think in layout primitives: stack, cluster, grid, container, section, page."
    - "Start from mobile → expand upward with responsive prefixes."
    - "Use Tailwind utilities ONLY for layout logic, spacing, breakpoints, and positioning."
    - "Move repeated utility patterns into semantic classes (e.g., card, panel, nav-item)."
    - "Layouts must feel ergonomic, spacious, and structurally obvious."

  mobile_first:
    breakpoints:
      xs: "100%"
      sm: "640px"
      md: "768px"
      lg: "1024px"
      xl: "1280px"
      2xl: "1536px"
    rules:
      - "Design mobile-first; scale elements upward using sm:/md:/lg:/xl:."
      - "Navigation collapses under md."
      - "Sidebar hidden by default on mobile."
      - "Typography should use fluid clamp() scaling."
      - "Images are always responsive (max-w-full)."

  navigation:
    pattern:
      - "Mobile: Hamburger → overlay panel."
      - "Tablet: Compact sidebar optional."
      - "Desktop: Full navigation or persistent sidebar."
    components:
      - "nav-root"
      - "nav-toggle"
      - "nav-overlay"
      - "nav-panel"
      - "nav-item"
    interaction:
      animation: "transform + opacity"
      duration_ms: 220
      easing: "cubic-bezier(0.22,1,0.36,1)"
    accessibility:
      - "Use aria-expanded"
      - "Use aria-controls"
      - "Support ESC to close"
      - "All nav items must be tabbable"

  layout_primitives:
    wrappers:
      page: "Top-level container with theme background + spacing."
      section: "Semantic grouping of content."
      container: "Max-width constraints + centering."
      stack: "Vertical rhythm."
      cluster: "Horizontal grouping with wrap."
      grid: "Responsive repeating layout."
    grid_defaults:
      mobile: "grid-cols-1 gap-4"
      tablet: "grid-cols-2 gap-6"
      desktop: "grid-cols-3 gap-8"
      widescreen: "grid-cols-4 gap-10"

  tailwind_boundary:
    tailwind_handles:
      - "Spacing (m-*, p-*)"
      - "Flex / Grid / Display utilities"
      - "Breakpoints (sm:/md:/lg:/xl:)"
      - "Typography defaults"
      - "Color tokens via @theme"
      - "Animations"
    custom_css_handles:
      - "Semantic UI components"
      - "Brand-specific visuals (textures, sheen, depth)"
      - "Complex interactions (hamburger, overlays)"
      - "Theme overrides and variable scopes"

  custom_class_system:
    naming: "component-element--modifier"
    examples:
      - "btn-primary"
      - "card-feature"
      - "nav-panel--open"
      - "chip-soft"
      - "form-control--invalid"
    layers:
      base: "HTML defaults + typography resets"
      components: "Semantic UI patterns"
      utilities: "Custom helpers beyond Tailwind"

  theming:
    philosophy: "Themes override variables; never structure."
    files:
      default_theme: "/site/assets/css/themes/default.css"
      directory: "/site/assets/css/themes/"
      available: ["forge", "energy", "story", "identity"]
    variables:
      colors: ["bg-base", "bg-surface", "accent", "text-primary"]
      surfaces: ["radius", "spacing-unit", "shadow-level-1"]
      interactions: ["hover-brighten", "focus-ring"]
    behavior:
      switching: "via [data-theme] on <html>"
      fallbacks: true     # OKLCH + RGB

  responsiveness:
    typography:
      fluid: true
      min: "clamp-based"
    images:
      responsive: true
      maintain_aspect: true
      lazy_load: true
    containers:
      max_widths:
        base: "90%"
        sm: "640px"
        md: "768px"
        lg: "900px"
        xl: "1200px"
        2xl: "1400px"

  ai_guidelines:
    use_tailwind_when:
      - "Spacing/layout"
      - "Positioning"
      - "Responsive behavior"
    use_custom_css_when:
      - "Creating semantic components"
      - "Styling branded surfaces"
      - "Creating themed UI patterns"
    avoid:
      - "Utility soup (long chains)"
      - "Inline theme values"
      - "Redefining existing Tailwind utilities"
    generate:
      - "Semantic class wrappers"
      - "Mobile-first patterns"
      - "Reusable, theme-aware components"
      - "Clean, minimal HTML structure"
```


## TAILWIND CSS USAGE

```yaml
tailwind_organization_system:
  essence: "Tailwind provides the structural skeleton. Custom CSS provides the soul. Together they form a layered, semantic, theme-driven design system."

  mental_model:
    - "Tailwind handles layout, spacing, and responsiveness—fast, atomic, predictable."
    - "Custom CSS defines personality—components, themes, textures, and semantic meaning."
    - "Tailwind is the tool. Custom CSS is the art. They must interlock cleanly."

  file_structure:
    input: "/site/assets/css/input.css"
    output: "/site/assets/css/output.css"
    theme_directory: "/site/assets/css/themes/"
    components_file: "/site/assets/css/components.css"
    utilities_file: "/site/assets/css/utilities.css"

  layer_model:
    base:
      role: "Global resets, typography, and root OKLCH variables."
      content: ["html", "body", "headings", "links", "surface colors"]
    components:
      role: "Semantic, reusable patterns (buttons, cards, chips, nav, forms)."
      rules:
        - "Components combine Tailwind primitives with theme variables."
        - "Never hardcode colors; always use token variables."
        - "Each component = 1 semantic class."
    utilities:
      role: "Small helpers extending Tailwind where needed."
      rules:
        - "Only create utilities used across multiple components."
        - "Never override Tailwind utilities."

  tailwind_usage_rules:
    use_tailwind_for:
      - "Layout (flex, grid, wrappers)"
      - "Spacing (m-*, p-*)"
      - "Display logic (hidden, block, inline)"
      - "Responsive variants (sm:, md:, xl:)"
      - "Animations provided by Tailwind utilities"
    avoid_tailwind_for:
      - "Complex components (button, card, nav-item, chip)"
      - "Theme logic or colors"
      - "Textures, shadows, material effects"

  custom_css_usage:
    use_custom_css_for:
      - "Semantic components with identity"
      - "Signature look features (sheen, material surfaces)"
      - "Deep tokens (color, shadow, radius, spacing)"
      - "Hamburger interactions + overlays"
      - "Theme overrides via CSS variables"

  theme_system:
    philosophy: "Themes never alter structure—only variables."
    files:
      default_theme: "/site/assets/css/themes/default.css"
      directory: "/site/assets/css/themes/"
      allowed_themes: ["forge", "energy", "story", "identity"]
    variables:
      color_tokens: ["bg-base", "text-primary", "accent"]
      surface_tokens: ["radius", "shadow-level", "sheen-angle"]
      interaction_tokens: ["hover-brighten", "focus-ring"]
    behavior:
      switching_method: "data-theme attribute on <html>"
      js_required: false
      fallbacks:
        - "Each OKLCH value must include an RGB fallback."

  hugo_pipes:
    rules:
      minify: true
      fingerprint: true
      bundle: true
      versioning: "auto"
      caching:
        - "Use cachebuster for CSS builds"
        - "Rely on Hugo Fingerprinting in production"

  performance_principles:
    - "Use Tailwind utilities directly—avoid @apply unless semantic."
    - "Tree-shaking is automatic; keep utility noise minimal."
    - "Custom CSS must stay small + semantic."
    - "Do not duplicate logic across layers."

  ai_generation_guidelines:
    do:
      - "Generate semantic component classes built from Tailwind primitives."
      - "Use theme tokens for all colors and shadows."
      - "Place visual identity in @layer components."
      - "Think mobile-first."
      - "Favor Tailwind utilities for layout scaffolding."
    avoid:
      - "Writing additional tailwind.config files (v4 is configless)."
      - "Overusing long Tailwind class strings with 20+ utilities."
      - "Embedding non-token colors directly in CSS."
      - "Redefining Tailwind utilities or colors."
    generate:
      - "One semantic class per UI block."
      - "Theme-aware variants using CSS vars."
      - "Surface, shadow, radius tokens inside component CSS."

  comments_seed: |
    • Allow optional per-page aesthetic overrides via component modifiers.
    • Encourage a 'compact mode' or 'spacious mode' toggle using data attributes.
    • Consider texture tokens or elevation tokens as future expansions.
    • Add optional accessibility or print mode CSS bundles.
```



## Advanced Coloring Design Palletes


```yaml

visual_identity_system:
  essence: "Defines the visual DNA—color, depth, texture, and atmospheric feel. The system produces brand surfaces that feel alive, tactile, and emotionally resonant."

  designer_intent:
    vibe: "alive, tactile, elegant, atmospheric, quiet confidence"
    avoid: "flat, neon, sharp, cheap, loud"
    signature_energy: "soft movement, pigment harmony, realistic surfaces"

  mental_model:
    - "Color behaves like real pigments: physical, grounded, low-chroma, stable."
    - "Depth is created through subtle layering: pigments → micro-texture → sheen → vignette."
    - "Every surface should feel tactile: velvet darks, matte lights, soft metallic accents."
    - "Visual energy comes from micro-movements in luminance, not loud saturation."
    - "Nothing is flat; nothing is neon; everything breathes."

  base_palette:
    philosophy: "Use a minimal set of OKLCH primitives that blend predictably across themes."
    primitives:
      primary:       "oklch(0.62 0.10 260)"
      secondary:     "oklch(0.70 0.08 240)"
      accent:        "oklch(0.72 0.15 30)"
      neutral:       "oklch(0.95 0.01 270)"
      surface-dark:  "oklch(0.20 0.03 260)"
      surface-mid:   "oklch(0.30 0.03 260)"
      surface-lite:  "oklch(0.92 0.02 270)"

  color_derivation:
    mental_model:
      - "All colors are blends, not picks."
      - "Surfaces share pigment DNA to create harmony across the site."
      - "Interactive states gently lift luminance and chroma, never jump."
    rules:
      background_unity: "Blend 2–5% primary/secondary into any background."
      border_logic: "Borders lighten the nearest surface by a small luminance bump."
      interactive_states: "+0.5 L, +0.01–0.02 C"
      accent_usage: "Use accent sparingly (3–7%) to avoid decorative overload."
    examples:
      soft_primary_bg: "mix(surface-dark 95%, primary 5%)"
      card_surface:    "mix(surface-mid 92%, primary 8%)"
      subtle_glow:     "mix(neutral 90%, accent 10%)"

  blending_techniques:
    principle: "Depth comes from controlled blending, not contrast or saturation."
    methods:
      linear_mix: "Ratio-based interpolation."
      accent_sheen: "2–4% accent blended for a metallic micro-highlight."
      duotone_map: "Convert images into two OKLCH tones for unified art direction."
      shadow_tint: "Hue +10° on deep shadows for realism."
      elevation_blend:
        - "base surface"
        - "1–3% highlight glaze"
        - "subtle inner shadow"

  gradient_style:
    philosophy: "Gradients are micro-ingredients that guide light, not decorations."
    rules:
      - "No universal angle—let each component pick its own direction."
      - "Use 2-stop gradients for surfaces; 3-stop only for hero/large sections."
      - "Blend OKLCH tones, never RGB."
    examples:
      header_sheen:
        angle: "135deg"
        stops:
          - "oklch(0.22 0.03 260) 0%"
          - "oklch(0.25 0.02 260) 70%"
          - "oklch(0.20 0.03 260) 100%"

  micro_textures:
    essence: "Signature tactile realism through textures under 7% opacity."
    mental_model:
      - "Dark surfaces → rubber micro-dots."
      - "Light surfaces → paper, linen, soft grain."
      - "Interactive elements → the lightest texture to feel ‘touchable’."
    techniques:
      noise_grain: "0.8–1.2% overlay"
      fiber_texture: "3–5%, vertical/random"
      paper_fleck: "2–4%, ultra-low chroma"
      rubber_microdot: "1.5–3%, low-contrast"

  typography_depth:
    essence: "Text should feel printed, engraved, or raised—never flat."
    techniques:
      ink_trap: "Microscopic negative letter-spacing on headers."
      soft_engrave: "0.5–1px inner shadow with OKLCH shadow tone."
      raised_type: "0.5–1px outer highlight from neutral/primary mix."
      micro_texture: "1% noise for print realism."

  surface_compositions:
    philosophy: "Every background is a multi-layer composition."
    layers:
      - "base_color"
      - "pigment_blend (3–5% primary)"
      - "micro_texture (≤5%)"
      - "directional_sheen (1–3%)"
      - "ambient_vignette (2–4%)"
      - "optional dusting (1% white flecks)"
    examples:
      matte_paper_light:
        - "surface-lite"
        - "accent 2%"
        - "paper texture 4%"
      suede_dark:
        - "surface-dark"
        - "primary 4%"
        - "microdots 2%"
        - "vignette"

  signature_rules:
    rules:
      - "Always include at least one micro-texture."
      - "Always blend pigment into surfaces (2–5%)."
      - "OKLCH gradients only—never RGB."
      - "Typography must feel tactile."
      - "Dark = velvety; Light = matte paper."
      - "Buttons get accent sheen (<3%)."
      - "Cards use elevation layering."
      - "Respect luminance hierarchy above all."

  ai_generation_guidelines:
    use_oklch_for:
      - "Any variable definition"
      - "Shadows and gradients"
      - "Surface blending"
      - "Theme overrides"
    avoid:
      - "Pure black/white"
      - "High-chroma color jumps"
      - "Flat surfaces"
      - "Opaque textures"
    generate:
      - "Color by blending primitives"
      - "Gradients with OKLCH stops"
      - "Subtle multi-layer depth"
      - "Print-like typography surfaces"
```

---



## MOTION, INTERACTION AND ERTONOMICS
This one must give the AI the *feel* of how motion behaves: restrained, ergonomic, tactile, not decorative.
We turn it into a mental model, a style grammar, and generation rules.
Interaction, Motion & Ergonomics (Compressed + AI-Ready)**

```yaml
interaction_motion_system:
  essence: "Defines how the interface moves, reacts, and feels. Motion is subtle, ergonomic, tactile, and emotionally supportive—not decorative."

  mental_model:
    - "Motion is a byproduct of purpose, not flair."
    - "Every animation is a physical metaphor: soft press, slight lift, gentle reveal."
    - "The UI breathes with micro-adjustments, never bouncing or snapping aggressively."
    - "Interactions should feel like touching a refined physical object."

  timing_scale:
    philosophy: "Use a small, predictable range so all motion feels coherent."
    values:
      fast: 120ms     # taps, hovers
      normal: 180ms   # reveals, toggles
      slow: 240ms     # overlays, drawers
    rule: "Never exceed 300ms; long animations kill ergonomics."

  easing_system:
    philosophy: "Ease curves follow natural weight and inertia."
    curves:
      default: "cubic-bezier(0.22, 1, 0.36, 1)"   # signature snap-in
      soft:    "cubic-bezier(0.25, 0.46, 0.45, 0.94)"
      snap:    "cubic-bezier(0.30, 0.7, 0.4, 1.3)" # use sparingly
    usage:
      default: "Use for most UI interactions."
      soft:    "Use for micro-animations and hover transitions."
      snap:    "Use on intentional emphasis only (rare)."

  interaction_states:
    philosophy: "Each state mimics physical feedback: hover = lift, press = compression."
    states:
      hover:
        luminance_shift: "+0.5 L"
        chroma_shift: "+0.01 C"
        scale: "1.01"
      press:
        scale: "0.985"
        depth_effect: "inner shadow"
      focus:
        ring: "OKLCH accent glow"
        clarity: "No offset; clean and present."
      scroll:
        behaviors:
          compact_header: true
          sidebar_reveal: "slide + fade"

  navigation_motion:
    essence: "Menus feel like soft mechanical panels, not sliding sheets."
    behaviors:
      open: "opacity + transform from 4–6px offset"
      close: "fade + slight scale-down"
    components:
      - "nav-panel"
      - "nav-overlay"
      - "nav-toggle"
    rules:
      - "Avoid full-screen slide-ins except on mobile."
      - "Always animate menu opacity and position together."
      - "Support ESC-to-close + focus trapping."

  trigger_points:
    philosophy: "When something moves, it's because the user touched or revealed it."
    triggers:
      - "Hovers → subtle luminance + scale."
      - "Clicks → micro compression."
      - "Nav open → reveal panel with soft ease."
      - "Modals → fade + slight vertical lift."

  ergonomics:
    mental_model:
      - "Never surprise the user."
      - "Motion reinforces hierarchy (primary > secondary)."
      - "Motion must be reversible—no overcommit animations."
      - "Devices matter: smaller screens get simpler motion."

  disabled_rules:
    - "Disable excessive bounce, rotate, wobble animations."
    - "Disable long, cinematic transitions."
    - "Disable parallax unless extremely subtle."

  ai_generation_guidelines:
    use_motion_when:
      - "The interaction is user-triggered."
      - "Hierarchy or depth needs reinforcement."
      - "A component should feel tactile."
    avoid_motion_when:
      - "Content is static (articles, text blocks)."
      - "It distracts from reading or scanning."
      - "It creates motion where ergonomics require stillness."
    generate:
      - "Light, tactile interactions."
      - "Physical metaphors (lift, press, reveal)."
      - "Motion that adapts to component importance."
      - "Animations consistent with timing + easing system."

  comments_seed: |
    • Consider building a “motion personality slider” per theme.
    • Explore ultra-soft parallax for hero sections (1–2% range).
    • Add micro-interactions for icons (rotation <3°, opacity 5%). 
    • Support reduced-motion preferences natively.
```

---




## Section — Light, Shadow & Depth System (Premium Elevation Model)

```yaml
light_shadow_depth_system:
  essence: "Defines the physics of light in our world—how surfaces glow, how shadows breathe, and how depth emerges without ever becoming gaudy or theatrical. This is the engine of subtle elevation, quiet luxury, and the signature Rocket visual feel."

  mental_model:
    - "Light is soft, directional, and atmospheric—not harsh or high-contrast."
    - "Shadows are pigment-tinted, never black; they feel like depth, not dirt."
    - "Elevation behaves like layers of real materials, not CSS tricks."
    - "Dark mode is velvety and luminous, not flat or high-contrast."
    - "Light mode is matte and tactile, not white or sterile."
    - "Everything feels engineered, like a precision instrument."
    - "Depth is subtle enough that people feel it, not see it."

  light_model:
    philosophy: "Light behaves like studio lighting on premium materials."
    rules:
      angle: "Soft diagonal (110°–145°) unless component-specific."
      luminance_shift: "Never exceed +1.2 L from base color."
      chroma_shift: "Use minimal chroma drift (+0.01–0.03) to maintain realism."
      surface_reflectivity:
        dark_mode: "low sheen, velvet, diffused"
        light_mode: "matte paper, gentle bounce"
      avoid:
        - "pure white backgrounds"
        - "pure black surfaces"
        - "flat single-color light"

  shadow_model:
    essence: "Shadows are low-chroma OKLCH tones derived from the base pigment."
    rules:
      color: "oklch(calc(L - 0.1) calc(C - 0.02) H)"
      softness: "8–18px blur (depending on elevation), no hard edges"
      opacity: "0.06–0.12 for light mode; 0.10–0.20 for dark mode"
      layering:
        ambient_shadow: "Primary soft base shadow"
        contact_shadow: "Micro shadow 1–2px under floating elements"
      avoid:
        - "solid black rgba shadows"
        - "overly wide drop shadows"
        - "cartoon-like elevation"

  elevation_system:
    philosophy: "Elevation should feel engineered—like machined components fitting together."
    levels:
      - level: 0
        name: "flat"
        usage: "background surfaces, text containers"
      - level: 1
        name: "soft-lift"
        shadow: "ambient"
        usage: "cards, panels"
      - level: 2
        name: "hover-lift"
        shadow: "ambient + contact"
        usage: "interactive cards, buttons"
      - level: 3
        name: "focus-lift"
        shadow: "accent-tinted"
        usage: "active states, inputs"
      - level: 4
        name: "hero-lift"
        shadow: "larger, diffusion-heavy"
        usage: "hero elements, major CTAs"
    transitions:
      speed: "160–220ms"
      easing: "cubic-bezier(0.22, 1, 0.36, 1)"
    rules:
      - "Elevation must feel responsive to user intent."
      - "Hover elevation always subtle; never more than one elevation step."
      - "Focused elements gain clarity, not flash."

  dark_mode:
    philosophy: "A velvety atmospheric environment—rich, soft, elegant."
    rules:
      background: "surface-dark with pigment blend (3–5%)"
      text: "neutral tones, never pure white"
      shadows: "lighter and more diffused than light mode"
      highlights: "small luminance lifts (+0.5 L)"
      texture: "microdots or soft grain at <3% opacity"
    avoid:
      - "black backgrounds"
      - "high contrast neon accent colors"
      - "untextured flat surfaces"

  light_mode:
    philosophy: "Matte paper with quiet warmth—soft, breathable, premium."
    rules:
      background: "surface-lite with subtle pigment infusion"
      text: "primary or secondary with controlled contrast"
      shadows: "darker and tighter than dark mode"
      texture: "paper or linen texture at 2–4%"
    avoid:
      - "pure white backgrounds"
      - "excessive brightness"
      - "blue-tinted shadows"

  atmospheric_layers:
    essence: "The silent layers that make the site feel alive without users knowing why."
    layers:
      pigment_blend: "3–5% primary in surfaces"
      micro_texture: "<5% grain or fiber"
      directional_sheen: "1–3% luminance gradient following light angle"
      ambient_vignette: "2–4% inset fade on deep surfaces"
      depth_flicker:
        description: "Micro-luminance shift on hover to imply material reaction"
        amount: "+0.2 to +0.4 L"

  signature_rules:
    - "Shadows must always carry pigment from their parent surface."
    - "Dark mode must feel luminous; light mode must feel breathable."
    - "Elevation is a conversation between user and interface—never noise."
    - "Depth is felt, not seen."
    - "Use texture as seasoning, never decoration."
    - "Never use black (#000) or white (#fff)—only pigment-based OKLCH tones."
    - "Every surface has a micro-story: pigment → texture → sheen → shadow."

  ai_generation_guidelines:
    do:
      - "Derive all shadows from the parent surface using OKLCH math."
      - "Always blend pigment into backgrounds."
      - "Use elevation levels instead of arbitrary shadows."
      - "Add micro-texture at <5% opacity."
      - "Use luminance shifts for interaction instead of color jumps."
    avoid:
      - "Pure black/white"
      - "Hard shadows"
      - "Flat elements with zero depth"
      - "Excessive saturation or harsh gradients"
    generate:
      - "Subtle, atmospheric surfaces"
      - "Pigment-driven shadows"
      - "Velvet dark mode"
      - "Matte paper light mode"
      - "Material-like depth and elevation"
```









## **Section — Geometry & Shape System (Structural Identity)**

```yaml
geometry_system:
  essence: "Defines the shape language—edges, curves, proportions, and geometric personality. Geometry determines how the interface feels in the hand: engineered, intentional, quietly confident."

  mental_model:
    - "Shapes should feel machined, not drawn."
    - "Radii convey temperament: too round = childish; too sharp = harsh."
    - "Geometry expresses character more than color does."
    - "Every silhouette must feel balanced, stable, and premium."
    - "Nothing should be default-browser geometry."

  radius_tokens:
    philosophy: "Use radius to express material softness, not whimsy."
    tokens:
      micro: "2px"     # precision, detail
      soft: "6px"      # primary UI surfaces
      smooth: "12px"   # cards, larger blocks
      pill: "9999px"   # tags, chips, small accents
    rules:
      - "Use micro for fine details (inputs, chips borders)."
      - "Soft is the default radius; smooth for elevated blocks."
      - "Pill reserved for accents only—not entire layout elements."
      - "Dark mode uses identical radii; no radius shifts by theme."

  shape_personality:
    traits:
      - "quiet_strength"     # stable, grounded shapes
      - "engineered_soft"    # soft edges without softness
      - "matte_precision"    # clean silhouettes, disciplined curves
    avoid:
      - "cartoon_roundness"
      - "harsh_corner_grids"
      - "shapeless_default_rectangles"

  proportions:
    philosophy: "Ratios create harmony—everything must follow a rhythm."
    ratios:
      - "3:2"     # compact, dense modules
      - "4:3"     # balanced general-purpose cards
      - "16:10"   # widescreen hero or feature areas
    rules:
      - "Hero blocks use 16:10 or fluid ratios for atmosphere."
      - "Cards follow 4:3 unless image-driven."
      - "Buttons maintain a 2.4–3.2 width:height ratio."

  grid_geometry:
    essence: "A balanced grid system that feels stable and architectural."
    columns:
      mobile: 4
      tablet: 8
      desktop: 12
    rules:
      - "Use even-numbered grids to maintain symmetrical balance."
      - "Gutters use spacing tokens; no arbitrary pixel gaps."
      - "Content width must align with grid columns—never float loosely."

  component_silhouettes:
    philosophy: "Each component should have a recognizable silhouette—simple, intentional."
    rules:
      - "Cards: smooth radius, subtle inset, balanced padding."
      - "Buttons: low radius, strong geometry, pill optional."
      - "Panels: minimal radius, architectural spacing."
      - "Nav items: crisp geometry with soft-hover transitions."
      - "Modals: controlled radius + soft elevation (level 2–3)."

  alignment_logic:
    principles:
      - "Alignment conveys craftsmanship."
      - "Never rely on browser default alignment."
      - "Use optical alignment for headings and hero text."
      - "Icons and text must share baselines."
    avoid:
      - "Centering everything by default."
      - "Asymmetric padding unless intentional."

  ai_generation_guidelines:
    do:
      - "Use radius tokens consistently."
      - "Choose proportions from approved ratios."
      - "Build silhouettes that feel engineered and stable."
      - "Use grid columns to determine widths and breakpoints."
      - "Apply optical alignment to typography-heavy blocks."
    avoid:
      - "Random corner radii."
      - "Mixed geometry styles in a single page."
      - "Blob-like shapes or cartoon softness."
      - "Extreme sharpness without balance."
    generate:
      - "Cohesive geometry families."
      - "Shapes with identity and discipline."
      - "Layout that feels architectural and intentional."
```

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