# 一位全加器的VHDL描述
过程：编程→编译→RTL Viewer查看器(查看仿真波形)
程序：
library ieee;
use ieee.std_logic_1164.all;
entity set_name is
    port
    (
        a: in std_logic;
        b: in std_logic;
        c: in std_logic;
        s: out std_logic;
        e: out std_logic;
    );
architecture one of set_name is
    signal d: std_logic;
    signal f: std_logic;
begin
    s<= a XOR b XOR c;
    d<= (a XOR b) AND c;
    f<= d AND f;
    e<= d OR f;
end one;

# BCD-7段显示译码器VHDL描述

library ieee;
use ieee.std_logic_1164.all;
entity BCD-7 is
    port
    (
        a: in std_logic_vector(3 downto 0);
        hex: out std_logic_vector(6 downto 0);
    );
end BCD-7
architecture one of BCD-7 is
begin
process(a)
begin
    case a is
    when "0000"=>hex<="1000000";
    when "0000"=>hex<="1000000";
    when "0000"=>hex<="1000000";
    when "0000"=>hex<="1000000";
    when "0000"=>hex<="1000000";
    when "0000"=>hex<="1000000";
    when "0000"=>hex<="1000000";
    when others=>hex<="1111111";
end case;
end process;
end;

# D触发器的VHDL描述
library ieee;
use ieee.std_logic_1164.all;
entity dff1 is
  port(
    clk,d:in std_logic;
	 q:out std_logic
  );
end dff1;

architecture behavior of dff1 is
  signal q1:std_logic;    <!--引进内部节点信号
  begin
    process(clk)     <!--进程语句以及敏感信号
	 begin
    if clk'event and clk='1' then  <!--检查clk上升沿
	   q1<=d;
	 end if;
	 q<=q1;
  end process;
end behavior;

# 十进制计数器的VerilogHDL描述
module cnt_10(rst,en,clk,q,count);
input rst,en,clk
output reg[3:o] q;
output reg count;
always@(posedge clk or negedge rst)
begin
if(~rst) begin q<=4'b0000;count<-1'b0;end
    else if(en)
    if(q==4'b1001) begin q<=4'b0000;count<=1'b0;end
end
endmodule

# 秒脉冲的VHDl描述

# 3-8译码器的VHDL描述

