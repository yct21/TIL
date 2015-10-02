Execute each line of a heredoc
=====
Use backticks in a heredoc, Ruby will execute each line in a shell and replace it with the output of that command.

```
output = <<-`COMMANDS`
  echo first
  echo second
COMMANDS

p output #-> "first\nsecond\n"
```

## Reference

-[Little Things: Heredocs](http://weblog.jamisbuck.org/2015/9/12/little-things-heredocs.html)
