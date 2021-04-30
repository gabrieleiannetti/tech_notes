# Bash

## Renaming Files

Remove file extension **tmp**:  
`for f in *.tmp; do mv -- "$f" "${f}"; done`

Replace file extension **tmp** with **out**:  
```
for f in *.tmp; do
    mv -- "$f" "${f%.tmp}.out";
done
```

## Resources

* [Shell Parameter Expansion](https://www.gnu.org/software/bash/manual/html_node/Shell-Parameter-Expansion.html)
