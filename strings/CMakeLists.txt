cmake_minimum_required(VERSION 3.10)

set(longStr abcdefabcdef)
set(shortBit def)

string(FIND ${longStr} ${shortBit} fwdIndex)
string(FIND ${longStr} ${shortBit} revIndex REVERSE)

message("fdwIndex = ${fwdIndex}, revIndex = ${revIndex}")

string(REPLACE def ERIC newLongString ${longStr})

message("newLongString = , ${newLongString}")

set(longStr abcdefabcdef)

string(REGEX MATCHALL "[ace]" matchVar ${longStr})
string(REGEX REPLACE "([de])" "X\\1Y" replVar1 ${longStr})
string(REGEX REPLACE "([de])" [[X\1Y]] replVar2 ${longStr})

message("longStr = " ${longStr})
message("matchVar = ${matchVar}")
message("replVar1 = ${replVar1}")
message("replVar2 = ${replVar2}")

string(SUBSTRING ${longStr} 3 4 subStr)
message("subStr = " ${subStr})

set(greeting "  Hello There  ")
string(LENGTH ${greeting} greetingLength)
string(TOLOWER ${greeting} lowerCaseGreeting)
string(TOUPPER ${greeting} upperCaseGreeting)
string(STRIP ${greeting} strippedGreeting)

message("\ngreeting: ${greeting} is ${greetingLength} \
  characters long.\n In lower case: ${lowerCaseGreeting}\n \
  and in upper case: ${upperCaseGreeting}. \n \
  stripped of white space front and back: ${strippedGreeting}")

set(myList a b c)
list(LENGTH myList myListLength)
message("\nmyList = ${myList}\nlength of myList = ${myListLength}")

list(GET myList 2 1 letters)
message("letters = ${letters}")

list(APPEND myList d e f)
message("myList lengthened to ${myList}")
list(INSERT myList 2 insert)
message("${myList}")

list(FIND myList insert index)
message("insert is at index ${index}")

list(REMOVE_ITEM myList insert)
message("insert removed: ${myList}")

list(REMOVE_AT myList 3)
message("index 3 item removed: ${myList}")

list(APPEND myList a b c)
message("extended to ${myList}")
list(REMOVE_DUPLICATES myList)
message("duplicates removed: ${myList}")

list(REVERSE myList)
message("list reversed: ${myList}")
list(SORT myList)
message("list sorted: ${myList}")

