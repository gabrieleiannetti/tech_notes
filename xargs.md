# XARGS

XARGS processes data from stdin and converts it to a list of arguments.  
So per default, it does not work line-wise!  

## Examples for Better Understanding

__Default xargs behaviour__  

Command: `echo -e "sentence_one\nsentence_two" | xargs`  

Output:  
  _sentence_one sentence_two_  

In the default behaviour xargs just prints the input in one line separated with a whitespace.
  
__Processing one line argument at a time__  

Command: `echo -e "sentence_one\nsentence_two" | xargs -L 1`

Output:  
  _sentence_one_  
  _sentence_two_  
  
With the parameter '-L 1' one line is processed at a time from the input arguments.

__Argument positioning__

Command: `echo -e "sentence_one\nsentence_two" | xargs -I {} echo whatever-you-want-{}`

Output:  
  _whatever-you-want-sentence_one_  
  _whatever-you-want-sentence_two_  
  
Arguments are replaced with '-I' by an identificator strings e.g. '{}'.  
The parameter '-I' interprets the newline as separator (ref. man page).  
