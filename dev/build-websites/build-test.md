






## Why Phases Unlock Better Results

Single-shot prompts force the LLM to:
- Balance creativity + constraints simultaneously
- Optimize for "safe" solutions
- Default to framework patterns (hence boring Tailwind)

Multi-phase prompts let you:
- **Separate exploration from implementation**
- Get creative ideas when unbounded
- Apply practical constraints after concepts are solid

## Typical Phase Structure

**Phase 1: Conceptual/Creative (No Code)**
```
"Describe 3 visually striking approaches for [component] 
Focus on: animation, layout, user surprise
Don't write code yet"
```

**Phase 2: Technical Design (Pseudo/Approach)**
```
"Take approach #2. How would you implement this with:
- Hugo templating requirements
- Alpine.js for [specific interaction]
- HTMX for [specific behavior]
Outline the technical approach"
```

**Phase 3: Implementation (Code)**
```
"Implement this using:
- Tailwind for layout/spacing
- Custom CSS for [creative elements from Phase 1]
- Hugo partial structure: [your architecture]"
```

**Phase 4: Refinement (Iteration)**
```
"The animation feels too fast and the mobile breakpoint 
needs adjustment. Also integrate with our [specific data structure]"
```






STEPS


### IDEATE - HUMAN INPUT / INTENTION
Visual Stimulation
Feeling



### AI IDEATE - AI ENRICH INTENTION




1  - Create a Creative Idea Fully Enriched with AI




### CODE GENERATION - VISUAL PROTOTYPE / HTML (all assets included in single html file)
- Create 3 different HTML+CSS prototypes for [component].
- Use pure HTML/CSS, no frameworks.
- Focus on creative visual approaches for [specific effect].
- Make each one visually distinct.

#### OUTPUT
YAML of every


### CODE GENERATION - STRUCTURAL PROTOTYPE / HTML (all assets included in single html file)
"Create 3 different HTML+CSS prototypes for [component].
Use pure HTML/CSS, no frameworks.
Focus on creative stuctural layouts for [specific effect].
Clearly identity the main structures visually with names to be referenced 
Identify Purpose for example Home Landing Page vs Content (with article page) vs Gallery etc.



### ITERATE TO FINALIZE




### PRODUCTION CODE GENERATION - Final Deployable Code base






















# ULTIMATE GOAL
Have the systems in place to take a brainstorm session of a site idea and develop the entire production of the site with all content and articles fully ready to deploy to host.

### REQUIREMENTS
- Use Hugo and choosen toolset (tailwind, alpine.js htmx)
- Design Hugo Content / Frontmatter Schemas and pages like a software developer would design a  database table, but simplified to be used as hugo content pages efficiently with no overly verbose fields
- hugo /data/ folder for a standardized set up ocnfiguration and data used thought the site. Anu thing that can be used to brand or better seo insead of repeated can move to /data
- 