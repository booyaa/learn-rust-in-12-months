default: run

.PHONY: default build run clean demo

build:
	mkdir -p build
	nasm -f bin boot_hello.asm -o build/boot_hello.bin

run: build
	qemu-system-i386 -curses -fda build/boot_hello.bin

clean:
	rm -rf build

demo:
	@docker run -it --rm -v "${PWD}":/src -w /src intermezzos-docker:latest bash -c 'make'
