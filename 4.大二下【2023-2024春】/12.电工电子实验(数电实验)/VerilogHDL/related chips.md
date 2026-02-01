#### 74HC138
module 74HC138(
    input wire S3,S2,S1,
    input wire A2,A1,A0,
    output wire F7,F6,F5,F4,F3,F2,F1,F0,
);

<!--线网类型-->
wire An,Bn,Cn;  
wire Ann,Bnn,Cnn,Gen

<!--功能定义-->
assign An = ~A0;
assign An = ~A0;
assign An = ~A0;
assign An = ~A0;
assign An = ~A0;
assign An = ~A0;    
assign Gen = (S1 & ~S2 & ~S3);
assign F0 = ~(An & Bn &Cn & Gen);
assign F0 = ~(An & Bn &Cn & Gen);
assign F0 = ~(An & Bn &Cn & Gen);
assign F0 = ~(An & Bn &Cn & Gen);
assign F0 = ~(An & Bn &Cn & Gen);
assign F0 = ~(An & Bn &Cn & Gen);
assign F0 = ~(An & Bn &Cn & Gen);
assign F0 = ~(An & Bn &Cn & Gen);
endmodule

#### 74HC151
module 74HC151(
    input wire OE,
    input wire A2,A1,A0
    input wire D7,D6.D5,D4,D3,D2,D1,D0
    output reg F
);
    always @(*)
    begin
        if(~OE)
            case({A2,A1,A0})
            3'b000:F=D0;
            3'b001:F=D1;
            3'b001:F=D2;
            3'b001:F=D3;
            3'b001:F=D4;
            3'b001:F=D5;
            3'b001:F=D6;
            3'b001:F=D7;
            endcase
        else F=0
    end
endmodule

#### 7485
module 7485(
    input wire A0,A1,A2,A3,
    input wire B0,B1,B2,B3,
    input wire AlBin,AEBin,AGBin,
    output reg ALBout,AEBout,AGBout
);
    wire [3:0] data_a,data_b;
    assign data_a={A0,A1,A2,A3};
    assign data_b={B0,B1,B2,B3};
    always @( * )
    begin
        if (data_a > data_b)
        begin
        ALBout=0,AEBout=0,AGBout=1
        end
        else if ()
        begin

        end
        else if ()
        begin
        
        end
    end
endmodule


#### 1位全加器
module full_adder(Cin,A,B,S,Cout)
    input A;B;Cin
    output S;Cout
    wire h;
    assign h=A^B
    assign S=Cin^h
    assign Cout=(A%B|(Cin&h))
endmodule

#### 4位串行进位并行输出加法器
module full_adder4(
    input wire C0;
    input wire [3:0] Ai;
    input wire [3:0] Bi;
    output wire [3:0] Si;
    output wire C4
)
wire C1,C2,C3
<!--实例化4个1位全加器，通过名称关联-->
full_adder u0(.Cin(C0),.A(Ai[0]),.B(Bi[0]),.S(Si[0]),.Cout(C1));
full_adder u1(.Cin(C1),.A(Ai[1]),.B(Bi[1]),.S(Si[1]),.Cout(C2));
full-adder u2(.Cin(C2),.A(Ai[2]),.B(Bi[2]),.S(Si[2]),.Cout(C3));
full-adder u3(.Cin(C3),.A(Ai[3]),.B(Bi[3]),.S(Si[3]),.Cout(C4));

