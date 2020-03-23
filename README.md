# reel
[WIP] Read Eval Edit Loop: A REPL that is also a text editor

Nobody ordered this, and I have no idea if it will even work. When I attempt to explain it, I'll likely receive blank stares and perhaps a "Why?", so bear with me. To fully appreciate this, we're gonna have to take a brief detour to learn a little about the history of text editors.

Once upon a time, there were only _line editors_, like
[ed](https://en.wikipedia.org/wiki/Ed_(text_editor)). Life was simple, though rather annoying, but the people carried on.

The boost in productivity enabled by _screen editors_ starting with vi is felt quite deeply at the times when this ability is not present, like when entering code into a REPL. So we started making better REPLs with better readlines and command history. [Rebel readline](https://github.com/bhauman/rebel-readline) took it much further by providing multiline editing, autocompletion, syntax highlighting and other features only previously found in text editors and IDEs, right there in your command-line. A very novel idea!

We're about to bring this to its thrilling conclusion, but first, a brief interlude, back to our humble line-editor. Imagine trying to do actual work by only having access to one line of the file at a time. I wouldn't wish that experience upon anyone. But along the switch to screen editors, I believe that we may have lost something.

Say you're doing something in your shell, you type a couple of commands. Then what? You need to make a text file. So you open up Vim. Or Emacs. Or Nano. What happens?

It opens up in your terminal, after first clearing the screen, disrupting the continuity of what you were doing. You cannot refer back to your command history until you exit your editor, at which point you can no longer see your text file! Oh, the agony! You'll be forced to open up _another_ window!

You _could_, on the other hand, use the `cat` command, directing STDIN into a file, and achieve a much cleaner workflow. Type in commands, type in your file, type in commands, and it's all right there in a nice linear view. But then you can't edit it at all! No way to do any serious work.

We missed something cool, and I want to make it. I'm going to make a text editor that is _invisible_. Nothing opens up, you're just doing your thing in your shell, then edit your file, without ever leaving the command-line, but you are actually now within an invisible multiline editor.

Bruce Hauman gave us a taste of this superpower with Rebel Readline, by putting elements of text editors into a REPL. But you're still disconnected from your source code, sooner or later you're going to have to awkwardly copy and paste it into something else.

Introducing **REEL**, the Read Eval Edit Loop.
