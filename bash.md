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

Rename files with indexes from **input.done** to **input**:  
```
for i in {0..34};
do
    filename_old=ext_standard_file_ost${i}.input.done
    filename_new=ext_standard_file_ost${i}.input
    
    if [ -f "${filename_old}" ]; then
        echo "rename ${filename_old} ${filename_new}"
        mv ${filename_old} ${filename_new}
    fi
done
```


## Resources

* [Shell Parameter Expansion](https://www.gnu.org/software/bash/manual/html_node/Shell-Parameter-Expansion.html)
