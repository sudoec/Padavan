THISDIR := $(shell pwd)
VERSION := 1.5.0

BIN_PREFIX := xray-core-mipsle

all: 
	@echo "xray-core build ok!"

clean:
	@echo "xray-core clean ok!"

romfs:
	$(ROMFSINST) -S -p +x $(THISDIR)/$(BIN_PREFIX)-$(VERSION) /usr/bin/xray

