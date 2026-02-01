###### 实验一
# 相关概念
三态逻辑笔：测量导线损坏，（一端接输入端INPUT 一端接数据开关）；一致则正常，否则高阻态
数字万用表：测高低电平电压值

# 与或非门 实现逻辑函数

# 用00和86设计一位全加器

# 用83设计一个余3码至8421码转换电路，并将结果用显示译码器(74HC248和共阴极LED数码管组成的译码显示电路)显示。

补码的相关知识
正数的补码=原码
负数的补码ex：
0011+1101=16，(3的补码为16-3)
011+101=8,(3的补码为8-3)

# 一位全加器的VHDL描述
过程：编程→编译→RTL Viewer(查看仿真波形)
VHDL程序：
library ieee;
use ieee.std_logic_1164.all;
entity name is <!--name为实体名称，必须与新建的工程名称一致-->
    port
    (
        a: in std_logic;
        b: in std_logic;
        c: in std_logic;
        s: out std_logic;
        e: out std_logic;
    );
architecture one of name is
    signal d: std_logic;
    signal f: std_logic;
begin
    s<= a XOR b XOR c;
    d<= (a XOR b) AND c;
    f<= d AND f;
    e<= d OR f;
end one;


# Quartus Prime使用教程
新建工程 <!--工程名称和顶层实体名称相同-->
    选择FPJA器件(Cyclone V家族中的5CEBA4F23C7N)
    一直next
    finish(回到主界面)
新建VHDL file
    编程
    保存
    编译(实体名称和工程名称必须一致)
电路仿真(后台调用multisium)
    调用路径设置
        tools-options-general-EDA Tool Options，路径设置为multisium.exe所在文件夹
    新建-memory-files-memory initialization file，建立矢量波形文件
edit-设置截止时间；
双击name下空白-node finder-list->>复制到右侧-OK
设置随机值



功能仿真 
检查无误 关闭仿真

配置引脚(PIN_U13、)
重新编译
.sof


功能仿真：前仿真，不考虑器件延时，验证项目逻辑是否正确  <!--不考虑电路的传播延时
时序仿真：后仿真，考虑器件延时；不仅测试逻辑功能，还测试目标器件最差情况下的时间关系