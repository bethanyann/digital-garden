---
sidebar_position: 1
id: tech-link
title: Tech Links
---

A collection of links that I can't seem to keep organized any other way

<!-- 
### Summary
A concise overview of a small utility: reading a file, transforming contents, and writing output.

## Prerequisites
- Git
- Node.js >= 16 (or any runtime that can run the snippet)
- Basic familiarity with command line

## Example: Node.js file transformer
Reads a text file, converts lines to uppercase, writes to an output file.

```js
// transform.js
import { readFileSync, writeFileSync } from 'fs';

const input = process.argv[2] || 'input.txt';
const output = process.argv[3] || 'output.txt';

const content = readFileSync(input, 'utf8');
const transformed = content
    .split(/\r?\n/)
    .map(line => line.trim().toUpperCase())
    .join('\n');

writeFileSync(output, transformed, 'utf8');
console.log(`Wrote ${output} (${transformed.length} bytes)`);
```

Run:
```bash
node transform.js docs/notes.txt docs/notes.UPPER.txt
```

## Tips
- Keep input/output paths relative to the project root.
- Add small tests to verify behavior for empty files and large inputs.
- Consider streaming for very large files to reduce memory usage.

## Further ideas
- Add CLI flags for encoding, trim behavior, and a dry-run mode.
- Add unit tests (Jest / Mocha) and a CI workflow to validate changes. -->

<!-- End of page -->