# The Great Unlearning Pattern Library

## Overview

This library documents emerging patterns for LLM-assisted software development. These patterns represent new approaches to software design and development that optimize for collaboration between humans and AI language models.

> **🧪 Experimental Notice**: These patterns are emerging from practical experience and community observations. They are not fixed rules but rather evolving guidelines that may change as LLM capabilities and tools evolve.

## Core Concepts

Before diving into specific patterns, it's important to understand the key principles that drive this new approach:

1. **Context Over Reuse**: Prioritize clear, self-contained context over traditional DRY principles
2. **Natural Language First**: Design for conversation with AI assistants
3. **Explicit Over Implicit**: Make intentions and dependencies clear
4. **Self-Containment**: Each component should include everything needed to understand and recreate it

## Pattern Categories

### 1. Architectural Patterns

#### Prompt-Oriented Architecture (POA)
**Context**: Traditional architectures organize code around technical concepts, which can be difficult to modify through natural language interaction.

**Solution**: Structure applications around natural language descriptions and common prompt patterns.

```
feature/
├── intent.md         # Purpose and requirements
├── implementation/   # Actual code
├── tests/           # Self-contained tests
└── prompts/         # Common modification scenarios
```

**Benefits**:
- Easier LLM understanding and modification
- Clear documentation integrated with code
- Natural alignment with human-AI collaboration

#### Context Window Optimization (CWO)
**Context**: LLMs have limited context windows, making it difficult to understand code spread across many files.

**Solution**: Organize code to fit within typical LLM context windows.

```
feature/
├── dependencies.md           # Explicit dependencies
├── core-logic/              # Fits in one context window
├── extensions/              # Each fits in one window
└── integration-points.md    # Connection documentation
```

**Benefits**:
- Better LLM comprehension
- Faster, more accurate modifications
- Clearer component boundaries

### 2. Implementation Patterns

#### Self-Regenerating Modules (SRM)
**Context**: Code often needs to be regenerated or heavily modified by LLMs.

**Solution**: Design modules to include all context needed for regeneration.

**Key Elements**:
- Complete business context
- Clear contracts and dependencies
- Self-contained validation rules
- Explicit boundaries

#### Context-First Design (CFD)
**Context**: Traditional DRY principles can make code harder for LLMs to understand holistically.

**Solution**: Prioritize complete context over code reuse.

**Implementation**:
```
feature/
├── context.md       # Complete business context
├── implementation/  # Self-contained code
├── tests/          # Context-specific tests
└── dependencies/   # Explicit dependencies
```

### 3. Documentation Patterns

#### LLM-Friendly Documentation Pattern (LFDP)
**Context**: Traditional documentation focuses on human readers and often lacks context needed by LLMs.

**Solution**: Create documentation that serves both human and AI readers.

**Components**:
- Natural language descriptions
- Code examples
- Common modification scenarios
- Test cases
- Integration points

#### Conversational Interface Pattern (CIP)
**Context**: Code modifications often happen through natural language interaction.

**Solution**: Design components to be modified through conversation.

**Features**:
- Clear modification boundaries
- Natural language validation rules
- Self-contained business logic

### 4. Process Patterns

#### AI-Assisted Versioning
**Context**: Traditional commit messages and change documentation don't provide enough context for LLMs.

**Solution**: Structure version control for AI comprehension.

**Implementation**:
- Detailed commit messages with clear context
- Change documentation in natural language
- Impact descriptions for each change

#### Prompt-Driven Testing (PDT)
**Context**: Traditional test cases can be difficult for LLMs to understand and modify.

**Solution**: Design tests to be AI-generateable and modifiable.

**Characteristics**:
- Natural language scenarios
- Self-contained test contexts
- Clear test boundaries
- AI-friendly assertions

## Implementation Examples

See our [example project](https://github.com/greatunlearning/example-project) for practical implementations of these patterns.

## Pattern Evolution

### Contributing New Patterns

1. Create an issue describing the pattern
2. Include:
   - Context where it's useful
   - Problem it solves
   - Implementation examples
   - Benefits and tradeoffs

### Pattern Lifecycle

Patterns go through these stages:
1. **Emerging**: Initial observation and documentation
2. **Experimental**: Being tested in real projects
3. **Established**: Proven useful in multiple contexts
4. **Evolving**: Being modified based on new tools/capabilities
5. **Deprecated**: No longer relevant due to tool evolution

## Anti-Patterns

### Over-Abstraction
❌ Creating deep inheritance hierarchies
✅ Use flatter, more explicit structures

### Context Fragmentation
❌ Spreading related code across many files
✅ Keep related code together within context windows

### Implicit Dependencies
❌ Hiding dependencies in abstractions
✅ Make dependencies explicit and self-contained

## Best Practices

1. **Documentation**
   - Write for both humans and AI
   - Include context and purpose
   - Use clear, natural language

2. **Code Organization**
   - Keep related code together
   - Make boundaries explicit
   - Include necessary context

3. **Testing**
   - Write self-contained tests
   - Include test context
   - Make assertions clear

## Resources

- [The Great Unlearning Article Series](https://www.linkedin.com/pulse/great-unlearning-continues-rethinking-software-llm-age-hannes-lehmann-jxjie)
- [Example Implementations](https://github.com/greatunlearning/example-project)
- [Community Discussions](https://github.com/greatunlearning/discussions)

## Contributing

We welcome contributions! See our [contribution guidelines](CONTRIBUTING.md) for details on how to:
- Propose new patterns
- Share implementation experiences
- Suggest pattern improvements
- Report pattern issues

## License

This pattern library is licensed under [MIT License](LICENSE) unless otherwise specified.

---

*Remember: These patterns are evolving guidelines, not strict rules. Use them as a starting point and adapt them to your specific needs and context.*
