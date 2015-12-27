# iverilog simple tutorial

First, let's assume your code has the name: hello.v
and th testbench file for simulation is named: hello_tb.v

###How to compile:
    % iverilog -o filename1 hello_tb.v hello.v

Note：filename1 is what you give to the file which is going to save the result of this compiling.

###How to run:
    %vvp filename1

###How to see the waveforms：
In your testbench, inside initial, add two lines of dump, like this:

    initial
     begin
        $dumpfile("wavefile.vcd");
        $dumpvars(0, tb_module_name);
     end
Note：To see the waveforms, you need to save the result of your code into a file in some form.
So you have to give that file a name, which is "wavefile.vcd".

Note: "tb_module_name" is what you write in your "hello_tb.v" as the module name. 


Then run this:

    % gtkwave wavefile.vcd &


Done.
