# 相关概念
PLD：可编程逻辑器件，是器件！其逻辑功能由用户编程设定
EDA工具：Quartus

HDL：硬件描述语言
VHDL、VerilogHDL：主要的硬件描述语言
PLD分类：SPLD、CPLD、FPGA

OLMC：输出逻辑宏单元

GAL：通用阵列逻辑，属于PLD的一种
组成：可编程与阵列、不可编程或阵列、OLMC
GAL16V8
    电路构成
    结构控制字：SYN AC0 AC1(n) XOR(n) PTD
    组合模式

#### Verilog HDL
# 特点 
    1.模块化
    2.C语言基础上开发

# 语言要素
    （1）关键字
    定义
        module;endmodule 模块开始结束定义
        input;output;inout 双向端口定义
        parameter 信号的参数定义
        wire wire信号定义
        reg reg信号定义
    关键字
        assign 产生wire信号语句
        always 产生reg信号语句
    标记
        if;else;
        for;
        begin;end;
        posedge;negedge; 上下沿触发
        case;endcase case语句
        default 默认分支
    （2）标识符
        组成:英文字母、数字、下划线"_"、字符
        用来命名
        必须以字母or_开头；字母区分大小写；关键字不能作为标识符使用
    （3）空白与注释
    空白不限制，编译时会被忽略
    注释用//到行尾 or /*--------*/开始到结束
    
    （4）逻辑值状态
        4种状态(0 1 x z)
            x为不确定或未知的逻辑状态
            z为高阻态

# 数据类型
    1.常量
        1.1 integer常量
            4'b1001
            5'h8c_2a
        1.2 parameter常量

    2.变量
        2.1 wire型变量
        输出随输入的变化而更新，用assign赋值
        2.2 reg型变量
        reg在always内使用

    3.基本程序结构
        module module_name(GND Vcc Qcc A B C Q Cr……)
            port_mode(input output inout)
            parameter_define(optional)
            (wire reg)
            语句
        endmodule


    4.常用语句

非阻塞赋值"<=" 块结束才改变
阻塞赋值"="立即改变

# 运算操作符
    !   ~
    *   /   %
    +   -
    <<  >>
    <   <=  >   >=
    ==  !=  === !==
    &   ^   ^~  |
    &&  ||
    ?
    {}


ModelSim仿真