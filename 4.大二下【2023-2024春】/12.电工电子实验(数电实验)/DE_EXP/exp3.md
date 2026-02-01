###### 实验三
# 用74161和置数法设计一个8进制计数器

# 用两片74161设计一个60进制计数器

# 用两片74161设计一个63进制计数器

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

