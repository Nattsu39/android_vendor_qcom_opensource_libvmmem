AM_CPPFLAGS := \
    -W \
    -Wall \
    -Wextra \
    -Wunused
ACLOCAL_AMFLAGS = -I m4


libvmmem_sources = vmmem.cpp vmmem_wrapper.cpp

# Build libvmmem.so
lib_LTLIBRARIES = libvmmem.la

libvmmem_la_SOURCES := $(libvmmem_sources)
libvmmem_la_CPPFLAGS := $(AM_CPPFLAGS) -Wno-error=pointer-to-int-cast

# GCC interprets = (equals sign) as a path relative to sysroot
libvmmem_la_CPPFLAGS += @LIBBASE_CFLAGS@ -I =${includedir}/vmmem
libvmmem_la_LDFLAGS := @LIBBASE_LIBS@

pkgconfigdir := $(libdir)/pkgconfig
pkgconfig_DATA := libvmmem.pc
EXTRA_DIST := $(pkgconfig_DATA)
