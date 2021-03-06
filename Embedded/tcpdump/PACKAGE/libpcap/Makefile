first_rule: all

all: build install

PACKAGE_NAME := libpcap-1.10.0
PACKAGE_DIR  := libpcap-1.10.0

# Configuration
PACKAGE_CONF := \
    --prefix=$(CURDIR)/../../OBJ/ \

test_directory:
	if [ ! -d $(CURDIR)/../../TARGET ]; then \
	   mkdir $(CURDIR)/../../TARGET/; \
	fi
	if [ -d $(CURDIR)/../../TARGET/$(PACKAGE_DIR) ]; then \
	       echo "Folder existed"; \
	else \
	       tar xvf $(CURDIR)/$(PACKAGE_NAME).tar.gz -C $(CURDIR)/../../TARGET/; \
	fi

build_lib: test_directory
	cd $(CURDIR)/../../TARGET/$(PACKAGE_DIR)/ && CC=aarch64-linux-gnu-gcc ./configure CFLAGS=-g $(PACKAGE_CONF) --host=aarch64-linux --target=aarch64-linux ; \

build: build_lib
	$(MAKE) ARCH=arm64 CROSS_COMPILE=/share/rlx/asdk-5.4.1-a53-EL-4.4-g2.23-a64nut-170801-r1/bin/aarch64-linux-  -C $(CURDIR)/../../TARGET/$(PACKAGE_DIR)/ all

install:
	$(MAKE) -C $(CURDIR)/../../TARGET/$(PACKAGE_DIR)/ install
	
config_rule:

clean_rule:

uninstall_rule:
