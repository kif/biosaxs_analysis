Dear Co-Editor,

Please find hereafter our answer to the three referees:

# Referee 1
1. The document was proof-read by Mark Tully, co-author, who is a native English speaker.
2. This refers actually to the command line tool (all lower case), different from the project which is named FreeSAS and includes it.
3. Fixed, thanks for spotting it
4. Distinction between IFT, the BIFT algorithm and the name of the program was made clearer.
5. This section reshuffled with a table listing all applications
6. main text updated to avoid the issue
7. figure updated to avoid having two stage 2
8. The sentence has been dropped
9. a sentence was added to compare the performances with the previous setup
10. The full sentence was removed. Just to comment on the reliability: Dahu is running as a single program with threads running algorithms implemented by FreeSAS using Cython. Any memory management error within the Cython part would crash the complete server. Since this does not occur, it proves the ensemble is reliable, unfortunately it does not prove all the math were properly implemented.
11. TODO
# Referee 2

# referee 3
1. You are right, since all software is new, this is not an upgrade but a new 