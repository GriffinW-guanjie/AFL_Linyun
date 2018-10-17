# AFL_Linyun
emprical study for AFL

The quick tutorial of running Dr. Wang Haijun's code.

1. How to run the afl-fuzz program.
We run afl-fuzz program has two prerequisites: 1) modify and recompile alf-fuzz.c and 2) compile the subject programs with alf compiler. We introduce the steps as follows:

=Modify and Recompile alf-fuzz.c
We should open afl-fuzz.c and locate the code with comment "///empirical study". There are two parts requiring modifications.
The first comment lies in line 82. The following variables are self-explained with its comments. Those variables specify the parameters of running a specific project.
The second comment lies in line 1102. We may output the value of the variables defined in the part of first comment. We may output an excel to collect the data.

After modification, we use make command to generate afl-fuzz binary program.

=Compile the subject projects with afl compiler.
We may refer to http://lcamtuf.coredump.cx/afl/QuickStartGuide.txt for more details. In short, the folder includes a c file "test-instr.c". Once we recompile afl-fuzz program, we should have alf-gcc. Hence, we can use the following command to compile the test program:
afl-gcc test-instr.c -o test

Everything is similar to gcc command, except that we use alf-gcc instead of gcc.

=Run the afl
Now we can run the program with the following command
./afl-fuzz -i input_dir -o out_dir -- test
You can see the output in the command line.
