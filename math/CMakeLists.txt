cmake_minimum_required(VERSION 3.10)

# math(EXPR outVar mathExpr)

set(x 3)
set(y 7)
math(EXPR zDec "(${x}+${y})")
message("decimal = ${zDec}")

# hexadecimal: cmake 3.13 or higher needed
# math(EXPR zHex "${x}+${y} * 2" OUTPUT_FORMAT HEXADECIMAL)

