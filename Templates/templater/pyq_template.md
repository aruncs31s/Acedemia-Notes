---
id: <% await tp.system.prompt("PYQ ID (e.g., Dec 2022 DSP)", tp.file.title) %>
tags:
  - academics
  - btech
  - <% await tp.system.prompt("Semester (s3/s5/s6/s7/s8)", "s5") %>
  - <% await tp.system.prompt("Subject (use underscores)", "digital_signal_processing") %>
  - pyq
  - <% await tp.system.prompt("Exam date/period", "dec_2022") %>
updated: <% tp.date.now("YYYY-MM-DD") %>
dg-publish: true
---

# <% tp.file.title %>

> [!toc]
> - [[#Part A]]
> - [[#Part B]]

---

## Part A

### Question 1

> [!question] <% await tp.system.prompt("Q1: State the question", "Question 1") %>

<% await tp.system.prompt("Q1 Answer", "Provide detailed answer here") %>

> [!tip] Exam Tip
> <% await tp.system.prompt("Exam tip for Q1", "What should students focus on?") %>

---

### Question 2

> [!question] <% await tp.system.prompt("Q2: State the question", "Question 2") %>

<% await tp.system.prompt("Q2 Answer", "Provide detailed answer here") %>

> [!tip] Exam Tip
> <% await tp.system.prompt("Exam tip for Q2", "What should students focus on?") %>

---

### Question 3

> [!question] <% await tp.system.prompt("Q3: State the question", "Question 3") %>

<% await tp.system.prompt("Q3 Answer", "Provide detailed answer here") %>

> [!tip] Exam Tip
> <% await tp.system.prompt("Exam tip for Q3", "What should students focus on?") %>

---

## Part B

### Long Answer 1

> [!question] <% await tp.system.prompt("Long Q1: State the question", "Long Answer Question 1") %>

**Key Points to Cover:**
- <% await tp.system.prompt("Point 1", "Key point") %>
- <% await tp.system.prompt("Point 2", "Key point") %>
- <% await tp.system.prompt("Point 3", "Key point") %>

**Detailed Answer:**

<% await tp.system.prompt("Long Q1 detailed answer", "Comprehensive answer with examples, diagrams, or formulas") %>

> [!important] Important
> <% await tp.system.prompt("Important note for long Q1", "What's the most critical aspect?") %>

---

### Long Answer 2

> [!question] <% await tp.system.prompt("Long Q2: State the question", "Long Answer Question 2") %>

**Key Points to Cover:**
- <% await tp.system.prompt("Point 1", "Key point") %>
- <% await tp.system.prompt("Point 2", "Key point") %>

**Detailed Answer:**

<% await tp.system.prompt("Long Q2 detailed answer", "Comprehensive answer with examples, diagrams, or formulas") %>

---

## Quick Reference

| Topic | Formula/Concept |
|-------|-----------------|
| <% await tp.system.prompt("Topic 1", "") %> | $$ \text{formula} $$ |
| <% await tp.system.prompt("Topic 2", "") %> | $$ \text{formula} $$ |
| <% await tp.system.prompt("Topic 3", "") %> | $$ \text{formula} $$ |

---

## Study Tips

> [!tip] Time Management
> <% await tp.system.prompt("Time management tip", "Allocate time wisely for Part A vs Part B") %>

> [!warning] Common Mistakes
> - <% await tp.system.prompt("Mistake 1", "What students often get wrong") %>
> - <% await tp.system.prompt("Mistake 2", "What students often get wrong") %>

---

_Created: <% tp.date.now("YYYY-MM-DDTHH:mm:ss") %>_
