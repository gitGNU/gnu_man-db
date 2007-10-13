## Process this file with automake to produce Makefile.in
##
## Copyright (C) 1994, 1995 Graeme Wilford.
## Copyright (C) 2001, 2002, 2003, 2004, 2005, 2006, 2007 Colin Watson.
##
## This file is part of man-db.
##
## man-db is free software; you can redistribute it and/or modify it
## under the terms of the GNU General Public License as published by
## the Free Software Foundation; either version 2 of the License, or
## (at your option) any later version.
##
## man-db is distributed in the hope that it will be useful, but
## WITHOUT ANY WARRANTY; without even the implied warranty of
## MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
## GNU General Public License for more details.
##
## You should have received a copy of the GNU General Public License
## along with man-db; if not, write to the Free Software Foundation,
## Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301  USA

noinst_LIBRARIES = libman.a
dist_noinst_DATA = README

libman_a_CPPFLAGS = -I$(top_builddir)/include

libman_a_SOURCES = \
	ansidecl.h \
	appendstr.c \
	cleanup.c \
	cleanup.h \
	debug.c \
	decompress.c \
	decompress.h \
	error.c \
	error.h \
	getcwdalloc.c \
	getcwdalloc.h \
	hashtable.c \
	hashtable.h \
	linelength.c \
	linelength.h \
	pathsearch.c \
	pathsearch.h \
	pipeline.c \
	pipeline.h \
	tempfile.c \
	xmalloc.c \
	xsigaction.c \
	xstrdup.c \
	xstrndup.c \
	xstrsignal.c

## Headers that are used conditionally. Automake can't detect these itself.
libman_a_SOURCES += \
	flock.h \
	gettext.h \
	setenv.h

libman_a_LIBADD = $(LIBOBJS) $(ALLOCA)

# Provide header files missing from this system. (This should eventually be
# replaced with use of Gnulib, which has modules for all of these.)

BUILT_SOURCES = $(FNMATCH_H) $(GETOPT_H) $(GLOB_H)
MOSTLYCLEANFILES = fnmatch.h fnmatch.h-t getopt.h getopt.h-t glob.h glob.h-t
EXTRA_DIST = fnmatch_.h getopt_.h glob_.h

fnmatch.h: fnmatch_.h
	{ echo '/* DO NOT EDIT! GENERATED AUTOMATICALLY! */'; \
	  cat $<; \
	} > $@-t
	mv -f $@-t $@
getopt.h: getopt_.h
	{ echo '/* DO NOT EDIT! GENERATED AUTOMATICALLY! */'; \
	  cat $<; \
	} > $@-t
	mv -f $@-t $@
glob.h: glob_.h
	{ echo '/* DO NOT EDIT! GENERATED AUTOMATICALLY! */'; \
	  cat $<; \
	} > $@-t
	mv -f $@-t $@