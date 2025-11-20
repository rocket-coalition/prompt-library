website_blueprint:
  brand:
    primary_name: "Rocket Personas"
    secondary_name: "Rocket Websites"
    founder_character: "Ray"
    positioning_one_liner: >
      "We turn company identity into a version-controlled Blueprint DNA,
      then build persona packages that generate aligned content at scale."

  global_voice_rules:
    primary_voice: >
      Clear, confident, outcome-focused, founder-led. Enterprise-credible.
    secondary_flavor: >
      Ray’s nerd-mythos appears in sidebars, footers, and stories,
      not in core sales copy.
    banned_tones:
      - "generic AI voice"
      - "mystical hype in core pitch"
      - "vague promises without outcomes"

  site_map:
    - slug: "/"
      page_name: "Home"
      purpose: >
        Instant clarity + credibility + primary CTA to Blueprint DNA setup.
      voice: "Professional, crisp, slight Ray edge."
      sections:
        - id: "hero"
          heading: "Your company’s identity, turned into an engine."
          subheading: >
            Blueprint DNA is a version-controlled identity file that makes
            every AI-generated message sound unmistakably like you—across
            marketing, product, sales, and leadership.
          primary_cta:
            label: "Build My Blueprint DNA"
            link: "/start/"
          secondary_cta:
            label: "See how it works →"
            link: "/how-it-works/"
          trust_line: "Repo-first. Enterprise-ready. Ownership stays with you."

        - id: "problem_insight"
          heading: "The AI era didn’t break content. It exposed identity."
          body: >
            AI can produce unlimited content. But without a clarified identity
            layer, that content becomes generic, fragmented, and untrustworthy.
            Most companies are scaling volume while their voice drifts.
            We fix the root cause: identity first, content second.

        - id: "what_we_do_cards"
          heading: "What we do"
          cards:
            - title: "Blueprint DNA"
              text: >
                We extract and codify your mission, voice, values, and reasoning
                patterns into a structured identity blueprint.
            - title: "Persona Packages"
              text: >
                Specialized personas inherit that DNA and generate aligned content
                for every role you need.
            - title: "Repo Delivery"
              text: >
                Everything lands in your repo—versioned, governed, deployable anywhere.

        - id: "founder_outcomes"
          heading: "What founders get"
          bullets:
            - "Content that scales without losing your voice"
            - "A single source of truth for messaging"
            - "Personas that work like full-time specialists"
            - "SEO authority built on real identity"
            - "Total ownership inside your repo"

        - id: "ray_sidebar"
          heading: "Ray, founder note"
          body: >
            “I don’t sell prompts. I sell the thing prompts need to work: identity.
            Give me your intention, I’ll drop aligned content into your repo.
            Simple system. Massive leverage.”

        - id: "closing_cta"
          heading: "Write your identity once. Scale your voice forever."
          primary_cta:
            label: "Start Blueprint DNA setup"
            link: "/start/"

    - slug: "/blueprint-dna/"
      page_name: "Blueprint DNA"
      purpose: >
        Explain the core product, why it matters in the AI era,
        and how it powers everything downstream.
      voice: "Authoritative thought leadership."
      sections:
        - id: "intro"
          heading: "Blueprint DNA is the soul of your company—written down."
          body: >
            Blueprint DNA is a structured identity file that defines how your
            company thinks, speaks, and positions itself. Every persona and every
            content output inherits from it. In an AI-first world, Blueprint DNA
            keeps you coherent, credible, and distinct.

        - id: "includes"
          heading: "What Blueprint DNA includes"
          bullets:
            - "Mission + strategic intent"
            - "Voice and tone rules"
            - "Core narrative and worldview"
            - "Semantic guardrails for AI"
            - "Entity map for topical authority"
            - "Governance + version history"

        - id: "why_now"
          heading: "AI content is flooding the web. Identity is the moat."
          body: >
            Within a few years, most public content will be AI-generated.
            The winners won’t be the loudest—they’ll be the clearest.
            Blueprint DNA ensures your AI output remains helpful, human-true,
            and unmistakably yours.

        - id: "power_flow"
          heading: "How Blueprint DNA powers everything"
          flow: "Intention → Blueprint DNA → Personas → Content Blueprints → Repo → Publish"

        - id: "cta"
          heading: "Want to see your DNA drafted?"
          primary_cta:
            label: "Book Blueprint DNA setup"
            link: "/start/"

    - slug: "/persona-packages/"
      page_name: "Persona Packages"
      purpose: >
        Show what personas are, how they inherit DNA,
        and how suites scale like teams.
      voice: "Practical + exciting."
      sections:
        - id: "intro"
          heading: "Personas are specialized minds that inherit your DNA."
          body: >
            Once Blueprint DNA exists, we build persona packages for the roles
            your business needs—writer, strategist, analyst, storyteller,
            community host, executive voice, and more. Each persona is trained
            on your identity, then tuned to a specialty.

        - id: "examples"
          heading: "Example personas"
          cards:
            - title: "The Founder Voice"
              text: "Letters, vision posts, investor narratives."
            - title: "The SEO Architect"
              text: "Long-form cluster content, semantic routing."
            - title: "The Community Host"
              text: "Threads, replies, live Q&A style content."
            - title: "The Case Study Builder"
              text: "Transformation narratives and proof assets."
            - title: "The Product Narrator"
              text: "Release notes, landing pages, docs."

        - id: "suites"
          heading: "Persona Suites scale like teams."
          body: >
            Start with one persona or expand into a suite that runs your content
            flywheel across every channel.

        - id: "cta"
          primary_cta:
            label: "Build my persona suite →"
            link: "/start/"

    - slug: "/how-it-works/"
      page_name: "How It Works"
      purpose: >
        De-mystify the pipeline from intention to repo to publishing.
      voice: "Simple, technical-but-clear."
      sections:
        - id: "steps"
          heading: "From intention to publish in one loop."
          steps:
            - title: "Setup Blueprint DNA"
              text: "Capture your mission, voice, and strategic worldview."
            - title: "Design Personas"
              text: "Build role-specific personas that inherit your DNA."
            - title: "Generate by Intention"
              text: "Route each request to the right pillar and cluster."
            - title: "Produce Hugo Files"
              text: "Output complete Hugo content with SEO front matter."
            - title: "Commit to Your Repo"
              text: "Content lands versioned, portable, and owned by you."

        - id: "reassurance"
          body: "No new platform to learn. No CMS lock-in. Your repo is the hub."

    - slug: "/case-studies/"
      page_name: "Case Studies"
      purpose: "Proof of transformation and ROI."
      voice: "Outcome-first, before/after clarity."
      sections:
        - id: "intro"
          heading: "What changes when identity becomes infrastructure."
          body: >
            These transformations show what happens after Blueprint DNA and
            persona suites align a company’s voice across every channel.

        - id: "case_study_template"
          heading: "Case study structure (repeat per story)"
          template:
            title_format: "[Company type] → [Outcome]"
            before: "Fragmented voice, generic AI content, slow throughput."
            blueprint_dna: "Identity codified + semantic rules installed."
            persona_suite: "Roles built to match company needs."
            after: "Coherent positioning, consistent output, measurable SEO lift."
            quote: "[Short founder reaction]"
            cta_label: "See the blueprint →"
            cta_link: "/start/"

    - slug: "/pricing/"
      page_name: "Pricing / Engagement"
      purpose: "Outcome-based packages and upgrade path."
      voice: "Calm, enterprise-friendly."
      sections:
        - id: "intro"
          heading: "Pricing is outcome-based, not artifact-based."
          body: >
            We don’t sell templates. We build company-specific identity systems
            and persona engines that replace fragmented content operations.

        - id: "packages"
          heading: "Engagement levels"
          packages:
            - name: "Blueprint DNA Setup (Start Here)"
              includes:
                - "Identity extraction workshop"
                - "Blueprint DNA file committed to your repo"
                - "First SEO/content cluster plan"
                - "One starter persona"
              cta:
                label: "Start DNA setup"
                link: "/start/"

            - name: "Persona Package Add-ons"
              includes:
                - "Role-specific personas"
                - "Prompt hierarchy + examples"
                - "Output automation rules"
              cta:
                label: "Add personas"
                link: "/start/"

            - name: "Persona Suite (Enterprise Engine)"
              includes:
                - "Multi-persona architecture"
                - "Full SEO cluster flywheel"
                - "Governance + evolution support"
              cta:
                label: "Build suite"
                link: "/start/"

        - id: "footer_note"
          body: "Exact scope scales with company size, goals, and existing assets."

    - slug: "/about/"
      page_name: "About"
      purpose: "Trust + founder story + mission."
      voice: "Human + credible; Ray more present."
      sections:
        - id: "company_intro"
          heading: "We’re building the identity layer for AI communication."
          body: >
            Rocket Personas exists because content is no longer scarce—coherent
            identity is. We watched companies scale AI content while their voice
            drifted and teams contradicted each other. Our answer: turn identity
            into a structured, version-controlled blueprint so personas can
            generate aligned content forever.

        - id: "ray_story"
          heading: "Ray’s note"
          body: >
            “I’m Ray. I’m the founder. I’m the guy who stays up too late writing
            prompts and thinking about why companies sound fake online.
            The fix isn’t magic prompts. It’s identity you can version.
            Once you write that DNA down, the rest is just intention in,
            content out.”

        - id: "mission"
          heading: "Mission"
          body: "Help companies scale AI content without losing their soul."

    - slug: "/blog/"
      page_name: "Blog / Library"
      purpose: "SEO flywheel hub + pillar navigation."
      voice: "Varies by pillar."
      sections:
        - id: "header"
          heading: "The Blueprint Library"
          subheading: >
            Daily posts across our pillars: Blueprint DNA, personas, Ray’s world,
            real transformations, and practical strategy.
        - id: "pillar_nav"
          buttons:
            - { label: "Blueprint Evangelism", link: "/pillars/blueprint-evangelism/" }
            - { label: "Ray’s World", link: "/pillars/rays-world/" }
            - { label: "Case Studies", link: "/pillars/case-studies/" }
            - { label: "Practical Strategy", link: "/pillars/practical-strategy/" }
            - { label: "SEO Deep Dives", link: "/pillars/seo-deep-dives/" }

    - slug: "/faq/"
      page_name: "FAQ"
      purpose: "Crush objections; clarify value."
      voice: "Straightforward, slightly blunt."
      sections:
        - id: "faq_list"
          items:
            - q: "Isn’t this just selling prompts?"
              a: >
                No. Prompts are cheap. Identity is not.
                We build a company-specific Blueprint DNA, persona stack,
                and governed production pipeline. Your repo holds the assets
                so you own them forever.
            - q: "Why put everything in a repo?"
              a: >
                Repos give version control, history, governance, portability,
                and zero-hosting simplicity. CMS tools store pages; repos store truth.
            - q: "Can my team use this?"
              a: >
                Yes. Blueprint DNA becomes a shared identity reference for humans
                and AI across departments.
            - q: "What do we get first?"
              a: "Blueprint DNA setup. Everything builds from that."

    - slug: "/start/"
      page_name: "Start / Contact"
      purpose: "Frictionless entry into Blueprint DNA setup."
      voice: "Short, directive."
      sections:
        - id: "intro"
          heading: "Start with Blueprint DNA."
          body: >
            Tell us what you’re building, where you’re headed,
            and how you want to sound. We’ll draft your Blueprint DNA
            and deploy it into your repo.
        - id: "form"
          fields:
            - "Name"
            - "Company"
            - "Website"
            - "What you’re trying to achieve"
            - "Repo link (optional)"
          submit_cta:
            label: "Send intention →"
            link: "/start/"

    - slug: "/trust/"
      page_name: "Trust, Security & Ownership"
      purpose: "Explain repo ownership, governance, privacy."
      voice: "Enterprise-safe, reassuring."
      sections:
        - id: "intro"
          heading: "You own the DNA. We just build it."
          body: >
            All Blueprints and Personas are committed into your repo.
            You control access, version history, deployment, and evolution.
            We don’t lock your identity into our platform.
        - id: "bullets"
          bullets:
            - "Repo-first ownership"
            - "No CMS lock-in"
            - "Full version history"
            - "Secure, portable assets"
            - "Enterprise-safe governance"

    - slug: "/terms/"
      page_name: "Terms"
      purpose: "Standard legal compliance."
      voice: "Legal."
      sections:
        - id: "placeholder"
          body: "Terms of service content goes here."

    - slug: "/privacy/"
      page_name: "Privacy"
      purpose: "Standard legal compliance."
      voice: "Legal."
      sections:
        - id: "placeholder"
          body: "Privacy policy content goes here."