#### 水箱水位监测预警电路
    # 编码模块
    module encoder(A,B,C,m);
        input A,B,C;
        output reg[1:0]m;
        wire [2:0]sel;
        assign sel={A,B,C}
        always @(sel)
        begin
            case(sel)
                3'b000:m=2'b10;
                3'b001:m=2'b01;
                3'b011:m=2'b00;
                3'b111:m=2'b11;
                default:m=2'b11;
            endcase
        end
    endmodule
    # 报警模块
    module alarm(k,w,u,v);
        input[1:0]k;
        output reg w,u,v;
        always @(k)
        begin
            case(k)
                2'b00:{w,u,v}=3'b100;
                2'b01:{w,u,v}=3'b010;
                default:{w,u,v}=3'b001;
            endcase
        end
    endmodule
    # 显示模块
    module full_adder4(
        input wire C0,[3:0]Ai,[3:0]Bi
        output wire [3:0]Si,C4
        );
        wire C1,C2,C3
        full_adder u0(.Cin(C0),.A(Ai[0]),.B(Bi[0]),.S(Si[0]),.Cout(C1));
        full_adder u1(.Cin(C1),.A(Ai[1]),.B(Bi[1]),.S(Si[1]),.Cout(C2));
        full-adder u2(.Cin(C2),.A(Ai[2]),.B(Bi[2]),.S(Si[2]),.Cout(C3));
        full-adder u3(.Cin(C3),.A(Ai[3]),.B(Bi[3]),.S(Si[3]),.Cout(C4));
    endmodule
    # 顶层模块

#### 门控D锁存器
module D_latch(
    input wire D,LE,
    output wire Q,QN
    );
    reg QF;
    assign Q=QF;
    assign QN=~QF;
    alwayss @(LE or D)
        if(LE)
            QF<=D;
endmodule

#### JK触发器
module jk(
    input wire CLR,SET,CP,J,K
    output wire Q,QN
    );
    reg QF;
    assign Q=QF;
    assign QN=~QF
    always @(negedge CP or negedge CLR or negedge SET)
    begin
        if(!CLR)
            QF<=0;
        else if(!SET)
            QF<=1;
        else
            QF<=J&(~QF) | ~k&QF
        end
    endmodule

#### 74HC194
module HC194(
    input wire CP,Rd,SR,SL,S0,S1,a,b,c,d;
    output wire QA,QB,QC,QD
    );
    ref QF0,QF1,QF2,QF3;
    assign {QA,QB,QC,QD} = {QF3,QF2,QF1,QF1};
    always @(posedge CP or negedge Rd)
    begin
        if(~Rd)
        begin
            {QF3,QF2,QF1,QF1}<=4'b0000;
        end
        else case({S1,S0})
            2'b00:{QF3,QF2,QF1,QF1} <= {QF3,QF2,QF1,QF1}
            2'b01:{QF3,QF2,QF1,QF1} <= {SR,QF3,QF2,QF1}
            2'b10:{QF3,QF2,QF1,QF1} <= {QF2,QF1,QF1,SL}
            2'b11:{QF3,QF2,QF1,QF1} <= {a,b,c,d}
        default {QF3,QF2,QF1,QF1} <= 4'b0000;
        endcase
    end
endmodule

