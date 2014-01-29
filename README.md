Codigo_tecladoM
===============

Codigo en verilog del teclado Matricial
======================================
`timescale 1ns / 1ps
//////////////////////////////////////////////////////////////////////////////////
// Company: 
// Engineer: 
// 
// Create Date:    23:02:24 01/07/2014 
// Design Name: 
// Module Name:    Top_Teclado 
// Project Name: 
// Target Devices: 
// Tool versions: 
// Description: 
//
// Dependencies: 
//
// Revision: 
// Revision 0.01 - File Created
// Additional Comments: 
//
//////////////////////////////////////////////////////////////////////////////////
module Top_Teclado(clk50,ascii,Columna,isDone,Fila);
	input clk50; 
	input [3:0]Columna;
	output [6:0]ascii; 
	output isDone;
	output [3:0] Fila;
	wire w_clk;

	LectorFila lec_F(.clk_sec(w_clk), .ent_teclado(Fila));

	Teclado teclado(.clk_Teclado(w_clk), .Fila(Fila), .ascii(ascii), .Columna(Columna), .isDone(isDone));

	Divisor_Teclado div_T(.clk_T(clk50), .t(w_clk));

endmodule
