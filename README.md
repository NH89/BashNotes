# BashNotes
A collection of very useful Bash + Perl commands

I needed to export files from Ext4 -> ExFAT. This caused problems because ExFAT prohibits certain characters in file paths.
These commands helped change all the afftected file and directory names.

 Here is the final version of the command used. '-v' gives verbose output.

find ~/ -name "*[\:]*"  -execdir rename -v 's/\:/_colon_/g' '{}' \+

find ~/ -name "*[\\]*"  -execdir rename -v 's/\\/_backslash_/g' '{}' \+

find ~/ -name "*[\*]*"  -execdir rename -v 's/\*/_asterisk_/g' '{}' \+

find ~/ -name "*[\?]*"  -execdir rename -v 's/\?/_questionmark_/g' '{}' \+

find ~/ -name "*[\<]*"  -execdir rename -v 's/\</_lessthan_/g' '{}' \+

find ~/ -name "*[\>]*"  -execdir rename -v 's/\>/_greaterthan_/g' '{}' \+

find ~/ -name "*[\|]*"  -execdir rename -v 's/\|/_pipe_/g' '{}' \+


And to check no ExFAT-illegal file paths remain

find ~/ -name "*[\\|\:|\*|\?|\<|\<|\>|\|]*"


find control characters in filepaths (these were mostly tab and newline characters)
 
find ~/ -name "*[:cntrl:]*"
