# Comparing in Bash
#bash

## Conditional operators

### `if`

```bash
if [[ test ]];
then
    code here
fi
```

#### Test clause `[ ]` vs, `[[ ]]`

`[[ ]]` is bash's improvement of the `[ ]`. `[[ ]]` works aso in ZSH. Both Bash and ZSH trests the `[[ ]]` as synthactical expression, thus `>, <, &&, ||` can be used to build logical expressions.

When writing script that have to be backwards compatible, use `[ ]` because god knows what will run it.

bash https://www.gnu.org/software/bash/manual/html_node/Conditional-Constructs.html#Conditional-Constructs
zsh http://zsh.sourceforge.net/Doc/Release/Conditional-Expressions.html#Conditional-Expressions

### `case`
Strings can be also compared with `case`operator

```bash
#! /usr/bin/env bash

A="text"

case ${A} in

    "text")
        echo "Match"
     ;;
     
     "nonText" | "cat")
         echo "Not matched"
     ;;
esac
```

## Strings

### Equal `[ "A" = "B" ]`or `[[ A == B ]]`

```bash
#! /usr/bin/env bash

A="text"
B="text"

if [ ${A} = ${B} ];
then
    echo "Equal"
fi

if [[ ${A} == ${B} ]];
then
    echo "Equal"
fi

```

### Not Equal `[ "A" != "B" ]` 

```bash
#! /usr/bin/env bash

A="text"
B="text_2"

if [ ${A} != ${B} ];
then
    echo "Not Equal"
fi

if [[ ${A} != ${B} ]];
then
    echo "Not Equal"
fi
```

### Regex match `[[ A =~ R ]]`
True if A matches the Regex pattern.

```bash
#! /usr/bin/env bash

A="text"
R=".ex."
R1=".a."

if [[ ${A} =~ ${R} ]];
then
    echo "Match"
fi

if [[ ${A} =~ ${R1} ]];
then
    echo "Match"
else
    echo "No Match"
fi
```

### Lexicographical comparison `[[ A < B ]]` or `[[ A > B ]]`

```bash
#! /usr/bin/env bash

A="abc"
B="def"
C="xyz"

if [[ ${A} < ${B} ]];
then
    echo "Lexicographical ${A} < ${B}"
fi

if [[ ${C} > ${B} ]];
then
    echo "Lexicographical ${C} > ${B}"
fi
```

### String is zero `[[ -z A ]]`

```bash
#! /usr/bin/env bash

A=""
C="a"

if [[ -z ${A} ]];
then
    echo "String has zero len"
fi

if [[ -z ${B} ]];
then
    echo "Non defined string has zero len"
fi

if [[ -z ${C} ]];
then
    echo "String is empty"
else
    echo "String not empty"
fi
```

### String is not empty `[[ -n A ]]`

```bash
#! /usr/bin/env bash

A="a"
C=""

if [[ -n ${A} ]];
then
    echo "String is not empty"
fi

if [[ -n ${B} ]];
then
    echo "Non defined string has zero len"
else
    echo "String is empty"
fi

if [[ -n ${C} ]];
then
    echo "String is not empty"
else
    echo "String is empty"
fi
```

## Numbers
