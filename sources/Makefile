MODULE := axistream_packetfilt
MODULE_CAPS := AXISTREAM_PACKETFILT

default:	$(MODULE).vcd

$(MODULE).vcd:	$(MODULE).vvp
	vvp $(MODULE).vvp

$(MODULE).vvp:	$(MODULE).v $(MODULE)_tb.v $(MODULE)_drivers.mem
	iverilog -DICARUS_VERILOG -DFROM_$(MODULE_CAPS) -g2012 -o $(MODULE).vvp $(MODULE)_tb.v

open:	$(MODULE).vcd
	gtkwave $(MODULE).vcd --autosavename &

clean:
	rm -rf $(MODULE).vvp
	rm -rf $(MODULE).vcd

force:
	touch $(MODULE)_tb.v
	make
