source=p3_tb.sv memory.sv regfile.sv mips.sv
iFlags=-g2005-sv
vFlags=-n

run: CheckVowel fact SimpleIf SumArray Swap

%.vvp: $(source)
	iverilog $(iFlags) -s tb_$* -o $@ $(source)

%.lx2: %.vvp
	vvp $(vFlags) $< -lxt2
	mv dump.lx2 $@

CheckVowel: CheckVowel.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

CheckVowel_wave: CheckVowel.lx2
	gtkwave -A $< &

CheckVowel_debug: CheckVowel_debug.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

fact: fact.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

fact_wave: fact.lx2
	gtkwave -A $< &

fact_debug: fact_debug.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

SimpleIf: SimpleIf.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

SimpleIf_wave: SimpleIf.lx2
	gtkwave -A $< &

SimpleIf_debug: SimpleIf_debug.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

SumArray: SumArray.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

SumArray_wave: SumArray.lx2
	gtkwave -A $< &

SumArray_debug: SumArray_debug.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

Swap: Swap.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

Swap_wave: Swap.lx2
	gtkwave -A $< &

Swap_debug: Swap_debug.vvp
	@echo vvp $(vFlags) $<
	@vvp $(vFlags) $< | grep -v "Not enough words" | grep -v "opened for output"

clean:
	rm -f *.vvp *.lx2 *.vcd
