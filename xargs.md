# XARGS

XARGS processes data from stdin and converts it to a list of arguments.  
So per default, it does not work line-wise!  

## Examples for Better Understanding

__Default xargs behaviour__

Command: `echo -e "sentence_one\nsentence_two" | xargs`  

Output:  
  _sentence_one sentence_two_  

In the default behaviour xargs just prints the input in one line separated with a whitespace.
  
Command: `echo -e "sentence_one\nsentence_two" | xargs -L 1`

Output:  
  _sentence_one_  
  _sentence_two_  
  
With the parameter '-L 1' one line is processed at a time from the input arguments.
