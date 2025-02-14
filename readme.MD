# Introduction

## Globals

- C: control
  - A stack of commands that still need to be executed
  - Commands could either be the nodes of the syntax tree (const, seq, etc.) or instructions
- S: stash
  - An array that stores intermediate results
- E: environment
  - The environments of the program

## Execution Flow

- Starting point

```js
execute(program)
// Parses the program into JSON and is added to C
// Initialises S to an empty array
// Initialsed to the `global_environment`

// Keeps looping while there is a control to execute
```

- Handling Commands

```js
// Get the command to be executed
// A command consists of a tag and possibly other fields depending on the tag
// Other fields include stmts (for seq), sym and expr (for const) etc.
const cmd = C.pop()
if (microcode.hasOwnProperty(cmd.tag)) {
    microcode[cmd.tag](cmd);
}
```
