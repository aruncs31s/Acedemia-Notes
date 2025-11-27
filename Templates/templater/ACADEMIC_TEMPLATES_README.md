# Templater Templates for Academic Notes

This folder contains Templater templates designed specifically for your Obsidian academic note-taking workflow. These templates follow the standardized pattern you've established across your notes.

## 📋 Available Templates

### 1. **academic_note.md** - General Academic Topic Notes
**Use for:** Individual topics, chapters, or lesson content

**Features:**
- Structured frontmatter with tags
- Table of Contents
- Overview section
- Key Concepts (multi-concept support)
- Examples section
- Formulas/Definitions table
- Summary callout
- Related Links

**When to use:**
- DSP topics (Convolution, FFT, Filters, etc.)
- Communication System concepts
- Individual module deep-dives
- Any single-concept exploration

---

### 2. **pyq_template.md** - Previous Year Questions (PYQ)
**Use for:** Exam question compilations with solutions

**Features:**
- Exam metadata in frontmatter
- Part A (short answer) questions
- Part B (long answer) questions
- Question-Answer callout pairs
- Exam tips for each question
- Quick reference table
- Time management tips
- Common mistakes callout

**When to use:**
- Dec 2022, May 2023, etc. exam papers
- Question compilation by semester
- Exam preparation notes

---

### 3. **module_template.md** - Module/Chapter Deep-Dive
**Use for:** Complete modules or chapters with comprehensive coverage

**Features:**
- Learning objectives
- Core concepts with definitions
- Mathematical representations
- Properties lists
- Worked examples (multiple)
- Key Formulas Reference table
- Comparison table for alternative methods
- Common Mistakes section
- Summary points
- Practice questions checklist
- Related Topics

**When to use:**
- Module 1, 2, 3, 4 content
- Complete chapter notes
- Comprehensive topic review

---

## 🚀 How to Use

### In Obsidian:

1. **Create a new note** using the template:
   - Press `Cmd + P` (Mac) → "Templater: Create new note from template"
   - Select the desired template (`academic_note`, `pyq_template`, or `module_template`)
   - Fill in the interactive prompts

2. **Interactive Prompts:**
   - The templates use `tp.system.prompt()` to ask you questions
   - Answer each prompt to customize your note
   - Press Enter to move to the next prompt
   - You can leave prompts blank if not applicable

3. **Auto-filled Fields:**
   - `<% tp.file.title %>` - Uses your note's filename as title
   - `<% tp.date.now() %>` - Inserts current date/time

### Editing After Creation:

- Replace `<% ... %>` placeholders manually if needed
- Add mermaid diagrams for visual explanations
- Include images using `![[image-name.png]]`
- Add more examples, sections, or content as needed

---

## 📝 Frontmatter Convention

All templates follow this tag structure:

```yaml
tags:
  - academics          # Always include
  - btech              # Degree level
  - s5                 # Semester (s3, s5, s6, s7, s8)
  - digital_signal_processing  # Subject (use underscores)
  - module_1           # (Optional) Topic/module
  - pyq                # (Optional) For exam papers
  - dec_2022           # (Optional) Exam date
```

**Tag Examples:**
- DSP Module: `academics`, `btech`, `s5`, `digital_signal_processing`, `module_1`
- PYQ Exam: `academics`, `btech`, `s5`, `digital_signal_processing`, `pyq`, `dec_2022`
- Communication System: `academics`, `btech`, `s6`, `analog_digital_communication`, `module_2`

---

## ✨ Best Practices

### ✅ DO:
- Use consistent subject names across all notes
- Fill in exam tips and common mistakes for better retention
- Link related topics using `[[Link]]` syntax
- Use formulas in LaTeX: `$...$` for inline, `$$...$$` for display
- Add mermaid diagrams for complex concepts
- Keep examples progressively harder (simple → complex)

### ❌ DON'T:
- Edit the frontmatter structure (maintain consistency)
- Remove the TOC callout (helps with Obsidian navigation)
- Skip exam tips (crucial for exam preparation)
- Mix different template styles in one file

---

## 🔄 Customization

### To modify existing templates:
1. Edit the `.md` file directly
2. Update placeholders as needed
3. Keep the frontmatter and callout structure intact

### Common customizations:
- Add more sections (e.g., History, Applications)
- Increase number of examples
- Add more comparison tables
- Include difficulty ratings for questions

---

## 📚 Related Files

- **Main templates directory:** `/Templates/templater/`
- **Callouts reference:** `/Templates/callouts/multi_callouts.md`
- **Obsidian vault settings:** Configure Templater plugin to use this folder

---

## 🎯 Quick Start Example

Creating a new DSP note:

1. Create new file: `Convolution.md`
2. Run Templater → Select `academic_note.md`
3. Fill prompts:
   - ID: "Convolution"
   - Tags: `s5`, `digital_signal_processing`
   - Subject: `digital_signal_processing`
   - Concept 1: "Linear Convolution"
   - Concept 2: "Circular Convolution"
   - Add example and formulas
4. Done! Note is ready with structured format

---

**Created:** November 2025
**Last Updated:** <% tp.date.now("YYYY-MM-DD") %>
