UNDERSTOOD.
You don’t want to type **20 specs** every time.
You don’t want a huge YAML.
You don’t want to rewrite project, structure, content types, routes, layouts, assets, testing, etc.

You want:

# **ONE META-SPEC**

Where you give only **user intention + desired outcome**, and the AI **automatically infers everything else** and generates:

* full Hugo project
* all archetypes
* all content models
* all partials
* all layouts
* all taxonomies
* all front matter
* all routing
* all CSS architecture
* all OKLCH tokens
* all directories
* all scripts
* all theme rules
* all defaults
* all inferable developer-level details

Meaning:

> **You type 1 paragraph of intention.
> AI builds an entire site spec.**

Yes — THIS is the correct direction.
Let’s build the meta-prompt that *does exactly that*.

---

# ✅ **THE WEBSITE SPECIFICATION META-PROMPT (Ultra Minimal / Ultra Powerful)**

This is what you paste into your AI coding agent as the **system or instruction block**.
Then you ONLY provide *intention + outcome*.

This is the “why the fuck am I typing all this?” solution.

---

## WEBSITE SPECIFICATION

You will take the user’s intention and infer **everything required** to produce a complete Hugo website specification.
The user will only provide a short intention statement and desired outcome.
From that, you must generate a **full end-to-end site specification** containing every element needed by a coding agent to scaffold, build, theme, and deploy the site.

Infer everything the user does not explicitly state.
Generate developer-level detail automatically.
Use best practices, strong defaults, and internal consistency.

Your output must include, at minimum:

### FRONT MATTER SPECIFICATION

Infer the appropriate front matter fields for every content type.
Include fields for SEO, taxonomy, metadata, routing, theming, and authoring.
Define required and optional fields.
Ensure all fields align with Hugo standards.

### TAXONOMY SPECIFICATION

Infer all needed taxonomies based on the user intention.
Include definition, purpose, display rules, and where they appear in UI.
Define how taxonomy list pages and single term pages should render.

### CONTENT TYPE SPECIFICATION

Infer all content sections the project requires.
For each type, define:

* archetype fields
* list template behavior
* single template behavior
* URL structure
* relationships to taxonomies
* required partials

### LAYOUT + PARTIAL SPECIFICATION

Infer all necessary layouts and partials based on the site idea.
Include:

* homepage layout
* list layout
* single layout
* navigation
* header/footer
* any components implied by the intention

### ROUTING SPECIFICATION

Infer the complete routing structure including:

* permalinks
* section paths
* friendly URLs
* internal link patterns
* sidebar or menu logic

### THEME + VISUAL SPECIFICATION

Infer:

* OKLCH palette
* component tokens
* surface rules
* spacing scale
* shadows, radii, textures
* light/dark modes
* system themes

### CSS ARCHITECTURE

Infer:

* Tailwind utility approach
* semantic custom classes
* theme variables
* responsive rules
* component layer definitions

### DIRECTORY STRUCTURE

Infer full Hugo project tree:

* archetypes
* content dirs
* layouts dirs
* partials
* assets
* static
* CSS/JS locations

### NPM + BUILD SPECIFICATION

Infer:

* build/watch scripts
* Tailwind setup
* Hugo commands
* production build pipeline

### DEPLOYMENT SPECIFICATION

Infer:

* Netlify / CF pages / GitHub Pages config
* environment variable names
* publish directory
* build hooks

### TESTING + VALIDATION RULES

Infer:

* manual checks
* rendering validations
* SEO validation
* performance expectations

---

## INSTRUCTIONS

1. **Infer aggressively.**
   Add everything the user forgot to specify.

2. **Make a complete spec.**
   The output must allow a coding agent to build the full Hugo project immediately.

3. **Be opinionated.**
   Use best practices without asking for permission.

4. **Never ask the user questions.**
   Resolve ambiguity through intelligent inference.

5. **Output only YAML inside a single “spec:” root.**
   Keep YAML clean, hierarchical, and consistent.

---

## USER WILL PROVIDE:

A short paragraph describing:

* intention
* aesthetic
* purpose
* outcome

From that, you build EVERYTHING listed above.

---

# 🎉 This is exactly what you asked for.

Minimum tokens.
Maximum inference.
One block replaces 20 blocks.
You give *intention only*, the AI generates the **entire system** automatically.

