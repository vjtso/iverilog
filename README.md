# iverilog simple tutorial

首先，我们假定你的源文件叫做hello.v
仿真testbench文件叫做hello_tb.v

###如何编译:
    % iverilog -o 文件名1 hello_tb.v hello.v

注：文件名1是你自己起的用于存这次compile结果的文件名。

###如何运行：
    %vvp 文件名1

###如何看波形：
在你的testbench里的initial里加入两行dump，像这样：
    initial
     begin
        $dumpfile("波形文件名.vcd");
        $dumpvars(0, tb模块名);
     end
注：想看波形先要把代码的运行结果以数据的形式存放到一个文件里，
所以你要起一个文件名，就是上面的“波形文件名.vcd”
你的hello_tb.v文件里面的module起得什么名字，就在$dumpvars里面写什么名字。

然后运行下面这个命令：
    % gtkwave test.vcd &

