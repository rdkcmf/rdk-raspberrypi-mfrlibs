##########################################################################
# If not stated otherwise in this file or this component's LICENSE
# file the following copyright and licenses apply:
#
# Copyright 2017 RDK Management
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
##########################################################################

# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.68])
AC_INIT([rdkmfrlibs], [1.0])
AC_CONFIG_SRCDIR([mfrlibs_rpi.c])

AM_INIT_AUTOMAKE([foreign])

# Checks for programs.
AC_PROG_CC

# Checks for libtool
LT_INIT

# Libs and cflags
RDKMFRLIB_LIBS=""
AC_SUBST(RDKMFRLIBS_LIBS)

RDKMFRLIBS_CFLAGS="-I$PKG_CONFIG_SYSROOT_DIR/usr/include/rdk/iarmmgrs-hal \
                           -I$PKG_CONFIG_SYSROOT_DIR/usr/include/rdk/iarmbus"
AC_SUBST(RDKMFRLIBS_CFLAGS)

# Checks for header files.
AC_CHECK_HEADERS([stdio.h stdlib.h string.h])

# Checks for typedefs, structures, and compiler characteristics.
# check for termal protection
AC_ARG_ENABLE([thermalprotection], [--enable-thermalprotection "Enable thermal protection"],
      [case "${enableval}" in
               yes) thermalprotection=true ;;
               no)  thermalprotection=false ;;
               *) AC_MSG_ERROR([bad value ${enableval} for thermal protection]) ;;
       esac], [thermalprotection=false])
AM_CONDITIONAL([THERMAL_PROTECTION_ENABLED], [test x$thermalprotection = xtrue])

# Checks for library functions.
AC_FUNC_MALLOC

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
