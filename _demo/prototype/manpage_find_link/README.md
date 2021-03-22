
## Example

run

``` sh
$ dpkg -L binutils-common | grep '/man/man.*/' | sort
```

show

```
/usr/share/man/man1/addr2line.1.gz
/usr/share/man/man1/ar.1.gz
/usr/share/man/man1/as.1.gz
/usr/share/man/man1/c++filt.1.gz
/usr/share/man/man1/dwp.1.gz
/usr/share/man/man1/elfedit.1.gz
/usr/share/man/man1/gold.1.gz
/usr/share/man/man1/gprof.1.gz
/usr/share/man/man1/ld.1.gz
/usr/share/man/man1/ld.bfd.1.gz
/usr/share/man/man1/ld.gold.1.gz
/usr/share/man/man1/nm.1.gz
/usr/share/man/man1/objcopy.1.gz
/usr/share/man/man1/objdump.1.gz
/usr/share/man/man1/ranlib.1.gz
/usr/share/man/man1/readelf.1.gz
/usr/share/man/man1/size.1.gz
/usr/share/man/man1/strings.1.gz
/usr/share/man/man1/strip.1.gz
```


run

``` sh
$ dpkg -L binutils-common | grep '/man/man.*/' | sort | awk -F '/' '{ print $6 }'
```

run

``` sh
$ dpkg -L binutils-common | grep '/man/man.*/' | sort | awk -F '/' '{ print $6 }' |  awk -F '.1.gz' '{ print $1 }'
```

run

``` sh
$ dpkg -L binutils-common | grep '/man/man.*/' | sort | awk -F '/' '{ print $6 }' |  awk -F '.1.gz' '{ print "https://manpages.ubuntu.com/manpages/focal/en/man1/"$1".1.html" }'
```

run

``` sh
$ dpkg -L binutils-common | grep '/man/man.*/' | sort | awk -F '/' '{ print $6 }' |  awk -F '.1.gz' '{ print "* $ man 1 ["$1"](https://manpages.ubuntu.com/manpages/focal/en/man1/"$1".1.html)" }'
```

## Reference

* https://samwhelp.github.io/book-ubuntu-basic-skill/book/content/manual/how-to-find-out-manpages-by-a-package.html
* https://www.debian.org/doc/manuals/debian-reference/ch02.en.html#_advanced_package_management_operations
