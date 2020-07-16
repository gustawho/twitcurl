# Hey Emacs, this is a -*- makefile -*-
# The twitcurl library.. a Makefile for OpenWRT
# Makefile-fu by John Boiles
# 28 September 2009

LIBNAME = twitcurl
SRC = $(LIBNAME).cpp
DESTDIR = 
INCLUDE_DIR = $(DESTDIR)/usr/include
LIBRARY_DIR = $(DESTDIR)/usr/lib

# Compiler flag to set the C Standard level.
# c89   - "ANSI" C
# gnu89 - c89 plus GCC extensions
# c99   - ISO C99 standard (not yet fully implemented)
# gnu99 - c99 plus GCC extensions
# CSTANDARD = -std=gnu99

# Place -D or -U options here
# CDEFS =

# Place -I options here
# CINCS = 

# CFLAGS =$(CDEFS) $(CINCS) $(CSTANDARD)

all: target

target: $(SRC) $(LIBNAME).h
	$(CC) -Wall -fPIC -c -I$(INCLUDE_DIR) $(SRC) oauthlib.cpp urlencode.cpp base64.cpp HMAC_SHA1.cpp SHA1.cpp

#clean project.
clean:
	rm -f lib$(LIBNAME)*.so.1.0
	rm -f $(LIBNAME).o
	rm -f *.o
	rm -f $(LIBRARY_DIR)/lib$(LIBNAME).so*

# Install library to local openwrt library directory
install: all
	install -m644 lib$(LIBNAME).so.1.0 $(LIBRARY_DIR)
	install -m644 $(LIBNAME).h $(INCLUDE_DIR)/
	install -m644 oauthlib.h $(INCLUDE_DIR)/
	ln -sf $(LIBRARY_DIR)/lib$(LIBNAME).so.1.0 $(LIBRARY_DIR)/lib$(LIBNAME).so
	ln -sf $(LIBRARY_DIR)/lib$(LIBNAME).so.1.0 $(LIBRARY_DIR)/lib$(LIBNAME).so.1
