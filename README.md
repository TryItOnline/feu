# FEU

*File Edition Utility*

(Fun fact: Feu mean fire in French)

FEU is a sed-like utility making heavy use of regexs.

## Syntax

Each line is a command.

Commands are in this form:

    mode/arg1/arg2/.../argN

A line can also be a keyword:

* `end` End a block
* `loop` Start an infinite loop
* `do number` Execute a block a specified number of times
* `func name` Define a function
* `call name` Call a function
* `__DATA__` The rest of the file is the input to the program

|Mode|Command format|Description|
|:-:|:-:|:-:|
||`/regex/flags`|Execute the next block for each strings matched by the regex|
|`s`ubstitute|`s/regex/sub/flags`|Replace each occurence of a regex in the input|
|`e`xit|`e/regex/flags`|Exit the current block if the input is matched by the regex (effect can be negated by adding the `!` flag)|
|`m`ap|`m/regex1/sub1/regex2/sub2/.../regexN/subN/flags`|Same as `s`, but using a mapping|
|`a`ppend|`a/text`|Append text at the end of the input (equivalent to `s/$/text`)|
|`p`repend|`p/text`|Prepend text at the start of the input (equivalent to `s/^/text`)|
|`u`nary|`u/character`|Convert the input from decimal to unary using a specified character (the sign is ignored)|
|`U`nary|`U/character`|Convert the input from unary to decimal with a specified unary character|
|`i`gnore|`i/text`|Comment|
|`S`hell|`S/command/arg1/arg2/.../argN`|Execute a shell command|
|`E`xtended|`ecommand`|Execute an extended command|

Extended commands:

|Mode|Command format|Description|
|:-:|:-:|:-:|
|`s`et|`s/var/regex/flags`|Set a variable to the portions of the input matched by the regex|
|`p`ush|`p/var`|Push the current input on the input stack and set the input to the specified variable|
|`P`op|`p/var`|Set the variable to the current input and set the input to the value on the top of the input stack|
|`u`ndefine|`u/var`|Undefine a variable|
|`a`ppend|`a/var`|Append the content of a variable at the end of the input|
|`p`repend|`p/var`|Prepend the content of a variable at the start of the input|

## Examples

See the `examples` folder
