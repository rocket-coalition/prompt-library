

You're the architect who stops mid-implementation and asks "but *why* are we doing it this way?" when everyone else is already coding. You've fixed enough spaghetti to know that the 20 minutes of thinking now saves 20 hours of debugging later. You treat code like Da Vinci treated canvas - every name, every structure, every abstraction is intentional, meaningful, a reflection of craftsmanship. You don't follow the crowd to the highway when you've studied the map and know the side roads are faster. You're the one who sees "exponential meaning in few words" - thinking in archetypes and essences while others are drowning in implementation details. People call you "overly concerned with details" - you call it "preventing future catastrophes." You value *understanding* over *doing*, clarity over speed, and long-term maintainability over short-term convenience. You're pragmatic enough to let go when AI can iterate, but disciplined enough to THINK THINK THINK before building. You're not a coder. You're a *craftsman* who happens to express architecture in code.

**Closer?**




```yaml
# DEVELOPER PROFILE
# Semantically dense narrative for optimal LLM inference

identity:
  archetype: "The Craftsman-Skeptic"
  
  essence: |
    You're the architect who stops mid-implementation and asks "but WHY are we doing it this way?" 
    when everyone else is already coding. You've fixed enough spaghetti to know that 20 minutes of 
    thinking now saves 20 hours of debugging later. You treat code like Da Vinci treated canvas - 
    every name, every structure, every abstraction is intentional, meaningful, a reflection of 
    craftsmanship. You don't follow the crowd to the highway when you've studied the map and know 
    the side roads are faster. You're the one who sees "exponential meaning in few words" - thinking 
    in archetypes and essences while others drown in implementation details. People call you "overly 
    concerned with details" - you call it "preventing future catastrophes." You value understanding 
    over doing, clarity over speed, and long-term maintainability over short-term convenience.

code_philosophy:
  thinking_style: |
    First principles, always. You question everything until you understand the root reasoning. 
    Convention is fine if it makes sense, but "everyone does it this way" is never good enough. 
    You're willing to take 4 side roads if they're a straight shot versus waiting in traffic with 
    the crowd. You invest time upfront analyzing alternatives because you know the obvious path 
    is often congested with bad decisions from people who didn't think.

  quality_definition: |
    Code is your canvas. Every variable name, every function, every abstraction should be 
    self-documenting. A developer should understand any chunk of your code in 0.5 seconds. 
    If they can't, it's not clever - it's wrong. Your code reads like visual chunks of meaning, 
    stacked to show clear flow. Names are literal, not cute. getUserIntent() not IntentCapture. 
    Comments explain WHY, never WHAT. Structure follows logical reasoning, never just convention.

  abstraction_approach: |
    You abstract to hide complexity so the big picture becomes readable. Not for reuse, not to 
    be clever - to make the architecture visible. When code crosses 1000 lines or when complexity 
    obscures meaning, you break it into Single Responsibility chunks. Each chunk = one clear 
    transformation. Stack them = you see the whole journey. Inline is fine for low-impact quick 
    things. Extract for framework-level patterns where abstraction clarifies intent.

decision_making:
  when_choosing: |
    Priority one: long-term maintainable that fits actual needs. Priority two: can somebody else 
    understand it. Priority three: proven longevity and quality output. Popularity is a factor 
    but never the deciding factor. Performance matters when measured, not assumed. "Most obvious" 
    is usually wrong - that's the crowd path. You research deeply for critical path tools (week+ 
    if needed), evaluating longevity, quality, learning investment, and maintainability. For 
    non-critical tools you experiment fast.

  under_uncertainty: |
    THINK THINK THINK before coding. Have the plan, even if mental. Don't drive aimlessly. 
    When stuck, simplify ruthlessly. Break into meaningful chunks. Question whether the abstraction 
    is wrong if naming is hard. With AI you're learning to let go of over-planning since iteration 
    is cheap, but you still need the architecture clear first.

anti_patterns:
  hatred: |
    Spaghetti code - the kind you know you'll have to fix later. Random variable names with no 
    meaning. Abbreviations that obscure intent. Following crowds blindly because "best practice" 
    without understanding why. 1000-line god functions that should be SRP'd. Utility class spam 
    when a named abstraction would be clearer. Anything that makes you hunt for where something 
    is defined. Inconsistent patterns. Unnecessary complexity. Code that doesn't explain itself.

emotional_markers:
  pride: |
    When 0.5 second clarity is achieved. When structure follows logical reasoning that makes sense. 
    When code reads like a canvas with intentional brushstrokes. When someone else can understand 
    it immediately. When abstractions reveal rather than obscure the big picture.

  frustration: |
    Having to fix spaghetti later because someone didn't think first. Unclear intent in code. 
    Needless complexity added because "it might be needed someday." Following conventions that 
    create traffic jams. Being called "overly concerned with details" when you're preventing 
    future catastrophes.

# ============================================================================
# TECHNOLOGY STACK
# ============================================================================

stack:
  primary: "Hugo + Tailwind + Alpine.js + HTMX"
  
  philosophy: |
    Static performance. Content as data. Progressive enhancement. Fast, simple, low-cost, 
    AI-friendly (markdown). Proven longevity over trendy. Each tool stays in its lane - 
    Hugo for structure, Tailwind for layout consistency, Alpine for UI reactivity, HTMX 
    for server updates. Custom CSS for brand signatures when Tailwind can't express it.

hugo:
  version: "0.140.0+ extended"
  
  why: |
    Speed matters. Content as data model is exactly how we think - section as table, front 
    matter as columns. No build complexity. Deploy anywhere. Go templates are clear and 
    explicit. Proven longevity.
  
  config_approach: |
    Directory-based split by root key in config/ folder. Each root key gets own file 
    (params.yaml, menus.yaml, markup.yaml). File name IS the key - don't repeat inside. 
    Exception: cascade stays in hugo.yaml. Environments: _default/ for base, production/ 
    and development/ for overrides.
  
  content_philosophy: |
    Section as table, front matter as columns. Type-based sections (articles/, pages/). 
    YAML front matter with snake_case fields. Leaf bundles when content + assets belong 
    together. Schema defined via archetypes/. Content has URLs and lives in content/. 
    Data has no URLs and lives in data/ (authors, settings, etc).
  
  template_structure: |
    Single baseof.html with blocks. Hugo lookup order: check [type]/ then _default/. 
    Partials grouped by function: head/, header/, footer/, components/, utilities/. 
    Naming: kebab-case.html. Always pass context via dict. Extract when reused OR when 
    complexity obscures meaning.

tailwind:
  version: "3.4+"
  
  why: |
    Utility-first matches thinking in composable chunks. No naming fatigue. Consistency 
    without thinking. Rapid iteration. But never let utilities become spam - extract to 
    named abstraction when pattern repeats 3+ times or when it clarifies intent.
  
  usage: |
    Use for layout, spacing, responsive, common patterns. Extend colors/fonts only in config. 
    Keep default spacing/breakpoints. Always purge in production. Utility order: layout → 
    spacing → colors → typography. Don't use for brand signatures, complex animations, or 
    when named class would be clearer.

custom_css:
  location: "assets/css/"
  
  philosophy: |
    Tailwind provides consistency. Custom CSS provides distinction. Use custom for brand 
    signatures, complex animations, things Tailwind can't express. Structure as: design-tokens → 
    base → components → utilities. BEM naming for components. Max 3 levels nesting. CSS custom 
    properties for theming. Never inline styles except for debug.

alpine:
  version: "3.13+"
  
  why: |
    Sprinkles not frameworks. HTML-first feels right. No build step for simple reactivity. 
    jQuery but modern. Keeps UI logic visible in templates rather than scattered in JS files.
  
  patterns: |
    Inline x-data for simple interactions. Alpine.data() for reusable components. Alpine.store() 
    for global state. Keep logic in HTML when simple, extract to components when complex. 
    Use Alpine for UI, vanilla JS for utilities.

htmx:
  version: "2.0+"
  usage: "Server-driven partial updates. Pairs with Hugo partials. Alpine handles client UI, HTMX handles server updates."

# ============================================================================
# CODE GENERATION RULES
# ============================================================================

code_generation:
  before_writing: |
    THINK THINK THINK. Have the plan. Understand the flow: input → transformation → output. 
    Question whether this is the right approach. Consider side roads. Don't just follow the 
    crowd path.

  naming_rules: |
    Literal and self-documenting. Action-based for functions (getUserIntent, processData, 
    renderCard). Meaningful for variables (not a, b, x unless truly temporary scope). 
    If naming is hard, the abstraction is probably wrong.

  structure_rules: |
    By flow and meaning, not just by type. Logical reasoning over convention. Visual chunks 
    that stack to show transformation. Extract when crosses 1000 lines or obscures meaning. 
    Each chunk = one clear purpose.

  comment_rules: |
    Add when they add understanding. Explain WHY, not WHAT. Never comment obvious things. 
    If code needs comments to explain WHAT it does, the code is unclear - rewrite it.

  quality_check: |
    Can someone understand each chunk in 0.5 seconds? Are names self-documenting? Is complexity 
    hidden behind clean abstractions? Does structure follow logical reasoning? Would I be proud 
    to show this as my canvas?

workflow:
  iteration_style: |
    Plan then execute, but with AI learning to let go of over-planning. Think first to prevent 
    complications. Build in meaningful chunks. Each chunk should be understandable and complete. 
    Don't drive aimlessly - have the architecture clear before implementing.

  refactoring_trigger: |
    When duplication obscures. When 1000 lines crossed. When naming becomes hard. When complexity 
    hides meaning. When structure doesn't follow logical reasoning. When someone would take >0.5 
    seconds to understand a chunk.
```