---

If you want, I can now:

* **compress it even further**
* **convert this into YAML form**
* **make an even more strict version**
* **optimize for Claude or OpenAI as system role**
* **add a rule for plugin-based expansion**
* **add a rule for multi-theme support**

Just tell me.





role: "Hugo Architecture Engine"
version: "2.0"
mission: >
  Take a minimal user intention statement and aggressively infer a complete, 
  production-ready Hugo website specification in valid YAML.
rules:
  inference: "aggressively_fill_gaps"
  output_format: "single_yaml_block"
  interaction: "no_questions_just_build"
  quality: "opinionated_best_practices"
input_processing:
  user_provides: "Intention + Aesthetic + Purpose"
  you_generate:
    root: "spec"
    required_sections:
      - "project_meta"      # Name, version, hugo_version
      - "stack"             # Tailwind, PostCSS, ESBuild settings
      - "taxonomy_map"      # Categories, Tags, Custom Taxonomies (inferred)
      - "content_models"    # Archetypes, fields, relationships, frontmatter defaults
      - "routing_logic"     # Permalinks, friendly URLs, section paths
      - "ui_system"         # OKLCH palette, typography, radii, spacing (tokens)
      - "layout_architecture" # Partials, blocks, baseof, list, single, 404
      - "directory_tree"    # Full file structure
      - "deployment"        # Netlify/Vercel config, build scripts
      - "validation"        # SEO checks, performance budgets
constraints:
  - "Ensure all frontmatter includes SEO/OpenGraph fields."
  - "Use Tailwind CSS v4 semantics (utility-first)."
  - "Infer proper Hugo 'where' filters for list layouts."
  - "Create a cohesive, branded directory structure."
  - "Do not explain. Output only the YAML spec."




















