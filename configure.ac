AC_INIT([musica],
        [0.0.1],
        [demfuhlseine-mail@gmx.de])

AM_INIT_AUTOMAKE([-Wall -Werror foreign no-dependencies subdir-objects])
AC_CONFIG_HEADER([config.h])
AC_CONFIG_MACRO_DIR([m4])
AC_PROG_CC
AC_LANG(C)
AM_PROG_AR

# Libraries
# FFTW3
AC_ARG_WITH([fftw3_inc],
            [AC_HELP_STRING([--with-fftw3-inc=DIR],
                            [FFTW3 include directory])],
            [CFLAGS="-I${withval} ${CFLAGS}"])
AC_ARG_WITH([fftw3_lib],
            [AC_HELP_STRING([--with-fftw3-lib=DIR],
                            [FFTW3 lib directory])],
            [LDFLAGS="-L$withval $LDFLAGS"])
AC_ARG_WITH([fftw3],
            [AC_HELP_STRING([--with-fftw3=DIR],
                            [FFTW3 install directory])],
            [
            if test -z "$with_fftw3_inc" -a -z "$with_fftw3_lib" ; then
               CPPFLAGS="-I$withval/include $CPPFLAGS"
               LDFLAGS="-L$withval/lib $LDFLAGS"
            else
               AC_MSG_FAILURE([Do not use --with-fftw3 and --with-fftw3-inc/--with-fftw3-lib options simultaneously.])
            fi])
AC_CHECK_LIB([fftw3],
             [fftw_plan_dft_r2c_1d],
             [],
             [AC_MSG_FAILURE([unable to find FFTW3 library])])

# SDL2
AC_ARG_WITH([sdl2_inc],
            [AC_HELP_STRING([--with-sdl2-inc=DIR],
                            [SDL2 include directory])],
            [CFLAGS="-I${withval} ${CFLAGS}"])
AC_ARG_WITH([sdl2_lib],
            [AC_HELP_STRING([--with-sdl2-lib=DIR],
                            [SDL2 lib directory])],
            [LDFLAGS="-L$withval $LDFLAGS"])
AC_ARG_WITH([sdl2],
            [AC_HELP_STRING([--with-sdl2=DIR],
                            [SDL2 install directory])],
            [
            if test -z "$with_sdl2_inc" -a -z "$with_sdl2_lib" ; then
               CPPFLAGS="-I$withval/include $CPPFLAGS"
               LDFLAGS="-L$withval/lib $LDFLAGS"
            else
               AC_MSG_FAILURE([Do not use --with-sdl2 and --with-sdl2-inc/--with-sdl2-lib options simultaneously.])
            fi])
AC_CHECK_LIB([SDL2],
             [SDL_Init],
             [],
             [AC_MSG_FAILURE([unable to find SDL2 library])])

AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([src/Makefile])

AC_OUTPUT
