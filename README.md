# bullseye

![Pulls](https://img.shields.io/docker/pulls/mkovac/bullseye.svg)
![Stars](https://img.shields.io/docker/stars/mkovac/bullseye.svg)

The [Debian](https://debian.org/) [Bullseye](https://wiki.debian.org/DebianBullseye)
[container image](https://hub.docker.com/r/mkovac/bullseye/) with few handy
utilities, utf8 locales...

This image is built daily and in case of any security update, the list of
packages is updated, commited and this triggers update of docker-hub image
and all dependant images.

## Quick Usage

Run prebuilt:

    $ docker run --rm -ti mkovac/bullseye bash

Or you can clone & build, run `bash` to explore:

    $ git clone https://github.com/multicast/docker-bullseye
    $ cd docker-bullseye
    $ docker build -t bullseye .
    $ docker run --rm -ti bullseye bash

Since the image is intended to be used as base image, I suppose more common usage
would be in your own `Dockerfile` in the form:

    FROM mkovac/bullseye:latest
    ...

## Build-time options

You can `export` environment variables found in the following list:

  * `ftp_proxy`
  * `http_proxy`
  * `https_proxy`

The values for these variables will not end up in the resulting image.

## Run-time options

You can define environment variables via `--env` argument found in the following list:

  * `ftp_proxy`
  * `http_proxy`
  * `https_proxy`
  * `BASE_DEBUG`
      * zero to higher numbers - to get more and more verbose
  * `BASE_NOEXIT`
      * set to 1 not to exit on startup errors

The apt proxy configuration will use above variables.

Further customization of container startup can be done using script mounted
to `/etc/entrypoint.d/NN-your-script-name`, and it gets executed by default
entry point script. See [examples](build/etc/entrypoint.d).

# Packages

    Desired=Unknown/Install/Remove/Purge/Hold
    | Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend
    |/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)
    ||/ Name                       Version                        Architecture Description
    +++-==========================-==============================-============-===============================================================================
    ii  adduser                    3.118                          all          add and remove users and groups
    ii  apt                        2.2.4                          amd64        commandline package manager
    ii  apt-utils                  2.2.4                          amd64        package management related utility programs
    ii  base-files                 11.1+deb11u3                   amd64        Debian base system miscellaneous files
    ii  base-passwd                3.5.51                         amd64        Debian base system master password and group files
    ii  bash                       5.1-2+b3                       amd64        GNU Bourne Again SHell
    ii  bsdutils                   1:2.36.1-8+deb11u1             amd64        basic utilities from 4.4BSD-Lite
    ii  ca-certificates            20210119                       all          Common CA certificates
    ii  coreutils                  8.32-4+b1                      amd64        GNU core utilities
    ii  curl                       7.74.0-1.3+deb11u1             amd64        command line tool for transferring data with URL syntax
    ii  dash                       0.5.11+git20200708+dd9ef66-5   amd64        POSIX-compliant shell
    ii  debconf                    1.5.77                         all          Debian configuration management system
    ii  debian-archive-keyring     2021.1.1                       all          GnuPG archive keys of the Debian archive
    ii  debianutils                4.11.2                         amd64        Miscellaneous utilities specific to Debian
    ii  di                         4.48-1                         amd64        advanced df like disk information utility
    ii  diffutils                  1:3.7-5                        amd64        File comparison utilities
    ii  dpkg                       1.20.10                        amd64        Debian package management system
    ii  e2fsprogs                  1.46.2-2                       amd64        ext2/ext3/ext4 file system utilities
    ii  etckeeper                  1.18.16-1                      all          store /etc in git, mercurial, brz or darcs
    ii  findutils                  4.8.0-1                        amd64        utilities for finding files--find, xargs
    ii  gcc-10-base:amd64          10.2.1-6                       amd64        GCC, the GNU Compiler Collection (base package)
    ii  gcc-9-base:amd64           9.3.0-22                       amd64        GCC, the GNU Compiler Collection (base package)
    ii  git                        1:2.30.2-1                     amd64        fast, scalable, distributed revision control system
    ii  git-man                    1:2.30.2-1                     all          fast, scalable, distributed revision control system (manual pages)
    ii  gpgv                       2.2.27-2+deb11u1               amd64        GNU privacy guard - signature verification tool
    ii  grep                       3.6-1                          amd64        GNU grep, egrep and fgrep
    ii  gzip                       1.10-4+deb11u1                 amd64        GNU compression utilities
    ii  hostname                   3.23                           amd64        utility to set/show the host name or domain name
    ii  init-system-helpers        1.60                           all          helper tools for all init systems
    ii  iproute2                   5.10.0-4                       amd64        networking and traffic control tools
    ii  iputils-ping               3:20210202-1                   amd64        Tools to test the reachability of network hosts
    ii  joe                        4.6-1+b1                       amd64        user friendly full screen text editor
    ii  less                       551-2                          amd64        pager program similar to more
    ii  libacl1:amd64              2.2.53-10                      amd64        access control list - shared library
    ii  libapt-pkg6.0:amd64        2.2.4                          amd64        package management runtime library
    ii  libattr1:amd64             1:2.4.48-6                     amd64        extended attribute handling - shared library
    ii  libaudit-common            1:3.0-2                        all          Dynamic library for security auditing - common files
    ii  libaudit1:amd64            1:3.0-2                        amd64        Dynamic library for security auditing
    ii  libblkid1:amd64            2.36.1-8+deb11u1               amd64        block device ID library
    ii  libbpf0:amd64              1:0.3-2                        amd64        eBPF helper library (shared library)
    ii  libbrotli1:amd64           1.0.9-2+b2                     amd64        library implementing brotli encoder and decoder (shared libraries)
    ii  libbsd0:amd64              0.11.3-1                       amd64        utility functions from BSD systems - shared library
    ii  libbz2-1.0:amd64           1.0.8-4                        amd64        high-quality block-sorting file compressor library - runtime
    ii  libc-bin                   2.31-13+deb11u3                amd64        GNU C Library: Binaries
    ii  libc-l10n                  2.31-13+deb11u3                all          GNU C Library: localization files
    ii  libc6:amd64                2.31-13+deb11u3                amd64        GNU C Library: Shared libraries
    ii  libcap-ng0:amd64           0.7.9-2.2+b1                   amd64        An alternate POSIX capabilities library
    ii  libcap2:amd64              1:2.44-1                       amd64        POSIX 1003.1e capabilities (library)
    ii  libcap2-bin                1:2.44-1                       amd64        POSIX 1003.1e capabilities (utilities)
    ii  libcom-err2:amd64          1.46.2-2                       amd64        common error description library
    ii  libcrypt1:amd64            1:4.4.18-4                     amd64        libcrypt shared library
    ii  libcurl3-gnutls:amd64      7.74.0-1.3+deb11u1             amd64        easy-to-use client-side URL transfer library (GnuTLS flavour)
    ii  libcurl4:amd64             7.74.0-1.3+deb11u1             amd64        easy-to-use client-side URL transfer library (OpenSSL flavour)
    ii  libdb5.3:amd64             5.3.28+dfsg1-0.8               amd64        Berkeley v5.3 Database Libraries [runtime]
    ii  libdebconfclient0:amd64    0.260                          amd64        Debian Configuration Management System (C-implementation library)
    ii  libelf1:amd64              0.183-1                        amd64        library to read and write ELF files
    ii  liberror-perl              0.17029-1                      all          Perl module for error/exception handling in an OO-ish way
    ii  libexpat1:amd64            2.2.10-2+deb11u3               amd64        XML parsing C library - runtime library
    ii  libext2fs2:amd64           1.46.2-2                       amd64        ext2/ext3/ext4 file system libraries
    ii  libffi7:amd64              3.3-6                          amd64        Foreign Function Interface library runtime
    ii  libgcc-s1:amd64            10.2.1-6                       amd64        GCC support library
    ii  libgcrypt20:amd64          1.8.7-6                        amd64        LGPL Crypto library - runtime library
    ii  libgdbm-compat4:amd64      1.19-2                         amd64        GNU dbm database routines (legacy support runtime version) 
    ii  libgdbm6:amd64             1.19-2                         amd64        GNU dbm database routines (runtime version) 
    ii  libgmp10:amd64             2:6.2.1+dfsg-1+deb11u1         amd64        Multiprecision arithmetic library
    ii  libgnutls30:amd64          3.7.1-5                        amd64        GNU TLS library - main runtime library
    ii  libgpg-error0:amd64        1.38-2                         amd64        GnuPG development runtime library
    ii  libgssapi-krb5-2:amd64     1.18.3-6+deb11u1               amd64        MIT Kerberos runtime libraries - krb5 GSS-API Mechanism
    ii  libhogweed6:amd64          3.7.3-1                        amd64        low level cryptographic library (public-key cryptos)
    ii  libidn2-0:amd64            2.3.0-5                        amd64        Internationalized domain names (IDNA2008/TR46) library
    ii  libk5crypto3:amd64         1.18.3-6+deb11u1               amd64        MIT Kerberos runtime libraries - Crypto Library
    ii  libkeyutils1:amd64         1.6.1-2                        amd64        Linux Key Management Utilities (library)
    ii  libkrb5-3:amd64            1.18.3-6+deb11u1               amd64        MIT Kerberos runtime libraries
    ii  libkrb5support0:amd64      1.18.3-6+deb11u1               amd64        MIT Kerberos runtime libraries - Support library
    ii  libldap-2.4-2:amd64        2.4.57+dfsg-3+deb11u1          amd64        OpenLDAP libraries
    ii  liblz4-1:amd64             1.9.3-2                        amd64        Fast LZ compression algorithm library - runtime
    ii  liblzma5:amd64             5.2.5-2.1~deb11u1              amd64        XZ-format compression library
    ii  libmd0:amd64               1.0.3-3                        amd64        message digest functions from BSD systems - shared library
    ii  libmnl0:amd64              1.0.4-3                        amd64        minimalistic Netlink communication library
    ii  libmount1:amd64            2.36.1-8+deb11u1               amd64        device mounting library
    ii  libmpdec3:amd64            2.5.1-1                        amd64        library for decimal floating point arithmetic (runtime library)
    ii  libncurses6:amd64          6.2+20201114-2                 amd64        shared libraries for terminal handling
    ii  libncursesw6:amd64         6.2+20201114-2                 amd64        shared libraries for terminal handling (wide character support)
    ii  libnettle8:amd64           3.7.3-1                        amd64        low level cryptographic library (symmetric and one-way cryptos)
    ii  libnewt0.52:amd64          0.52.21-4+b3                   amd64        Not Erik's Windowing Toolkit - text mode windowing with slang
    ii  libnghttp2-14:amd64        1.43.0-1                       amd64        library implementing HTTP/2 protocol (shared library)
    ii  libnsl2:amd64              1.3.0-2                        amd64        Public client interface for NIS(YP) and NIS+
    ii  libp11-kit0:amd64          0.23.22-1                      amd64        library for loading and coordinating access to PKCS#11 modules - runtime
    ii  libpam-modules:amd64       1.4.0-9+deb11u1                amd64        Pluggable Authentication Modules for PAM
    ii  libpam-modules-bin         1.4.0-9+deb11u1                amd64        Pluggable Authentication Modules for PAM - helper binaries
    ii  libpam-runtime             1.4.0-9+deb11u1                all          Runtime support for the PAM library
    ii  libpam0g:amd64             1.4.0-9+deb11u1                amd64        Pluggable Authentication Modules library
    ii  libpcre2-8-0:amd64         10.36-2                        amd64        New Perl Compatible Regular Expression Library- 8 bit runtime files
    ii  libpcre3:amd64             2:8.39-13                      amd64        Old Perl 5 Compatible Regular Expression Library - runtime files
    ii  libperl5.32:amd64          5.32.1-4+deb11u2               amd64        shared Perl library
    ii  libpopt0:amd64             1.18-2                         amd64        lib for parsing cmdline parameters
    ii  libprocps8:amd64           2:3.3.17-5                     amd64        library for accessing process information from /proc
    ii  libpsl5:amd64              0.21.0-1.2                     amd64        Library for Public Suffix List (shared libraries)
    ii  libpython3-stdlib:amd64    3.9.2-3                        amd64        interactive high-level object-oriented language (default python3 version)
    ii  libpython3.9-minimal:amd64 3.9.2-1                        amd64        Minimal subset of the Python language (version 3.9)
    ii  libpython3.9-stdlib:amd64  3.9.2-1                        amd64        Interactive high-level object-oriented language (standard library, version 3.9)
    ii  libreadline8:amd64         8.1-1                          amd64        GNU readline and history libraries, run-time libraries
    ii  librtmp1:amd64             2.4+20151223.gitfa8646d.1-2+b2 amd64        toolkit for RTMP streams (shared library)
    ii  libsasl2-2:amd64           2.1.27+dfsg-2.1+deb11u1        amd64        Cyrus SASL - authentication abstraction library
    ii  libsasl2-modules-db:amd64  2.1.27+dfsg-2.1+deb11u1        amd64        Cyrus SASL - pluggable authentication modules (DB)
    ii  libseccomp2:amd64          2.5.1-1+deb11u1                amd64        high level interface to Linux seccomp filter
    ii  libselinux1:amd64          3.1-3                          amd64        SELinux runtime shared libraries
    ii  libsemanage-common         3.1-1                          all          Common files for SELinux policy management libraries
    ii  libsemanage1:amd64         3.1-1+b2                       amd64        SELinux policy management library
    ii  libsepol1:amd64            3.1-1                          amd64        SELinux library for manipulating binary security policies
    ii  libslang2:amd64            2.3.2-5                        amd64        S-Lang programming library - runtime version
    ii  libsmartcols1:amd64        2.36.1-8+deb11u1               amd64        smart column output alignment library
    ii  libsqlite3-0:amd64         3.34.1-3                       amd64        SQLite 3 shared library
    ii  libss2:amd64               1.46.2-2                       amd64        command-line interface parsing library
    ii  libssh2-1:amd64            1.9.0-2                        amd64        SSH2 client-side library
    ii  libssl1.1:amd64            1.1.1n-0+deb11u2               amd64        Secure Sockets Layer toolkit - shared libraries
    ii  libstdc++6:amd64           10.2.1-6                       amd64        GNU Standard C++ Library v3
    ii  libsystemd0:amd64          247.3-7                        amd64        systemd utility library
    ii  libtasn1-6:amd64           4.16.0-2                       amd64        Manage ASN.1 structures (runtime)
    ii  libtinfo6:amd64            6.2+20201114-2                 amd64        shared low-level terminfo library for terminal handling
    ii  libtirpc-common            1.3.1-1                        all          transport-independent RPC library - common files
    ii  libtirpc3:amd64            1.3.1-1                        amd64        transport-independent RPC library
    ii  libudev1:amd64             247.3-7                        amd64        libudev shared library
    ii  libunistring2:amd64        0.9.10-4                       amd64        Unicode string library for C
    ii  libuuid1:amd64             2.36.1-8+deb11u1               amd64        Universally Unique ID library
    ii  libxtables12:amd64         1.8.7-1                        amd64        netfilter xtables library
    ii  libxxhash0:amd64           0.8.0-2                        amd64        shared library for xxhash
    ii  libzstd1:amd64             1.4.8+dfsg-2.1                 amd64        fast lossless compression algorithm
    ii  localepurge                0.7.3.10                       all          reclaim disk space by removing unneeded localizations
    ii  locales                    2.31-13+deb11u3                all          GNU C Library: National Language (locale) data [support]
    ii  login                      1:4.8.1-1                      amd64        system login tools
    ii  logsave                    1.46.2-2                       amd64        save the output of a command in a log file
    ii  lsb-base                   11.1.0                         all          Linux Standard Base init script functionality
    ii  mawk                       1.3.4.20200120-2               amd64        Pattern scanning and text processing language
    ii  media-types                4.0.0                          all          List of standard media types and their usual file extension
    ii  mount                      2.36.1-8+deb11u1               amd64        tools for mounting and manipulating filesystems
    ii  ncurses-base               6.2+20201114-2                 all          basic terminal type definitions
    ii  ncurses-bin                6.2+20201114-2                 amd64        terminal-related programs and man pages
    ii  net-tools                  1.60+git20181103.0eebece-1     amd64        NET-3 networking toolkit
    ii  openssl                    1.1.1n-0+deb11u2               amd64        Secure Sockets Layer toolkit - cryptographic utility
    ii  passwd                     1:4.8.1-1                      amd64        change and administer password and group data
    ii  perl                       5.32.1-4+deb11u2               amd64        Larry Wall's Practical Extraction and Report Language
    ii  perl-base                  5.32.1-4+deb11u2               amd64        minimal Perl system
    ii  perl-modules-5.32          5.32.1-4+deb11u2               all          Core Perl modules
    ii  procps                     2:3.3.17-5                     amd64        /proc file system utilities
    ii  psmisc                     23.4-2                         amd64        utilities that use the proc file system
    ii  python3                    3.9.2-3                        amd64        interactive high-level object-oriented language (default python3 version)
    ii  python3-minimal            3.9.2-3                        amd64        minimal subset of the Python language (default python3 version)
    ii  python3.9                  3.9.2-1                        amd64        Interactive high-level object-oriented language (version 3.9)
    ii  python3.9-minimal          3.9.2-1                        amd64        Minimal subset of the Python language (version 3.9)
    ii  readline-common            8.1-1                          all          GNU readline and history libraries, common files
    ii  sed                        4.7-1                          amd64        GNU stream editor for filtering/transforming text
    ii  sensible-utils             0.0.14                         all          Utilities for sensible alternative selection
    ii  sysvinit-utils             2.96-7+deb11u1                 amd64        System-V-like utilities
    ii  tar                        1.34+dfsg-1                    amd64        GNU version of the tar archiving utility
    ii  tzdata                     2021a-1+deb11u4                all          time zone and daylight-saving time data
    ii  ucf                        3.0043                         all          Update Configuration File(s): preserve user changes to config files
    ii  unzip                      6.0-26                         amd64        De-archiver for .zip files
    ii  util-linux                 2.36.1-8+deb11u1               amd64        miscellaneous system utilities
    ii  whiptail                   0.52.21-4+b3                   amd64        Displays user-friendly dialog boxes from shell scripts
    ii  xtail                      2.1-8                          amd64        like "tail -f", but works on truncated files, directories, more
    ii  zlib1g:amd64               1:1.2.11.dfsg-2+deb11u1        amd64        compression library - runtime
