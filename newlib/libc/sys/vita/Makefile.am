## Process this file with automake to generate Makefile.in

AUTOMAKE_OPTIONS = cygnus

INCLUDES = $(NEWLIB_CFLAGS) $(CROSS_CFLAGS) $(TARGET_CFLAGS)

AM_CCASFLAGS = $(INCLUDES)

noinst_LIBRARIES = lib.a

SOCKET_OBJS = accept.o bind.o connect.o getpeername.o getsockname.o getsockopt.o listen.o recv.o recvfrom.o recvmsg.o send.o sendto.o sendmsg.o setsockopt.o shutdown.o socket.o netdb.o

lib_a_SOURCES = syscalls.c sbrk.c threading.c mlock.c io.c socket.c dup.c select.c netdb.c
lib_a_LIBADD = ${SOCKET_OBJS}
lib_a_CCASFLAGS = $(AM_CCASFLAGS)
lib_a_CFLAGS = $(AM_CFLAGS)

all-local: crt0.o

$(SOCKET_OBJS): socket.c netdb.c
	$(COMPILE) -DF_$* $< -c -o $@

ACLOCAL_AMFLAGS = -I ../../.. -I ../../../..
CONFIG_STATUS_DEPENDENCIES = $(newlib_basedir)/configure.host
