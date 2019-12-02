# デフォルト動作

default :
	../HariboteOS/tolset/z_tools/make.exe img

# ファイル生成規則

ipl.bin : ipl.nas Makefile
	../HariboteOS/tolset/z_tools/nask.exe ipl.nas ipl.bin ipl.lst

helloos.img : ipl.bin Makefile
	../HariboteOS/tolset/z_tools/edimg.exe   imgin:../HariboteOS/tolset/z_tools/fdimg0at.tek \
		wbinimg src:ipl.bin len:512 from:0 to:0   imgout:helloos.img

# コマンド

asm :
	../HariboteOS/tolset/z_tools/make.exe -r ipl.bin

img :
	../HariboteOS/tolset/z_tools/make.exe -r helloos.img

run :
	../HariboteOS/tolset/z_tools/make.exe img
	copy helloos.img ..\HariboteOS\tolset\z_tools\qemu\fdimage0.bin
	../HariboteOS/tolset/z_tools/make.exe -C ../HariboteOS/tolset/z_tools/qemu

install :
	../HariboteOS/tolset/z_tools/make.exe img
	../HariboteOS/tolset/z_tools/imgtol.com w a: helloos.img

clean :
	-del ipl.bin
	-del ipl.lst

src_only :
	../HariboteOS/tolset/z_tools/make.exe clean
	-del helloos.img