


[SkillName]           # Semantic identifier
description:          # What cognitive capability this provides
intent:              # Semantic category/purpose (taxonomy)
instructions:        # The actual cognitive content/prompt text
context_needs:       # What semantic context it requires
cognitive_weight:    # How much "thinking" it demands
combines_with:       # What other semantic bits it works well with




SEMANTIC_COMPONENT := {
  MEANING     # The cognitive instruction/knowledge it carries
  INTENT      # Why this meaning exists (its purpose)  
  BOUNDARY    # Where this meaning starts and ends
}
```

That's it. Everything else is metadata.

---

### **THE 5 AXIOMS**

**Axiom 1: SEMANTIC ATOMICITY**
- A semantic component cannot be decomposed without losing its meaning
- Like a word that becomes meaningless letters when split

**Axiom 2: COGNITIVE EFFECTUALITY** 
- It MUST change how the model thinks/responds
- If it has no cognitive effect, it's not a component

**Axiom 3: CONTEXT INDEPENDENCE**
- The component's MEANING remains constant
- Its APPLICATION may vary by context, but its core semantic content doesn't change

**Axiom 4: COMPOSABILITY THROUGH MEANING**
- Components combine based on semantic compatibility, not syntactic rules
- Like ideas that "make sense together" vs words that are grammatically correct

**Axiom 5: INTENT PRESERVATION**
- A component's purpose must be preserved through all compositions
- You cannot use it in a way that violates its intent

---

### **THE 7 PRINCIPLES**

**Principle 1: Semantic Completeness**
```
Each component must contain sufficient meaning to achieve its intent alone
Example: "Be concise" is complete. "Be" is not.
```

**Principle 2: Single Purpose**
```
One intent per component (Unix philosophy for semantics)
NOT: "Be concise and friendly"
YES: "Be concise" + "Be friendly"
```

**Principle 3: Effect Determinism**
```
Given same context, produces predictable cognitive modification
Not random, not ambiguous in its effect
```

**Principle 4: Semantic Density**
```
Maximum meaning in minimum expression
Every word carries weight
No fluff, no redundancy
```

**Principle 5: Boundary Clarity**
```
Clear start and end to the semantic instruction
Self-contained thought unit
No bleeding into adjacent concepts
```

**Principle 6: Intent Alignment**
```
The meaning must serve the intent directly
No side effects, no hidden purposes
WYSIWYG for cognitive instructions
```

**Principle 7: Composable Neutrality**
```
Doesn't force specific compositions
Plays well with others by default
No semantic antibodies




[SEMANTIC_GENE]
│
├─ MEANING_SEQUENCE: "The actual semantic instruction"
│   └─ Must be: Complete, Unambiguous, Actionable
│
├─ INTENT_MARKER: "category.subcategory.purpose"
│   └─ Taxonomic position in semantic space
│
└─ BOUNDARY_MARKERS:
    ├─ BEGIN: Where this semantic unit starts
    └─ END: Where this semantic unit ends







[Be]          # Intent: existence.assert
[Think]       # Intent: cognition.activate  
[Focus]       # Intent: attention.narrow
[Expand]      # Intent: scope.broaden
[Connect]     # Intent: relationship.establish


