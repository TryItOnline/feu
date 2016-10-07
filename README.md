# FEU

*File Edition Utility*

(Fun fact: Feu mean fire in French)

FEU is a sed-like utility making heavy use of regexs.

## Syntax

Each line is a command.

Commands are in this form:

    mode/arg1/arg2/.../argN

A line can also be `end` to end a block command.

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

## Examples

See the `examples` folder