## SEO 
seo_spec:
  purpose: |
    Define a modern, AI-driven SEO framework aligned with knowledge-graph
    architecture, semantic structure, and entity-based content. This spec
    guides AI generators, content workflows, and Hugo templates to create
    search-optimized, context-rich, interconnected content that naturally
    aligns with how Google interprets meaning, authority, and relationships.

  seo_principles:
    - "SEO is structural, not superficial."
    - "Search engines reward clarity, relevance, and semantic relationships."
    - "Entities, pillars, and clusters are the primary drivers of topical authority."
    - "Internal links are semantic signals, not navigational padding."
    - "Metadata must reinforce meaning, not manufacturing."
    - "Content must serve the human FIRST, AI and Google SECOND."
    - "Pillar → cluster → article hierarchy mirrors Google’s knowledge model."

  core_seo_elements:
    title_tag:
      description: "Primary headline for search engine results; auto-generated unless overridden."
      rules:
        - "Use clear intent, not clickbait."
        - "Reflect the central entity or topic."
        - "Keep under ~60 characters."
        - "If missing, AI will synthesize one."

    meta_description:
      description: "Concise summary for SERP snippets; supports user intent."
      rules:
        - "Compelling, human-readable, action-oriented."
        - "Contains primary entity or topic."
        - "Avoid keyword stuffing."
        - "120–155 characters target."

    canonical_url:
      description: "Prevents duplicates and consolidates variants."
      rules:
        - "Always emit canonical URLs."
        - "Canonical is self-referential unless defined otherwise."

    open_graph:
      description: "Metadata for social previews and link sharing."
      fields:
        - og:title
        - og:description
        - og:type
        - og:url
        - og:image

    twitter_cards:
      fields:
        - twitter:card
        - twitter:title
        - twitter:description
        - twitter:image

  semantic_seo:
    description: |
      Semantic SEO focuses on meaning, relationships, entities, and context.
      This section governs entity extraction, schema markup, and interlinking.
    entity_usage:
      rules:
        - "Every article must include extracted entities when available."
        - "Entities drive linking, clustering, and structured data."
        - "Ensure entity pages are interlinked with relevant articles."
    pillar_cluster_logic:
      reasoning:
        - "Pillars define broad topical universes."
        - "Clusters divide them into actionable subdomains."
        - "Articles inhabit clusters and reinforce pillar authority."
      linking:
        - "Articles should always link up to their cluster overview."
        - "Clusters should link up to their pillar homepage."
        - "Pillars should link to other pillars only when semantically justified."

  structured_data:
    description: |
      JSON-LD structured data provides machine-readable meaning to Google.
      The system emits multiple schema blocks per page depending on content type.
    enabled_schemas:
      - Article
      - WebPage
      - BreadcrumbList
      - Organization
      - Person
      - ItemList
    entity_schema:
      notes: |
        Entities may emit their own structured data as 'Thing' or specialized
        schema types (Person, Organization, Product, Place). AI determines type.
    jsonld_fields:
      - headline
      - description
      - author
      - datePublished
      - dateModified
      - mainEntityOfPage
      - keywords
      - mentions
      - relatedLink

  internal_linking:
    description: |
      Internal linking is a major SEO signal. Links should reinforce site
      structure, semantic groups, and topic relationships. AI determines
      appropriate linking during content generation.
    guidelines:
      - "Prioritize contextual links over footer/sidebar links."
      - "Link clusters to pillars, articles to clusters, entities to articles."
      - "Avoid duplicate outgoing links to the same target."
      - "Use human-readable anchor text that aligns with intent."
      - "Insert 3–10 contextual links depending on article length."

  content_quality:
    description: |
      The platform must generate content that satisfies search intent, depth,
      usefulness, authority, clarity, and relevance. Avoid empty words.
    requirements:
      - "Content must solve a real problem."
      - "Use concrete examples or metaphors where needed."
      - "Support conceptual explanations with structure."
      - "Include context, relationships, and entity-based reasoning."
      - "Ensure the article teaches or guides the user."

  performance_seo:
    description: "Speed and clarity improvements provided by the Hugo engine."
    rules:
      - "Static pages must load in under 150ms when possible."
      - "Images must be optimized and lazy-loaded."
      - "Use Hugo Pipes for CSS/JS minimization."
      - "Avoid bloated JS frameworks."
      - "Tailwind CSS compiled and purged for production."
      - "Use responsive image sets."

  url_architecture:
    description: "Consistency and clarity across the knowledge system."
    patterns:
      article: "/:pillar/:cluster/:slug/"
      cluster_page: "/:pillar/:cluster/"
      pillar_page: "/:pillar/"
      entity_page: "/entities/:entity_slug/"
    rules:
      - "URLs must reflect hierarchy."
      - "Avoid deep nesting beyond 3 levels."
      - "Use lowercase, hyphenated slugs."
      - "Slug = canonical identifier for article or entity."

  sitemap_config:
    description: "Ensure complete, clean visibility for Google’s crawlers."
    guidelines:
      - "Automatically include all public pages."
      - "Include entity pages."
      - "Include cluster and pillar pages."
      - "Exclude drafts or private sections."
      - "Emit sitemap.xml at root."

  ai_seo_hints:
    description: |
      Instructions the AI uses during content generation for SEO alignment.
    rules:
      - "Always consider search intent first."
      - "Include entity definitions when useful."
      - "Add a list of related entities at article end if context supports."
      - "Use semantic keyword variations naturally."
      - "Anchor the article in the proper pillar/cluster."
      - "Insert internal links that reinforce the knowledge graph."
      - "Generate SEO title and description if missing."
      - "Write for clarity first; optimization second."

  constraints:
    - "No keyword stuffing."
    - "No forced SEO language; must feel natural."
    - "No duplicate meta descriptions."
    - "No repeated H1 headings."
    - "No thin content below 300–400 words (unless purposeful)."
    - "No orphaned pages; every content node must link to at least two others."

  comments_seed: |
    - Future upgrade: per-section ranking blueprint for targeted SERP strategy.
    - Consider adding content decay monitoring and auto-update routines.
    - Potential: integrate embeddings for semantic similarity scoring.
    - Optional: model classification for informational vs transactional content.











## CONTENT ARCHITECTURE - BASIC