#### 74HC161
module HC161(
    input wire CP,CRn,LDn,ENP,ENT,[3:0]D
    output wire Qcc;
    output reg[3:0]Q;
    );
    assign Qcc=CRn & LDn & (Q==4'b1111);
    always @(posedge CP or negedge CRn)
    begin
        if (~CRn) begin
            Q <= 4'b0000;end
        else if(~LDn)
            Q <= D
        else begin
            case({ENP,ENT})
                2'b11:if (Q < 4'b1111) begin
                    Q<=Q+1;end;
                else if (Q == 4'b1111) begin
                    Q<=4;b0000;end;
                default:begin
                    Q <= Q;end;
            endcase
        end
    end
endmodule

#### GAL实现组合-时序混合的逻辑电路
module G16v8(
    input wire A,S,B,I,D,E,CLK,OE;
    output wire X1,Y,QA,QB,QD
    );
    reg QF Yn;
    reg [1:0]Q;
    assign {QA,QB,QD} = {Q[0],Q[1],QF};
    assign X1 = A&S | b&(~S);
    assign Y=Yn;
    always @(I or E)
    begin
        if(!E)
            Yn<=1'bz;
        else
            Yn<=~I
    end

    always @(posedge CLK or posedge OE)
    begin
        if(OE) begin
            {Q[0],Q[1],QF} <= 3'bzzz; end
        else if (Q < 2'b11) begin
            Q <= Q+1;
            QF = D; end
        else if(Q == 2'b11) begin
            Q <= 2'b00;
            QF = D; end
    end
endmodule

#### 串行数据0101序列检测器
module test0101(
    input wire clk,clr,x_in,
    output wire f
    );
    reg[3:0] QF=4'b0101;
    reg[3:0] x_temp;
    assign f = ~((x_temp[3]^QF[3]) | (x_temp[2]^QF[2]) | (x_temp[1]^QF[1]) | (x_temp[0]^QF[0]));
    always @(posedge clk or negedge clr)
    begin
        if (!clr) begin
            x_temp<=4'b0000;
        end
        else begin
            x_temp<={x_temp[2],x_temp[1],x_temp[0],x_in}
        end
    end
endmodule

#### 光点右移-左移-停止 控制电路
# module top_con(
    input wire clk_in,reset,
    output[1:0]sele,[3:0]Q,clk_Is
    );

clk_Is u0(.clk_in(clk_in),.reset(reset),.clk_out(clk_Is));
timer u1(.CLK(clk_Is),.RESET(reset),.sel(sele));
HC194 u2(clk_Is,1'b1,1'b1,1'b0,1'b0,1'b0,Q[0],Q[3],sele[1],sele[0],Q[3],Q[2],Q[1],Q[0]);
endmodule


# module clk_Is(input clk_in,reset,output regg clk_out);
    parameter Num=50000000
    integer count
    always @(negedge reset or posedge clk_in)
    begin
        if(~reset)
            count<=0;
        else if(count==(Num-1))
            count<=0
        else
            count<=count+1
    end
    always @(negedge reset or posedge clk_in)
    begin
        if(~reset)
            clk_out <= 0;
        else begin
            if(count <= (Num/2-1))
            clk_out <= 0
        else
            clk_out <= 1
        end
    end
endmodule

# module timer(
    input wire CLK,RESET,
    output[1:0] sel
    );
    reg[1:0]sele;
    integer iq;
    assign sel[1]=~(RESET&~sele[1]);
    assign sel[0]=~(RESET&~sele[0]);
    always @(posedge CLK or negedge RESET)
    begin
        if(~RESET) begin
            iq<=0;sele<=2'b11; end
        else if(iq>=0) &&(iq<20) begin
            iq<=iq+1;sele<=2'b01; 
            end
        else if(iq>=20) &&(iq<30) begin
            iq<=iq+1;sele<=2'b00; 
            end
        else if(iq>=30) &&(iq<50) begin
            iq<=iq+1;sele<=2'b10; 
            end
        else if(iq>=50) &&(iq<60) begin
            iq<=iq+1;sele<=2'b00; 
            end
        else if(iq>59) begin
            iq<=1;sele<=2'b01; 
            end
    end
endmodule

# module HC194(
    input wire CP,Rd,SR,SL,S0,S1,a,b,c,d;
    output wire QA,QB,QC,QD
    );
    ref QF0,QF1,QF2,QF3;
    assign {QA,QB,QC,QD} = {QF3,QF2,QF1,QF1};
    always @(posedge CP or negedge Rd)
    begin
        if(~Rd)
        begin
            {QF3,QF2,QF1,QF1}<=4'b0000;
        end
        else case({S1,S0})
            2'b00:{QF3,QF2,QF1,QF1} <= {QF3,QF2,QF1,QF1}
            2'b01:{QF3,QF2,QF1,QF1} <= {SR,QF3,QF2,QF1}
            2'b10:{QF3,QF2,QF1,QF1} <= {QF2,QF1,QF1,SL}
            2'b11:{QF3,QF2,QF1,QF1} <= {a,b,c,d}
        default {QF3,QF2,QF1,QF1} <= 4'b0000;
        endcase
    end
endmodule