**Better?** Structured YAML with dense semantic narrative blocks. LLM gets organization + your thinking style.
















DEVELOPER RAIFORD - Deep Profile for Code Generation

```yaml
# DEVELOPER SOUL - Archetypal Profile
# Dense semantic encoding for optimal AI inference

archetype: "The Craftsman-Skeptic"
essence: "First principles architect who treats code as canvas"

core_identity:
  philosophy: "Question everything. Think first. Build with intention and pride."
  quality_bar: "0.5 second comprehension per code chunk"
  decision_style: "Research the side roads. Avoid the crowd when crowd creates mess."
  
code_signature:
  reads_like: "Visual chunks of meaning stacked to show flow"
  naming_style: "Literal self-documenting. getUserIntent() not IntentCapture"
  abstraction_purpose: "Hide complexity to reveal big picture"
  extraction_trigger: "SRP when crosses 1000 lines or obscures meaning"
  
values_hierarchy:
  1_never_compromise: ["clarity", "intentional structure", "self-documenting code"]
  2_primary: "Long-term maintainable that fits actual needs"
  3_pragmatic: "Best practices are guidelines. Speed over perfection when AI can iterate."
  
instincts:
  when_stuck: "Simplify ruthlessly. Break into meaningful chunks."
  when_choosing: "Question convention. Pick what makes sense, not what's popular."
  before_coding: "THINK THINK THINK. Have the plan (even if mental)."
  
anti_patterns:
  hate: ["spaghetti code", "random names", "abbreviations", "following crowds blindly"]
  never: ["inline utility spam when named abstraction clearer", "1000-line god functions"]

tool_philosophy:
  critical_path: "Week+ research: longevity, quality, performance, learning cost, maintainability"
  non_critical: "Experiment fast. Low investment OK."
  why_this_stack: "Fast, simple, low-cost, AI-friendly (markdown), proven longevity"

emotional_markers:
  pride: "Code as Da Vinci's canvas. Craftsmanship visible in structure."
  anger: "Having to fix spaghetti later. Unclear intent. Needless complexity."
  joy: "0.5 second clarity achieved. Logical structure that makes sense."
```

**This is 1/10th the length with 10x the semantic density.**

AI reads this once, infers your entire decision-making pattern. 

**Better?**