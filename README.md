# IS
Single header library to handle characters streams in C

___
## Is IsInit(char *input, int input_size, int plat, int tab)

init and return the needed stucture to stream\
**input** : the stream\
**input_size** : the stream length\
**plat** : the current end of line format ( possible values : **UNIX**[lf], **MAC**[cr], **WIN**[cr+lf] )\
**tab** : the tab indentation size to keep track of the current stream position
___
## char IsNext(Is *is)

return the character at the current stream position and advance the stream\
the caller must be sure that the stream is not terminated
___
## char IsPeek(Is *is)

return the character at the current stream position
___
## int IsAccept(Is *is, char c)

if the c parameter match the current stream position advance the stream and return 1, otherwise return 0\
(should be used to accept possible characters)
___
## int IsExpect(Is *is, char c)

if the c parameter match the current stream position advance the stream and return 1, otherwise return 0\
(should be used to accept expected charatcers and return errors on fail)
___
## void IsSkipBlanks(Is *is)

advance the stream skipping all the blank charcters\
' ','\f','\n','\r','\t','\v'
___
## int IsEnd(Is *is)

return 1 if stream end, otherwise 0