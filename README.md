![img](http://ecx.images-amazon.com/images/I/51AH1J4Wo9L._SX394_BO1,204,203,200_.jpg)
# Professional Assembly Language

# OS 
ubuntu-gnome-16.04-desktop-amd64
# Prerequisites
sudo apt install gcc-multilib

# Book
[code](https://github.com/ELWIN-MAO/pal)
[book](https://github.com/IammyselfYBX/GAS-Professional-Assembly-Language)
在线:http://www.dgt-factory.com/uploads/2018/10/1026/%E6%B1%87%E7%BC%96%E8%AF%AD%E8%A8%80%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1(%E7%BE%8E)%E5%B8%83%E9%B2%81%E5%A7%86%20%E7%9D%80,%E9%A9%AC%E6%9C%9D%E6%99%96%20%E7%AD%89....pdf

# Command
```bash
$ bash
>>> as --32 -o xxx.o xxx.s
>>> ld -m elf_i386 -o xxx xxx.o
>>> ld -m elf_i386 -dynamic-linker /lib32/ld-linux.so.2 -o xxx xxx.o /lib32/libc.so.6
```
