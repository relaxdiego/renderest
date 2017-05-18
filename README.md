# renderest

Because it's better than a renderer! Why do I think it's better than
all other renderers out there, you ask? How dare you ask me that question!
Move along now!

This repo is the companion source code for my article at https://relaxdiego.com/2017/05/templating-and-testing-with-bash.html

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

## Testing

Just run:

```
./test-render
```
