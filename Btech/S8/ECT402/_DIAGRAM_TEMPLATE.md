---
id: Diagram Templates
tags:
  - template
  - mermaid
dg-publish: false
---

# Mermaid Diagram Templates

## Standard Colors

| Element | Color Code | Use For |
|---------|------------|---------|
| Primary | `#4ecdc4` | Main concepts |
| Secondary | `#ff6b6b` | Important/Warning |
| Highlight | `#f0932b` | Key points |
| Background | `#f7f7f7` | Boxes |

## Flowchart Template

```mermaid
flowchart TD
    A[Start] --> B[Process]
    B --> C{Decision}
    C -->|Yes| D[Output 1]
    C -->|No| E[Output 2]

    style A fill:#4ecdc4,color:#000
    style C fill:#f0932b,color:#000
    style D fill:#c8e6c9
    style E fill:#ffcdd2
```

## Mindmap Template

```mermaid
mindmap
  root((Main Topic))
    SubTopic1
      Point1
      Point2
    SubTopic2
      Point3
      Point4
```

## Classification Diagram

```mermaid
graph TD
    Main[Main Category] --> Sub1[Sub Category 1]
    Main --> Sub2[Sub Category 2]

    Sub1 --> Item1[Item A]
    Sub1 --> Item2[Item B]

    Sub2 --> Item3[Item C]
    Sub2 --> Item4[Item D]

    style Main fill:#4ecdc4,color:#000
    style Sub1 fill:#ff6b6b,color:#000
    style Sub2 fill:#ff6b6b,color:#000
```

## Comparison Table

```mermaid
graph LR
    A[Aspect 1] --> B[Result 1]
    C[Aspect 2] --> D[Result 2]

    style A fill:#e1f5fe
    style C fill:#e1f5fe
```

## Gantt Chart Template

```mermaid
gantt
    title Activity Timeline
    dateFormat HH:mm
    axisFormat %H:%M

    section Phase 1
    Task A :a1, 00:00, 30m
    Task B :a2, after a1, 45m

    section Phase 2
    Task C :c1, after a2, 30m
```

---

## Quick Copy-Paste Examples

### For Important Formulas
```markdown
$$Formula$$ 
```

### For Callouts
```markdown
> [!tip] **Title**
> Content

> [!callout] **Warning**
> Content
```

### For Tables
```markdown
| Header 1 | Header 2 |
|----------|------------|
| Value 1 | Value 2    |
```

### For Links
```markdown
[[Module X/Topic Name|Display Text]]
```