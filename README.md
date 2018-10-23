module TecladoLindinho2009(clk, speakerLa, speakerDo, speakerRe, speakerMi, speakerFa, speakerSol, speakerSi);
input clk; 
output speakerLa, speakerDo, speakerRe, speakerMi, speakerFa, speakerSol, speakerSi; 

reg [31:0] counterLa = 0, counterDo = 0, counterRe = 0, counterMi = 0, counterFa = 0, counterSol = 0, counterSi = 0;
reg clk25;

always@(posedge clk)
begin

	clk25 <= ~clk25;
	
end

always @(posedge clk25)
begin

	if(counterDo==47348) counterDo<=0; 
	else counterDo <= counterDo+1;

	if(counterRe==42087) counterRe<=0; 
	else counterRe <= counterRe+1;

	if(counterMi==37878) counterMi <=0; 
	else counterMi <= counterMi+1;

	if(counterFa==35511) counterFa <=0; 
	else counterFa <= counterFa+1;

	if(counterSol==31565) counterSol <=0; 
	else counterSol <= counterSol+1;

	if(counterLa==28408) counterLa<=0; 
	else counterLa <= counterLa+1;

	if(counterSi==25252) counterSi <=0; 
	else counterSi <= counterSi+1;

end
    
reg speakerDo, speakerRe, speakerMi, speakerFa, speakerSol, speakerLa, speakerSi;

always @(posedge clk25)
begin
	if(counterDo==47348) speakerDo <= ~speakerDo;
	if(counterRe==42087) speakerRe <= ~speakerRe;
	if(counterMi==37878) speakerMi <= ~speakerMi;
	if(counterFa==35511) speakerFa <= ~speakerFa;
	if(counterSol==31565) speakerSol <= ~speakerSol;
	if(counterLa==28408) speakerLa <= ~speakerLa;
	if(counterSi==25252) speakerSi <= ~speakerSi;

end 
endmodule

/*

Frequencia notas:

DO = 47348
RE = 42087
MI = 37878
FA = 35511
SOL = 31565
LA = 28408
SI = 25252

Pinos FPGA:

D3 - Do
C3 - Re
A3 - Mi
B4 - Fa
B5 - Sol
D5 - La
A6 - Si

*/ 
