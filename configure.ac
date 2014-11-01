AC_INIT([libbudgie], 1, [ikey@evolve-os.com], [libbudgie], [https://evolve-os.com/])
AM_INIT_AUTOMAKE([-Wno-portability no-dist-gzip dist-xz foreign subdir-objects])
AC_PROG_CC
AC_PROG_CC_STDC
LT_PREREQ(2.2)
AC_CONFIG_HEADERS([config.h])
AC_PREFIX_DEFAULT(/usr/local)
AM_SILENT_RULES([yes])
LT_INIT([disable-static])

GLIB_GSETTINGS

GETTEXT_PACKAGE=libbudgie
AC_SUBST(GETTEXT_PACKAGE)
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE, "$GETTEXT_PACKAGE",
                   [The prefix for our gettext translation domains.])

# Package requirements
PKG_CHECK_MODULES([GOBJECT], [gobject-2.0 >= 2.38.0])
PKG_CHECK_MODULES([GIO], [gio-2.0 >= 2.38.0])
PKG_CHECK_MODULES([GTK3], [gtk+-3.0 >= 3.10.0])

AC_ARG_ENABLE(demos, AS_HELP_STRING([--enable-demos], [enable demos @<:@default=no@:>@]),
	      [], [enable_demos=no])
AS_IF([test "x$enable_demos" = "xyes"],
	[AC_DEFINE([DEMOS], [1], [Building demos])],
	[])
AM_CONDITIONAL([BUILD_DEMOS], [test x$enable_demos = x"yes"])

AC_CONFIG_MACRO_DIR([m4])


AC_CONFIG_FILES([Makefile
                src/Makefile])
AC_OUTPUT

AC_MSG_RESULT([
        libbudgie $VERSION
        ========

        prefix:                 ${prefix}
        libdir:                 ${libdir}
        sysconfdir:             ${sysconfdir}
        exec_prefix:            ${exec_prefix}
        bindir:                 ${bindir}
        datarootdir:            ${datarootdir}

        compiler:               ${CC}
        cflags:                 ${CFLAGS}
        ldflags:                ${LDFLAGS}

        demos:                  ${enable_demos}

])
