# reel
[WIP] Read Eval Edit Loop: A REPL that is a text editor

A common REPL-driven workflow in Clojure is to use the REPL inside your editor. This is just the opposite - we put the text editor in your REPL. Think [Rebel readline](https://github.com/bhauman/rebel-readline) with the ability to save files.

Why? For the times when we're doing something in the terminal and then need to create/edit a file, and would rather not have to stop and open a text editor. For simple cases, you can do this:

```bash
$ cat > myfile
my text
```

This can be useful if you are demonstrating something in the shell and want to present a clean sequence of commands. No clearing of the screen, nothing disrupting the continuity of your workflow. But then you have no multiline editing so it's only useful for creating one-off files. I wanted something in between a _line editor_, like [ed](https://en.wikipedia.org/wiki/Ed_(text_editor)), and a full _screen editor_ like vi.