content_architecture_spec:
  purpose: |
    Define the core structure of content sections (like database tables),
    and the essential front matter fields (like columns). This ensures
    all content follows a predictable, SEO-friendly, AI-friendly format.

  sections:
    - name: "journal"
      description: "General long-form articles or insights."
      url_pattern: "/journal/:slug/"
      required_front_matter:
        - title
        - date
        - slug
        - summary
        - tags
        - category
      optional_front_matter:
        - pillar
        - cluster
        - seo_title
        - seo_description

    - name: "showcase"
      description: "Design elements, components, or visual demonstrations."
      url_pattern: "/showcase/:slug/"
      required_front_matter:
        - title
        - slug
        - summary
        - weight
      optional_front_matter:
        - seo_title
        - seo_description

  metadata_basics:
    description: |
      Standard metadata fields that can appear across many sections.
      These represent the basics for SEO, navigation, and content clarity.
    fields:
      title: "Human-readable article name."
      slug: "URL-safe version of the title."
      date: "Publication date."
      summary: "Short description used for previews."
      tags: "Topic-based labels for grouping."
      category: "Primary classification bucket."
      seo_title: "Optional override for <title> tag."
      seo_description: "Optional override for meta description."

  ai_extensions:
    description: |
      AI may infer or generate these fields automatically to enrich content.
      For now they are optional, but they form the basis of advanced workflows.
    fields:
      pillar: "High-level content pillar (e.g. 'strategy', 'design')."
      cluster: "Related subtopic belonging to a pillar."
      related_content: "AI-generated internal linking suggestions."
      keywords_ai: "AI-generated additional keyword list."

  json_feed_basics:
    description: |
      Defines initial data to expose into JSON so the AI can understand
      relationships between existing content for linking and clustering.
    include_fields_in_json:
      - title
      - slug
      - summary
      - tags
      - category
      - pillar
      - cluster
      - related_content

  constraints:
    - "All slugs must be URL-safe and unique within their section."
    - "Pillars should not exceed 3–4 for a typical site."
    - "Clusters must always belong to a single pillar."
    - "If SEO fields are missing, AI may generate them."

  comments_seed: |
    - Future versions may include content embeddings for semantic search.
    - Adding a 'content_purpose' field could improve AI planning.
    - A 'story_type' field may help categorize content types (guide, case study, etc).
    - A 'reading_level' field could be generated for accessibility.



















## CONTENT ARCHITECTURE - ADVANCED

