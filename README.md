# TecladoLindinho2009

module TecladoLindinho2009(clk, speaker, speaker1);
input clk;
output speaker;
output speaker1;

reg [31:0] counter,counter1;
always @(posedge clk)begin
if(counter==56818) counter<=0; else counter <= counter+1;
if(counter1==47348) counter1<=0; else counter1 <= counter1+1;
end

reg speaker, speaker1;
always @(posedge clk)begin
  if(counter==56818 || counter==56817 ) speaker <= ~speaker;
  if(counter1==47348 || counter1==47347) speaker1 <= ~speaker1;
  end
endmodule

// LA = 56818
// DO = 47348
// RE =
// MI =
// FA =
// SOL =
// SI = 
