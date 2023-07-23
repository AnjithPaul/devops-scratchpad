- [ ] when you need a series of **instructions to run** depending on what **files have changed**

### How to
- [ ] create file with name `Makefile` in a directory.
- [ ] use `make <target>` command to run
    - [ ] or just `make`. first target is the default target

### Syntax
```bash
target: prerequisites
<TAB> recipe
```

e.g:
```bash
say_hello:
        echo "Hello World"
```

- [ ] `say_hello` is **target** (like a function)
    - [ ] when target is just a name for the recipe instead of being a file, it's called **phony target**
- [ ] `echo "Hello World"` is **recipe**.
- [ ] **prerequisite** is a file which if modified will cause the rule to run again.
- [ ] target + prerequisites + recipe = **rule**

- [ ] suppress displaying actual command by adding an **@** prefix
    - [ ] e.g: `@echo "Hello World"`
- [ ] 