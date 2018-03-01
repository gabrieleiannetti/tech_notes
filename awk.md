# AWK

## Substitution with Text

This is the text how it looks like form the input.txt file:

> value1|value2

The awk command with substitution within a given text:

```
awk -F '|' '{ print "UPDATE TABLE SET field='\''"$2"'\'' where field='\''"$1 "'\'';"}' input.txt
```
