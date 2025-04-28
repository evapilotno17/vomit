# vomit

if you're like me and prefer using llms the traditional way (copy pasting into your llm interface) rather than through cursor or whatnot, this tool is for you.

you can use this to dump your entire filesystem into a single .txt file 


## installation

on mac:

```bash
brew tap evapilotno17/vomit
brew install vomit
vomit --help
```

on windows:

```bash
kys
```

## usage

basic dump:

```bash
vomit
```

ignore certain paths (like `.git/`, `*.ipynb`, etc):

```bash
vomit --ignore .vomitignore
```

only include certain paths (inverse filter):

```bash
vomit --contains .vomitinclude
```

print a live ASCII tree of the directory structure before dumping:

```bash
vomit --tree
```

report token usage per file (and embed it into the dump file for LLMs to see):

```bash
vomit --tokens
```

full example:

```bash
vomit --ignore .vomitignore --contains .vomitinclude --tree --tokens
```

this will:
- print a live tree to stdout
- dump only files matching your `.vomitinclude` patterns
- ignore files matching `.vomitignore`
- embed a full token usage table at the top of `vomit.txt`

## testing

to test vomit inside the provided `test_directory`, run:

```bash
cd test_directory
vomit --ignore ../vomitignore.txt --contains ../vomitinclude.txt --tree --tokens
```
