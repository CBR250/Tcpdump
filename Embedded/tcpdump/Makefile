CURDIR=$(shell pwd)
PACKAGE_VERSION :=
PACKAGE_DIR :=
PACKAGE_CONF :=

first_rule: all

all: env build

env:
	@echo su auto.sh.
	sh env.sh

build:
	$(MAKE) -C $(CURDIR)/PACKAGE/libpcap      first_rule
	$(MAKE) -C $(CURDIR)/PACKAGE/tcpdump      first_rule
	
config_rule:

install_rule install:

clean_rule distclean clean:

uninstall_rule uninstall:

