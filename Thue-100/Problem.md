<b>Problem writer: Jacob Edelman</b><br>
This year we have a few programming challenges for the Thue programming language. Thue is an esoteric programming language, rarely known and never used for programming in practice. Don't worry if you don't know it already, if you do, you have a bit too much time on your hands. Also note that for simplicity reasons the version of Thue we use is slightly different from the standard version. Don't worry though, programming in Thue is easy. Your program will consist of a set of substitution (string replacement) rules, each terminated by a semicolon. Each rule consists of a left hand side string (lhs), an equals sign, and a right hand side string (rhs). A program will take an input string and set the state equal to that, and then search through the substitution rules, starting from the first one you give it, for any rules with an lhs that appears in the state. When such a rule is found, the first appearance of the lhs in the state is replaced with the rhs of that rule and the search through the substitution rules is started again with this new state. When no such rule is found in all the rules given, the current state is returned as the output. The input, lhs, and rhs strings all consist only of ascii characters besides semicolons and equals signs. Whitespace, such as line breaks, spaces, and tabs, is ignored in both the rule set and the input. For instance a program could be:

00 = he0;
1 = -world;
0 = xxo1;
x = l;

Note that the line breaks and spaces we have included are not needed and have no effect on
the program. An input to it could be the string "00". The execution of the program
would look like this:

00 (initial state)
he0 (the first rule in our program matches so it is applied)
hexxo1 (the 1st and 2nd rules do not match but the 3rd one does so it is applied)
hexxo-world (the 1st rule doesn't match but the 2nd does)
helxo-world (the 4th rule matches)
hello-world (the 4th rule matches)
hello-world (this is returned as no more rules apply)

Have more questions? You can see the source code for the Thue interpreter we are using for all Thue problems here.

Problems will have rather large time, state size, and program size unless state otherwise, so if you're getting an error that says it is one of those it will most likely be because your program is faulty.

Now, for 100 points, can you code a program in Thue that takes an input in the form "a[several repetitions of the letter b]" and outputs "[the same number of the letter b]a". For instance, "abb" should go to "bba" and "abbbb" should go to "bbbba". Good luck!
