cmake_minimum_required(VERSION 3.10)

set(myVar a b c)
message("myVar = ${myVar}")

set(myVar a;b;c)
message("myVar = ${myVar}")

set(myVar "a b c")
message("myVar = ${myVar}")

set(myVar a "b c")
message("myVar = ${myVar}")

set(foo ab)
message("foo = ${foo}")

set(bar ${foo}cd)
message("bar = ${bar}")

set(baz ${foo} cd)
message("baz = ${baz}")

set(myVar ba)
message("myVar = ${myVar}")

set(big "${${myVar}r}ef")
message("big = ${big}")

set(${foo} xyz)
message("${foo} = ${${foo}}")

# Simple multi-line content with bracket syntax,
# no = needed between the square bracket markers
set(multiLine [[
    First line
    Second line
]])

# Bracket syntax prevents unwanted substitution
set(shellScript [=[
#!/bin/bash

[[ -n "${USER}" ]] && echo "Have USER"
]=])
message("shellScript = ${shellScript}")

# equivalent code without bracket syntax
set(shellScript
"#!/bin/bash

[[ -n \"\${USER}\" ]] && echo \"Have USER\"
")

message("ENV{PATH} = $ENV{PATH}")
set(ENV{PATH} "$ENV{PATH}:/opt/")
message("ENV{PATH} = $ENV{PATH}")

# cache variables
# set(varName value... CACHE type "docstring")

