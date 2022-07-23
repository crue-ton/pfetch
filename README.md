# pfetch

A pretty system information tool written in POSIX `sh`.

The goal of this project is to implement a simple system information tool in POSIX `sh` using features built into the language itself (*where possible*).

The source code is highly documented and I hope it will act as a learning resource for POSIX `sh` and simple information detection across various different operating systems.

If anything in the source code is unclear or is lacking in its explanation, open an issue. Sometimes you get too close to something and you fail to see the "bigger picture"!

```sh
➜ pfetch
    ___       goldie@KISS
   (.· |      os     KISS Linux
   (<> |      host   Lenovo YOGA 900-13ISK
  / __  \     kernel 5.3.1-coffee
 ( /  \ /|    uptime 6h 20m
_/\ __)/_)    pkgs   130
\/-____\/     memory 1721M / 7942M
```

## OS support

- **Haiku**
- **MacOS**
- **Minix**
- **Solaris**
- **BSD**
    - DragonflyBSD
    - FreeBSD
    - NetBSD
    - OpenBSD
- **Windows**
    - Windows subsystem for Linux.
- **Linux**
    - Alpine Linux
    - Arch Linux
    - Arco Linux
    - Artix Linux
    - CentOS
    - Debian
    - Elementary
    - Fedora
    - Gentoo
    - Guix
    - Hyperbola
    - KISS Linux
    - Linux Lite
    - Linux Mint
    - Mageia
    - Manjaro
    - MX Linux
    - NixOS
    - OpenSUSE
    - Parabola
    - Pop!\_OS
    - PureOS
    - Slackware
    - Ubuntu
    - Void Linux
    - Other distributions are supported with a generic penguin logo.

## TODO

- [ ] Add optional and additional information detection.
    - [ ] Terminal Emulator ([#12](https://github.com/dylanaraps/pfetch/pull/12))
        - The way I implement this in `neofetch` is interesting.
- [ ] Expand operating system support.
    - [ ] Android
    - [ ] iOS
    - [ ] AIX ([#7](https://github.com/dylanaraps/pfetch/issues/7))
    - [ ] IRIX ([#8](https://github.com/dylanaraps/pfetch/issues/8))
    - [ ] FreeMiNT ([#9](https://github.com/dylanaraps/pfetch/issues/9))
    - [ ] Windows ([#10](https://github.com/dylanaraps/pfetch/issues/10))
        - [ ] CYGWIN
        - [ ] MSYS
        - [ ] MINGW

## Configuration

`pfetch` is configured through environment variables.

```sh
# Which information to display.
# NOTE: If 'ascii' will be used, it must come first.
# Default: first example below
# Valid: space separated string
#
# OFF by default: shell editor wm de palette
PF_INFO="ascii title os host kernel uptime pkgs memory"

# Example: Only ASCII.
PF_INFO="ascii"

# Example: Only Information.
PF_INFO="title os host kernel uptime pkgs memory"

# Separator between info name and info data.
# Default: unset
# Valid: string
PF_SEP=":"

# Color of info names:
# Default: unset (auto)
# Valid: 0-9
PF_COL1=4

# Color of info data:
# Default: unset (auto)
# Valid: 0-9
PF_COL2=7

# Color of title data:
# Default: unset (auto)
# Valid: 0-9
PF_COL3=1

# Alignment padding.
# Default: unset (auto)
# Valid: int
PF_ALIGN=""

# Which ascii art to use.
# Default: unset (auto)
# Valid: string
PF_ASCII="openbsd"

# The below environment variables control more
# than just 'pfetch' and can be passed using
# 'HOSTNAME=cool_pc pfetch' to restrict their
# usage solely to 'pfetch'.

# Which user to display.
USER=""

# Which hostname to display.
HOSTNAME=""

# Which editor to display.
EDITOR=""

# Which shell to display.
SHELL=""

# Which desktop environment to display.
XDG_CURRENT_DESKTOP=""
```

## Credit

- [ufetch](https://gitlab.com/jschx/ufetch): Lots of ASCII logos.
    - Contrary to the belief of a certain youtuber, `pfetch` shares **zero** code with `ufetch`. Only some of the ASCII logos were used.
