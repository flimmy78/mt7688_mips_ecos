#
# Makefile
#

#.EXPORT_ALL_VARIABLES:

include $(TOPDIR)/.config

EXTRA_CFLAGS += -I./include

ALL_OBJS = ./src/httpd.o ./src/tdate_parse.o  ./src/http_api.o


MODULE = $(shell pwd | sed "s/.*\///" ).o

all: $(MODULE)

include $(TOPDIR)/rules.mak

$(MODULE): $(ALL_OBJS:.o=.d)
	$(XLD) -r $(ENDIAN) -o $(MODULE) $(ALL_OBJS)

clean:
	rm $(MODULE) $(ALL_OBJS)


