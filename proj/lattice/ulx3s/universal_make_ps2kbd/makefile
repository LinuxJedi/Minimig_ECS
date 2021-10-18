# ******* project, board and chip name *******
PROJECT = minimig_ps2kbd
BOARD = ulx3s
# 25 45 85
FPGA_SIZE = 25
FPGA_PACKAGE = 6bg381c
# config flash: 1:SPI (standard), 4:QSPI (quad)
FLASH_SPI = 4
# chip: is25lp032d is25lp128f s25fl164k
FLASH_CHIP = is25lp128f

# ******* design files *******
CLK0_NAME = clk_minimig
CLK0_FILE_NAME = ../../../../rtl_emard/lattice/ulx3s/clocks/$(CLK0_NAME).v
CLK0_OPTIONS = \
  --module=$(CLK0_NAME) \
  --clkin=25 \
  --clkout0_name=clk_140 --clkout0=140.625 \
  --clkout1_name=clk_112 --clkout1=112.5 \
  --clkout2_name=clk_28  --clkout2=28.125 \
  --clkout3_name=clk_7   --clkout3=7.03125

CLK1_NAME = clk_ramusb
CLK1_FILE_NAME = ../../../../rtl_emard/lattice/ulx3s/clocks/$(CLK1_NAME).v
CLK1_OPTIONS = \
  --module=$(CLK1_NAME) \
  --clkin=25 \
  --clkout0_name=clk_112        --clkout0=112.5 \
  --clkout1_name=clk_112_120deg --clkout1=112.5 --phase1=120 \
  --clkout2_name=clk_6          --clkout2=6

CLK2_NAME = clk_usb
CLK2_FILE_NAME = ../../../../rtl_emard/lattice/ulx3s/clocks/$(CLK2_NAME).v
CLK2_OPTIONS = \
  --module=$(CLK2_NAME) \
  --clkin=25 \
  --clkout0_name=clk_240         --clkout0=240 \
  --clkout1_name=clk_48          --clkout1=48 \
  --clkout2_name=clk_6           --clkout2=6

# ******* design files *******
# current boards v3.0.3 v2.1.2
CONSTRAINTS = ../../constraints/ulx3s_v20.lpf
# first ULX3S prototypes v1.7 boards with patched ESP32 connection
#CONSTRAINTS = ../../constraints/ulx3s_v17p.lpf

TOP_MODULE_FILE = ../../../../rtl_emard/lattice/ulx3s/top/amiga_ulx3s_ps2kbd.vhd
# usually all toplevels have the same top module name
TOP_MODULE = amiga_ulx3s

include files.mk

#STRATEGY = ../../../../Minimig_ECS/Area2.sty
STRATEGY = ../../../../Minimig_ECS/Minimig1.sty

SCRIPTS = ../../include/scripts
include $(SCRIPTS)/trellis_path.mk
include $(SCRIPTS)/diamond_path.mk
include $(SCRIPTS)/diamond_main.mk
