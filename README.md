<p align="center">
  <img src="https://raw.githubusercontent.com/relaxdiego/renderest/master/logo.png">
</p>

[![Build Status](https://travis-ci.org/relaxdiego/renderest.svg?branch=master)](https://travis-ci.org/relaxdiego/renderest)

This repo is the companion source code for my article on
[Templating and Testing with BASH](https://relaxdiego.com/2017/05/templating-and-testing-with-bash.html).

## Usage

Given template.txt:

```bash
Hello, {{person}}!
```

Run:

```
$ person=Bob ./render template.txt
```

And you'll see the output

```
Hello, Bob!
```

Write it to a file by redirecting stdout to a file:

```
$ person=Bob ./render template.txt > rendered.txt
```

Or declare your variables in a file and then source it. Best done inside a script:

```bash
#!/usr/bin/env bash
source ./myvalues
./render template.txt > rendered.txt
```

Error out on empty env variables:

```
$ person= ./render --no-empty template.txt > rendered.txt
```

## Testing

Just run:

```
./test-render
```
