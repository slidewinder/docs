# Coffeescript style guide

## Some basic rules

1. don't commit any generated javascript - only commit the coffeescript
2. follow [this community style guide](https://github.com/polarmobile/coffeescript-style-guide#guide)

## Readability

We also have some additional rules that help keep the codebase clean and readable to people who might be coming from other languages.

### When calling a function/method with more than one argument, wrap the arguments in parenthesis

```coffeescript
some_function arg # good
some_function arg1, arg2 # bad
some_function(arg1, arg2) # good
```

### When nesting function calls use parenthesis to explicitly show the order of operation

```coffeescript
some_function other_function arg1, arg2 # bad bad bad
some_function(other_function(arg1, arg2)) # better
```

### But ideally, don't nest function calls

It only saves lines of code, which are free. It also makes debugging harder.

There is sometimes a memory/efficiency cost to creating lots of variables, but this is not a resource intensive program and there's currently no need to optimise.

Prefer a single expression per line:

```coffeescript
# best
result = other_function(arg1, arg2)
some_function(result)
```

### Make code blocks easy to see by not nesting too deeply

There are two parts to this:

1. If you are about to nest something more than one level within a function/method, break it out into a new function/method.
2. Bring the indentation back to the starting level at the end of each block, even if it means redundantly naming a return value.

```coffeescript
# bad
plan_day = (day) ->
  switch day
    when "Mon" then go work
    when "Tue" then go relax
    when "Thu" then go iceFishing
    when "Fri", "Sat"
      if day is bingoDay
        go bingo
        go dancing

# good (two functions, each pulls back to starting indentation)
plan_day = (day) ->
  switch day
    when "Mon" then go work
    when "Tue" then go relax
    when "Thu" then go iceFishing
    when "Fri", "Sat" then bingo_or_dancing day
  null

bingo_or_dancing = (day) ->
  if day is bingoDay
    go bingo
  else go dancing
```
