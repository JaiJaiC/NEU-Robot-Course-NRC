module test(clk,IN,A,B,C)
    input clk,IN;
    output reg A,B,C;
    always @(posedge clk)
    begin
        A<=IN;<!---->
        B<=A;<!---->
        C<=B;
    end
endmodule
