---
title: 'Extract speaker notes from PowerPoint to text'
date: '2025-10-09T11:41:43-04:00'
author: Dries
published: true
type: note
url: /extract-speaker-notes-from-powerpoint-to-text
id: 5891
---

When working on presentations, I like to extract my speaker notes to review the flow and turn them into blog posts. I'm doing this right now for my DrupalCon Vienna talk. 

I used to do this manually, but with presentations often having 100+ slides, it gets tedious and isn't very repeatable. So I ended up automating this with a Python script.

Since I use Apple Keynote or Google Slides rather than Microsoft PowerPoint, I first export my presentations to PowerPoint format, then run my Python script.

If you've ever needed to pull speaker notes from a presentation for review, editing or blogging, here is my script and how to use it.

### Speaker notes extractor script

Save this code as `powerpoint-to-text.py`:

```python
#!/usr/bin/env python3
"""Extract speaker notes from PowerPoint presentations to text files."""

import sys
from pathlib import Path
from pptx import Presentation

def extract_speaker_notes(pptx_path: Path) -> tuple[str, int]:
    presentation = Presentation(pptx_path)
    notes_text = []

    for i, slide in enumerate(presentation.slides, 1):
        if slide.notes_slide and slide.notes_slide.notes_text_frame:
            notes = slide.notes_slide.notes_text_frame.text.strip()
            if notes:
                notes_text.append(f"=== Slide {i} ===\n{notes}\n")

    return "\n".join(notes_text), len(notes_text)

def main():
    if len(sys.argv) != 2:
        print("Usage: python powerpoint-to-text.py presentation.pptx")
        sys.exit(1)

    input_path = Path(sys.argv[1])

    if not input_path.exists():
        print(f"Error: File '{input_path}' not found")
        sys.exit(1)

    if input_path.suffix.lower() != '.pptx':
        print(f"Warning: '{input_path}' may not be a PowerPoint file")

    try:
        notes_text, notes_count = extract_speaker_notes(input_path)
    except Exception as e:
        print(f"Error reading presentation: {e}")
        sys.exit(1)

    output_path = input_path.with_suffix('.txt')
    output_path.write_text(notes_text, encoding='utf-8')

    print(f"Extracted {notes_count} slides with notes to {output_path}")

if __name__ == "__main__":
    main()
```

The script uses the `python-pptx` library to read PowerPoint files. This library understands the internal structure of .pptx files (which are zip archives containing XML). It provides a clean Python interface to access slides and their speaker notes. The script loops through each slide, checks if it has notes, and writes them to a text file.

### Usage

I like to use [uv](https://github.com/astral-sh/uv) to run Python code. `uv` is a fast, modern Python package manager that handles dependencies automatically:

```bash
$ uv run --with python-pptx powerpoint-to-text.py your-presentation.pptx
```

This saves a `.txt` file with your notes in the same directory as the input file, not the current directory or desktop.

The text file contains:

```bash
=== Slide 1 ===
Speaker notes from slide 1 ...

=== Slide 3 ===
Speaker notes from slide 3 ...
```

Only slides with speaker notes are included.
