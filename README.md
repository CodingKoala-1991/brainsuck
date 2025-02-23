## 说明
fork 自 liancheng 大神，自行去修改去理解一下这个小项目

## Brainsuck

Brainsuck is an optimizing compiler prototype for the Brainfuck programming language.  It's written in Scala using the same technologies used in Spark SQL's Catalyst optimizer.  It's minimum, and only consists of 292 lines of code (test code not included).  This project is designed for [my QCon Beijing 2015 talk][1].

## How to build

```bash
$ sbt stage
```

## Run

Use the following command line to run the Hanoi tower example:

```bash
JAVA_OPTS=-Xss8m ./target/universal/stage/bin/brainsuck scripts/hanoi.b -O 2
```

The `-O` flag is used to specify optimization level (0, 1, or 2). `-O 0` disables all optimizations.

Brainsuck uses recursion extensively for conciseness.  That's why you need to specify stack size to avoid stack overflow.  These recursions can be easily removed, but this makes the codebase unnecessarily bloated.  Anyway, this is only a demo for a talk :^)

## Acknowledgement

This project is inspired by [brainfuck optimization strategies][2] authored by Mats Linander.

## Licence

MIT

[1]: https://www.slideshare.net/liancheng/dive-into-catalyst
[2]: http://calmerthanyouare.org/2015/01/07/optimizing-brainfuck.html