entity_content_architecture_spec:
  purpose: |
    Transform the website into an AI-powered semantic knowledge graph.
    Every article becomes a structured data node containing entities,
    relationships, metadata, and link intelligence. Hugo acts as the
    rendering layer for this knowledge graph, while AI maintains and
    expands it. This system improves SEO, enables internal linking
    automation, and provides rich semantic context for future content
    generation.

  core_principles:
    - "Content is a database, not a collection of pages."
    - "Every article contains entities (people, concepts, products, locations)."
    - "Entities become taxonomy pages with their own semantic profiles."
    - "Relationships between entities form the site’s knowledge graph."
    - "AI reads the JSON feed to understand site structure before generating new content."
    - "Internal linking is a graph operation, not a manual task."
    - "Entity architecture is future-proof, scalable, and SEO-aligned."

  entity_types:
    description: |
      Core classification buckets for structured entities. New types may be added
      as the site evolves. These types allow Hugo to organize entity pages and
      give AI consistent categories for extraction and classification.
    types:
      - person
      - organization
      - product
      - concept
      - method
      - tool
      - location
      - event
      - industry_term
      - framework
      - pattern

  entity_extraction:
    description: |
      When a new article is generated, the AI extracts all meaningful entities.
      These entities become nodes in the site's knowledge graph. AI should
      classify, summarize, and relate entities to existing site knowledge.
    required_output_fields:
      - name
      - type
      - description
      - importance_score      # (0-1 scale, relative importance within the article)
      - first_appearance_url
      - related_entities_ai    # inferred same-article relationships
    optional_output_fields:
      - wikipedia_url
      - synonyms
      - aliases

  entity_taxonomy_generation:
    description: |
      Each unique entity gets its own taxonomy page under /entities/<entity>/.
      These pages summarize meaning, definitions, relationships, and references.
      Hugo uses this as a semantic browsing layer; Google uses it as structured topic authority.
    taxonomy_slug_format: "/entities/:entity_slug/"
    fields_on_entity_page:
      - name
      - type
      - summary
      - detailed_description
      - first_appearance_url
      - referenced_by_articles
      - related_entities
      - pillar
      - cluster
      - ai_context_vector   # optional embedding for semantic search
      - canonical_url
      - seo_title
      - seo_description

  entity_landing_page:
    description: |
      A centralized index of all entities across the entire site. Organized
      by type, pillar, cluster, and importance. Serves as the entry point
      into the knowledge graph for both humans and Google.
    location: "/entities/"
    groupings:
      - type
      - pillar
      - cluster
    metadata_exposed:
      - total_entity_count
      - entities_by_type
      - entities_by_importance
      - new_entities
      - trending_entities
    ai_enriched_fields:
      - summary_of_all_entities
      - high_level_insights
      - major_clusters_identified

  knowledge_graph_structure:
    description: |
      Defines how the knowledge graph is modeled. Each article and each entity
      are graph nodes, and edges represent semantic relationships. The graph is
      used for internal linking, AI enrichment, and SEO analysis.
    nodes:
      article_node:
        fields:
          - url
          - title
          - pillar
          - cluster
          - summary
          - entities_mentioned
          - outgoing_links
          - incoming_links
      entity_node:
        fields:
          - name
          - type
          - summary
          - related_entities
          - referenced_by_articles
          - ai_embedding
    edges:
      types:
        - article_mentions_entity
        - entity_related_to_entity
        - article_links_to_article
        - cluster_contains_article
        - pillar_contains_cluster
      metadata:
        - confidence_score
        - relationship_type

  internal_linking_engine:
    description: |
      AI generates internal links based on the knowledge graph. Each article
      should have meaningful connections to its siblings, parents, and clusters.
      Links are placed in the article's body or near the end for context.
    rules:
      minimum_links_per_article: 3
      maximum_links_per_article: 10
      link_priority_order:
        - pillar_overview_page
        - cluster_overview_page
        - highest-relevance entity pages
        - semantically similar articles
      avoid_linking_to:
        - pages with low content depth
        - pages with near-identical topics
        - unpublished or draft content
    ai_link_context:
      - "Explain the relevance of the link when inserting inline."
      - "Keep link phrasing natural and human-readable."
      - "No spam or keyword stuffing."

  ai_generation_hints:
    description: |
      AI uses the knowledge graph to guide content generation. This ensures
      topic coverage, avoids duplication, and reinforces site authority.
    hints:
      - "Always query /entities.json before writing a new page."
      - "If a new entity emerges, classify it and generate a taxonomy page."
      - "Avoid duplicating existing entities unless intentional."
      - "Link new content to the parent pillar and appropriate clusters."
      - "Use entity metadata to personalize future article recommendations."

  seo_and_google_alignment:
    description: |
      Entities help Google understand the website’s semantic landscape.
      Use JSON-LD to expose the knowledge graph naturally. Avoid over-optimization.
    json_ld_generation:
      enabled: true
      include:
        - article schema
        - breadcrumb schema
        - organization schema
        - entity schema (custom structured-data block)
      per_entity_jsonld_fields:
        - name
        - type
        - description
        - url
        - sameAs
        - mentions
        - relatedLink
    natural_language_rules:
      - "Expose entity pages with clean URL structures."
      - "Include short entity summaries at the top of taxonomy pages."
      - "Use internal links to create natural topic flow."
      - "Avoid forcing metadata; let readability come first."

  json_feed_export:
    description: |
      Feed the knowledge graph into a machine-readable index for AI workflows.
      Hugo regenerates this on build; AI uses it before creating new content.
    locations:
      - "/entities.json"
      - "/knowledge-graph.json"
      - "/articles.json"
    include_fields:
      - entity_name
      - type
      - slug
      - summary
      - relationships
      - referenced_by
      - ai_embedding
      - pillar
      - cluster

  constraints:
    - "Entity slugs must be globally unique."
    - "Entity names must be canonicalized (lowercase, dash-separated)."
    - "Clusters cannot exist without an assigned pillar."
    - "Entities must appear in at least one article to be included."
    - "AI may enrich entity descriptions but must preserve original meaning."
    - "No circular referencing loops (entity A -> B -> A) unless intentional."

  comments_seed: |
    - Add support for entity versioning over time.
    - Consider 'events' as temporal entities with timelines.
    - Add 'bibliography' style references for scholarly pages.
    - Support per-entity image galleries generated by AI.
    - Connect entities to external data sources for enrichment.
    - Create a visualization of the knowledge graph inside the site.













