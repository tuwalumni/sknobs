INSTALL_LIB=lib64

build: sknobs.pm sknobs_wrap.c sknobs.mk
	make -f sknobs.mk

test:
	make -f sknobs.mk test

install:
	make -f sknobs.mk install

sknobs.pm sknobs_wrap.c: sknobs.i
	swig -perl5 sknobs.i

sknobs.mk: Makefile.PL
	perl Makefile.PL INSTALLSITEARCH=${PREFIX}/${ARCH}/${INSTALL_LIB}/perl

clean:
	if [ -f sknobs.mk ]; then make -f sknobs.mk clean; fi
	if [ -f sknobs.pm ]; then rm sknobs.pm; fi
	if [ -f sknobs_wrap.c ]; then rm sknobs_wrap.c; fi
	if [ -f sknobs.mk.old ]; then rm sknobs.mk.old; fi
