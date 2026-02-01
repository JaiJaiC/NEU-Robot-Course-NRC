###### 实验二
# 用153和138分别实现主裁判表决电路

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


触发器：具有记忆功能的二进制信息存储器件

# 利用JK和D构成四进制计数器
用两个JK
用两个D
用一个JK和一个D
同步和异步

# D触发器的VHDL描述