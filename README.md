# CS340-Summer21-Notes
Lecture notes from SLU CS-340 Summer 2021

## 1. Overview

The repository contains the lecture notes for the Summer 2021 semester's instruction of CS 340: Software Engineering at St. Lawrence University. The notes are all written and curated as markdown files and formatted with the style guide specified below. 

The course consisted of 29 class dates, however some lectures where dedicated to guest lectures and reading days. These sessions **do not** contain correspoding notes in the repo. 

The Lecture Notes span the following topics in chronological order:
1. The Command-Line
2. Version Control Systems
3. Quality Assurance
4. Software Defects
5. Software Design

## 2. Style Guide

### 2.1 Naming Convention

- Name lecture files Lecture_{number}.md starting from 1 to comply with Lecture and Homework counting scheme of course site
- If Lecture number is less than 10, use a leading zero before the number
    + Ex/ Lecture_05.md
    + This ensures files are sorted in chronological lecture order preventing Lecture_10.md to be sorted before Lecture_5.md

### 2.2 Template

The Lecture_template.md file in the repository provides formatting guidelines for lecture note files. 

#### 2.2.1 Header

- Include the course information in the first line of file as a four hash subtitle (####)
- Add title, single hash (#), to each file with respective information on its lecture number, topic and date
    + Not only does this provide a consistent style, but allows for easy 'grepping' of content based on files' useful information

The header should look as follows and can be found in the template file. 

```markdown
#### CS 340 Class Notes Summer 2021
# Lecture #: Topic   
(mm/dd/2021)
```

#### 2.2.2 Titles

- Make use of double hashes for main sections (##) and add one more hash for subsections

```
## Section

### Subsection

#### Subsubsection
```

- Note: Lecture notes generally revolve around a couple main topics as opposed to many sectioned topics, so numbering headers is not necessary

#### 2.2.3 Whitespace 

- Introduce a sinlge blank line in between paragraphs and between title headings and content

#### 2.2.4 Code Blocks

- Specify language for code blocks, with the exception of pseudo-code
    + Note: some pseudo-code in the lectures is made to be similar to other languages, for example Python. In these cases the developer may specify this language as long as they are consistent within the block

### 2.3 Other Formatting

Other formatting guidelines where specified through the commit and issues history of the repository but where not stated in the template. These are more guidelines than hard rules but are recurring styles in the notes. 

#### 2.3.1 Definitions and Commands

+ Make use of Markdown code syntax for bash commands, with explanations after a colon 
    - Bolding may be used as well but this is preferred for definitions

```markdown
- `command`: explanation
    + `-flag`: explanation

- **definition**: explanation
```

#### 2.3.2 End of File Whitespace

+ Remove trailing whitespace except for single blank line after end of note content

## 3. Citations

1. Kevin Angstadt. CS-340: Software Engineering. Summer 2021. St. Lawrence University, https://myslu.stlawu.edu/~kangstadt/teaching/summer21/340/. License: Creative Commons BY-SA 4.0.