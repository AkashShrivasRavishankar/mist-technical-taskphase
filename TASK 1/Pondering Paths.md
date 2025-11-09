# Module Name
Linux Luminarium
## Challenge Name
The Root

### Solve
**Flag:** `pwn.college{YRCHz7B1s2bSOcgOC_SJHFyAOR1.QX4cTO0wCOzYDN0EzW}`

I had looked into commands such as cd, pwd and ls. and it was provided that we had to view the pwn file in the root directory.
so initially i was just going through directories and trying to spot pwn using cd to go through directories and later on just using ls for the paths. i tried using cat pwn but i was a bit confused as it didn't seem like the key, so i tried using cd but i realised i made a mistake by putting / before bin later on, and the bin folder was huge. so i thought i was overcomplicating things and copy pasted the hint given from cat pwn. then it just worked out!

```bash
hacker@paths~the-root:~$ cd /
hacker@paths~the-root:/$ pwd
/
hacker@paths~the-root:/$ cd pwn
bash: cd: pwn: Not a directory
hacker@paths~the-root:/$ cd /pwn
bash: cd: /pwn: Not a directory
hacker@paths~the-root:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   pwn   run   srv  tmp  var
boot  dev        flag  lib   lib64  media   nix  proc  root  sbin  sys  usr
hacker@paths~the-root:/$ cd pwn
bash: cd: pwn: Not a directory
hacker@paths~the-root:/$ cat pwn
#!/bin/bash

/challenge/.pwn
hacker@paths~the-root:/$ cd /bin/bash/challenge
bash: cd: /bin/bash/challenge: Not a directory
hacker@paths~the-root:/$ cd bin
hacker@paths~the-root:/bin$ cd bash
bash: cd: bash: Not a directory
hacker@paths~the-root:/bin$ ls
 7z                                   givaro-makefile                    php-cgi
 7za                                  glib-compile-resources             php-cgi7.4
 7zr                                  glib-compile-schemas               php7.4
 QuadraticSieve                       glib-genmarshal                    pic
 R                                    glib-gettextize                    piconv
 Rscript                              glib-mkenums                       pidof
 Singular                             glow                               pidstat
 X11                                  gnome-text-editor                  ping
'['                                   gnome-www-browser                  ping4
 aarch64-linux-gnu-addr2line          gobject-query                      ping6
 aarch64-linux-gnu-ar                 gold                               pinky
 aarch64-linux-gnu-as                 gp                                 pip
 aarch64-linux-gnu-c++filt            gp-2.11                            pip3
 aarch64-linux-gnu-cpp                gpasswd                            pkg-config
 aarch64-linux-gnu-cpp-9              gpg-zip                            pkill
 aarch64-linux-gnu-dwp                gpgcompose                         pl2pm
 aarch64-linux-gnu-elfedit            gpgparsemail                       pl2wam
 aarch64-linux-gnu-gcc                gpgsplit                           pldd
 aarch64-linux-gnu-gcc-9              gpgtar                             plt-games
 aarch64-linux-gnu-gcc-ar             gpgv                               plt-help
 aarch64-linux-gnu-gcc-ar-9           gpic                               plt-r5rs
 aarch64-linux-gnu-gcc-nm             gplc                               plt-r6rs
 aarch64-linux-gnu-gcc-nm-9           gprof                              plt-web-server
 aarch64-linux-gnu-gcc-ranlib         gprolog                            pmap
 aarch64-linux-gnu-gcc-ranlib-9       gracket                            pod2html
 aarch64-linux-gnu-gcov               gracket-text                       pod2man
 aarch64-linux-gnu-gcov-9             grep                               pod2text
 aarch64-linux-gnu-gcov-dump          gresource                          pod2usage
 aarch64-linux-gnu-gcov-dump-9        groff                              podchecker
 aarch64-linux-gnu-gcov-tool          grog                               podselect
 aarch64-linux-gnu-gcov-tool-9        grops                              poly-11d.x
 aarch64-linux-gnu-gprof              grotty                             poly-4d.x
 aarch64-linux-gnu-ld                 groups                             poly-5d.x
 aarch64-linux-gnu-ld.bfd             gsettings                          poly-6d.x
 aarch64-linux-gnu-ld.gold            gtbl                               poly.x
 aarch64-linux-gnu-nm                 gtester                            pr
 aarch64-linux-gnu-objcopy            gtester-report                     preconv
 aarch64-linux-gnu-objdump            gtk-update-icon-cache              prefcnt
 aarch64-linux-gnu-ranlib             gunzip                             print
 aarch64-linux-gnu-readelf            gzexe                              printenv
 aarch64-linux-gnu-size               gzip                               printerbanner
 aarch64-linux-gnu-strings            h2ph                               printf
 aarch64-linux-gnu-strip              h2xs                               prlimit
 ab                                   hd                                 procan
 addpart                              head                               prolog
 addr2line                            helpztags                          prove
 ag                                   hexdump                            prtstat
 apropos                              hexedit                            ps
 apt                                  hexgplc                            psbook
 apt-cache                            hostid                             psjoin
 apt-cdrom                            hostname                           pslog
 apt-config                           hostnamectl                        psmerge
 apt-get                              htcacheclean                       psnup
 apt-key                              htdbm                              psresize
 apt-mark                             htdigest                           psselect
 ar                                   htpasswd                           pstops
 arch                                 i386                               pstree
 as                                   i686-linux-gnu-pkg-config          pstree.x11
 asan_symbolize                       ibd2sdi                            ptar
 asan_symbolize-10                    icas                               ptardiff
 autoconf                             icdiff                             ptargrep
 autoexpect                           iconv                              ptx
 autoheader                           id                                 pwd
 autom4te                             ifnames                            pwdx
 automat-visualize3                   includeres                         py.test-3
 autopasswd                           infocmp                            py3clean
 autoreconf                           infotocap                          py3compile
 autoscan                             innochecksum                       py3versions
 autoupdate                           install                            pybabel
 awk                                  install-info                       pybabel-python3
 b2sum                                instmodsh                          pydoc3
 base32                               ionice                             pydoc3.8
 base64                               iostat                             pygettext3
 basename                             ip                                 pygettext3.8
 bash                                 ipcmk                              pygmentize
 bashbug                              ipcrm                              pyhtmlizer3
 batcat                               ipcs                               pytest-3
 bc                                   ipdb3                              python
 binwalk                              iptables-xml                       python3
 bison                                ipython                            python3-config
 bison.yacc                           ipython3                           python3-futurize
 bootctl                              irb                                python3-pasteurize
 browse                               irb2.7                             python3.8
 bsd-from                             ischroot                           python3.8-config
 bsd-write                            isodump                            pyvenv
 btfdiff                              isoinfo                            qemu-aarch64
 bugpoint                             isovfy                             qemu-aarch64_be
 bugpoint-10                          ispell-wrapper                     qemu-alpha
 bundle2.7                            ivshmem-client                     qemu-arm
 bundler2.7                           ivshmem-server                     qemu-armeb
 bunzip2                              jar                                qemu-cris
 busctl                               jarsigner                          qemu-hppa
 bzcat                                java                               qemu-i386
 bzcmp                                javac                              qemu-img
 bzdiff                               javadoc                            qemu-io
 bzegrep                              javap                              qemu-m68k
 bzexe                                jcmd                               qemu-microblaze
 bzfgrep                              jconsole                           qemu-microblazeel
 bzgrep                               jdb                                qemu-mips
 bzip2                                jdeprscan                          qemu-mips64
 bzip2recover                         jdeps                              qemu-mips64el
 bzless                               jexec                              qemu-mipsel
 bzmore                               jfr                                qemu-mipsn32
 c++                                  jhsdb                              qemu-mipsn32el
 c++filt                              jimage                             qemu-nbd
 c89                                  jinfo                              qemu-nios2
 c89-gcc                              jjs                                qemu-or1k
 c99                                  jlink                              qemu-ppc
 c99-gcc                              jmap                               qemu-ppc64
 c_rehash                             jmod                               qemu-ppc64abi32
 cal                                  jmol                               qemu-ppc64le
 calendar                             join                               qemu-pr-helper
 callgrind_annotate                   journalctl                         qemu-riscv32
 callgrind_control                    jpackage                           qemu-riscv64
 captoinfo                            jps                                qemu-s390x
 cas_help                             jq                                 qemu-sh4
 cat                                  jrunscript                         qemu-sh4eb
 catchsegv                            jshell                             qemu-sparc
 catman                               json_pp                            qemu-sparc32plus
 cautious-launcher                    jstack                             qemu-sparc64
 cc                                   jstat                              qemu-system-i386
 cddexec                              jstatd                             qemu-system-x86_64
 cddexec_gmp                          kbxutil                            qemu-tilegx
 cftp3                                kernel-install                     qemu-x86_64
 cg_annotate                          keyctl                             qemu-xtensa
 cg_diff                              keytool                            qemu-xtensaeb
 cg_merge                             kibitz                             racc2.7
 chacl                                kill                               racc2y2.7
 chage                                killall                            racket
 chardet3                             kmod                               raco
 chardetect3                          kropr                              rake
 chattr                               last                               ranlib
 chcon                                lastb                              rbash
 checkgid                             lastlog                            rcp
 chfn                                 lcalc                              rdf2bin
 chgrp                                lcf                                rdf2com
 chkfont                              ld                                 rdf2ihx
 chmod                                ld.bfd                             rdf2ith
 choom                                ld.gold                            rdf2srec
 chown                                ldd                                rdfdump
 chrt                                 ldrdf                              rdflib
 chsh                                 less                               rdma
 cifsiostat                           lessecho                           rdoc
 ckeygen3                             lessfile                           rdoc2.7
 cksum                                lesskey                            rdx
 clang                                lesspipe                           readelf
 clang++                              lex                                readlink
 clang++-10                           lexgrog                            realpath
 clang-10                             libnetcfg                          red
 clang-cpp-10                         libtool                            rename.ul
 class-11d.x                          libtoolize                         renice
 class-4d.x                           link                               reset
 class-5d.x                           linux32                            resizepart
 class-6d.x                           linux64                            resolvectl
 class.x                              llc                                rev
 clear                                llc-10                             rgrep
 clear_console                        lli                                ri
 cmake                                lli-10                             ri2.7
 cmp                                  lli-child-target-10                rlogin
 codiff                               llvm-PerfectShuffle                rlogin-cwd
 col                                  llvm-PerfectShuffle-10             rm
 colcrt                               llvm-addr2line-10                  rmdir
 colrm                                llvm-ar                            rmid
 column                               llvm-ar-10                         rmiregistry
 comm                                 llvm-as                            rotatelogs
 compose                              llvm-as-10                         routef
 conch3                               llvm-bcanalyzer                    routel
 corelist                             llvm-bcanalyzer-10                 rpcgen
 cp                                   llvm-c-test                        rrsync
 cpack                                llvm-c-test-10                     rsh
 cpan                                 llvm-cat                           rst-buildhtml
 cpan5.30-x86_64-linux-gnu            llvm-cat-10                        rst2html
 cpio                                 llvm-cfi-verify                    rst2html4
 cpp                                  llvm-cfi-verify-10                 rst2html5
 cpp-9                                llvm-config                        rst2latex
 cryptdir                             llvm-config-10                     rst2man
 csplit                               llvm-cov                           rst2odt
 cstool                               llvm-cov-10                        rst2odt_prepstyles
 ctags                                llvm-cvtres                        rst2pseudoxml
 ctags.emacs                          llvm-cvtres-10                     rst2s5
 ctest                                llvm-cxxdump                       rst2xetex
 ctracer                              llvm-cxxdump-10                    rst2xml
 ctstat                               llvm-cxxfilt                       rstpep2html
 curl                                 llvm-cxxfilt-10                    rsync
 cut                                  llvm-cxxmap-10                     rtstat
 cvtsudoers                           llvm-diff                          rubiks_cubex
 cws-11d.x                            llvm-diff-10                       rubiks_dikcube
 cws-4d.x                             llvm-dis                           rubiks_optimal
 cws-5d.x                             llvm-dis-10                        ruby
 cws-6d.x                             llvm-dlltool                       ruby2.7
 cws.x                                llvm-dlltool-10                    run-mailcap
 cygdb3                               llvm-dwarfdump                     run-parts
 cysignals-CSI                        llvm-dwarfdump-10                  runcon
 cython3                              llvm-dwp                           rview
 dash                                 llvm-dwp-10                        rvim
 date                                 llvm-elfabi-10                     rzsh
 dbus-cleanup-sockets                 llvm-exegesis                      sadf
 dbus-daemon                          llvm-exegesis-10                   sage
 dbus-monitor                         llvm-extract                       sanstats
 dbus-run-session                     llvm-extract-10                    sanstats-10
 dbus-send                            llvm-ifs-10                        sar
 dbus-update-activation-environment   llvm-install-name-tool-10          sar.sysstat
 dbus-uuidgen                         llvm-jitlink-10                    savelog
 dd                                   llvm-lib                           scncopy
 deb-systemd-helper                   llvm-lib-10                        scp
 deb-systemd-invoke                   llvm-link                          screen
 debconf                              llvm-link-10                       scribble
 debconf-apt-progress                 llvm-lipo-10                       script
 debconf-communicate                  llvm-lto                           scriptreplay
 debconf-copydb                       llvm-lto-10                        sdiff
 debconf-escape                       llvm-lto2                          sed
 debconf-set-selections               llvm-lto2-10                       see
 debconf-show                         llvm-mc                            select-default-iwrap
 decryptdir                           llvm-mc-10                         select-editor
 delpart                              llvm-mca                           sem
 devdump                              llvm-mca-10                        sensible-browser
 df                                   llvm-modextract                    sensible-editor
 dh_autotools-dev_restoreconfig       llvm-modextract-10                 sensible-pager
 dh_autotools-dev_updateconfig        llvm-mt                            seq
 dh_installxmlcatalogs                llvm-mt-10                         serialver
 dh_numpy3                            llvm-nm                            setarch
 dh_sphinxdoc                         llvm-nm-10                         setfacl
 diff                                 llvm-objcopy                       setpriv
 diff3                                llvm-objcopy-10                    setsid
 dir                                  llvm-objdump                       setterm
 dircolors                            llvm-objdump-10                    setup-plt
 dirname                              llvm-opt-report                    sftp
 dirsplit                             llvm-opt-report-10                 sg
 dislocate                            llvm-pdbutil                       sh
 dmesg                                llvm-pdbutil-10                    sha1sum
 dnsdomainname                        llvm-profdata                      sha224sum
 domainname                           llvm-profdata-10                   sha256sum
 dpkg                                 llvm-ranlib                        sha384sum
 dpkg-architecture                    llvm-ranlib-10                     sha512sum
 dpkg-buildflags                      llvm-rc                            shasum
 dpkg-buildpackage                    llvm-rc-10                         showchar
 dpkg-checkbuilddeps                  llvm-readelf                       showfigfonts
 dpkg-deb                             llvm-readelf-10                    shred
 dpkg-distaddfile                     llvm-readobj                       shuf
 dpkg-divert                          llvm-readobj-10                    size
 dpkg-genbuildinfo                    llvm-reduce-10                     skill
 dpkg-genchanges                      llvm-rtdyld                        slabtop
 dpkg-gencontrol                      llvm-rtdyld-10                     slatex
 dpkg-gensymbols                      llvm-size                          sleep
 dpkg-maintscript-helper              llvm-size-10                       slideshow
 dpkg-mergechangelogs                 llvm-split                         slogin
 dpkg-name                            llvm-split-10                      snice
 dpkg-parsechangelog                  llvm-stress                        socat
 dpkg-query                           llvm-stress-10                     soelim
 dpkg-scanpackages                    llvm-strings                       sort
 dpkg-scansources                     llvm-strings-10                    sotruss
 dpkg-shlibdeps                       llvm-strip                         sphinx-apidoc
 dpkg-source                          llvm-strip-10                      sphinx-autogen
 dpkg-split                           llvm-symbolizer                    sphinx-build
 dpkg-statoverride                    llvm-symbolizer-10                 sphinx-quickstart
 dpkg-trigger                         llvm-tblgen                        splain
 dpkg-vendor                          llvm-tblgen-10                     split
 dreadnaut                            llvm-undname                       sprof
 drracket                             llvm-undname-10                    sql
 dsymutil                             llvm-xray                          sqldiff
 dsymutil-10                          llvm-xray-10                       sqlite3
 dtagnames                            ln                                 ss
 du                                   lnstat                             ssh
 dwp                                  locale                             ssh-add
 ebrowse                              locale-check                       ssh-agent
 ebrowse.emacs                        localectl                          ssh-argv0
 echo                                 localedef                          ssh-copy-id
 ecl                                  logger                             ssh-keygen
 ecl-config                           login                              ssh-keyscan
 ecm                                  loginctl                           stat
 ed                                   logname                            stdbuf
 edit                                 logresolve                         strace
 editor                               look                               strace-log-merge
 egrep                                lorder                             strfile
 elfedit                              lpunlock                           strings
 emacs                                ls                                 strip
 emacs-gtk                            lsattr                             stty
 emacsclient                          lsb_release                        su
 emacsclient.emacs                    lsblk                              sudo
 en_cas_help                          lscpu                              sudoedit
 enc2xs                               lsipc                              sudoreplay
 encguess                             lslocks                            sum
 env                                  lslogins                           swindle
 env_parallel                         lsmem                              symcryptrun
 env_parallel.bash                    lsmod                              sympow
 env_parallel.csh                     lsns                               sync
 env_parallel.fish                    lspgpot                            syscse
 env_parallel.ksh                     ltrace                             systemctl
 env_parallel.pdksh                   lzcat                              systemd
 env_parallel.tcsh                    lzcmp                              systemd-analyze
 env_parallel.zsh                     lzdiff                             systemd-ask-password
 epsffit                              lzegrep                            systemd-cat
 eqn                                  lzfgrep                            systemd-cgls
 erb                                  lzgrep                             systemd-cgtop
 erb2.7                               lzless                             systemd-delta
 es_cas_help                          lzma                               systemd-detect-virt
 etags                                lzmainfo                           systemd-escape
 etags.emacs                          lzmore                             systemd-id128
 eu-addr2line                         m17n-db                            systemd-inhibit
 eu-ar                                m4                                 systemd-machine-id-setup
 eu-elfcmp                            ma2asm                             systemd-mount
 eu-elfcompress                       mailmail3                          systemd-notify
 eu-elflint                           make                               systemd-path
 eu-findtextrel                       make-first-existing-target         systemd-resolve
 eu-make-debug-archive                man                                systemd-run
 eu-nm                                man-recode                         systemd-socket-activate
 eu-objdump                           mandb                              systemd-stdio-bridge
 eu-ranlib                            manpath                            systemd-sysusers
 eu-readelf                           mawk                               systemd-tmpfiles
 eu-size                              maxima-sage                        systemd-tty-ask-password-agent
 eu-stack                             mcookie                            systemd-umount
 eu-strings                           md5sum                             tabs
 eu-strip                             md5sum.textutils                   tac
 eu-unstrip                           mesg                               tachyon
 ex                                   migrate-pubring-from-classic-gpg   tachyon-nox
 exec-suid                            mkdir                              tail
 exiftool                             mkfifo                             tapestat
 expand                               mkisofs                            tar
 expect                               mknod                              taskset
 expect_autoexpect                    mksquashfs                         tbl
 expect_autopasswd                    mktemp                             tclsh8.6
 expect_cryptdir                      mkzftree                           tee
 expect_decryptdir                    more                               tempfile
 expect_dislocate                     mori-11d.x                         test
 expect_ftp-rfc                       mori-4d.x                          tex2mail
 expect_kibitz                        mori-5d.x                          tic
 expect_lpunlock                      mori-6d.x                          timed-read
 expect_mkpasswd                      mori.x                             timed-run
 expect_multixterm                    mount                              timedatectl
 expect_passmass                      mountpoint                         timeout
 expect_rftp                          mpstat                             tkconch3
 expect_rlogin-cwd                    mred                               tknewsbiff
 expect_timed-read                    mred-text                          tkpasswd
 expect_timed-run                     ms_print                           tload
 expect_tknewsbiff                    mt                                 tmux
 expect_tkpasswd                      mt-gnu                             toe
 expect_unbuffer                      mtrace                             top
 expect_weather                       multixterm                         touch
 expect_xkibitz                       mv                                 tput
 expect_xpstat                        mwrank                             tr
 expiry                               my_print_defaults                  trial3
 expr                                 myisam_ftdump                      troff
 extractres                           myisamchk                          true
 f2py3                                myisamlog                          truncate
 f2py3.8                              myisampack                         tset
 factor                               mysql                              tsort
 faillog                              mysql_config_editor                tty
 fallocate                            mysql_migrate_keyring              twist3
 false                                mysql_secure_installation          twistd3
 fc-cache                             mysql_ssl_rsa_setup                tzselect
 fc-cat                               mysql_tzinfo_to_sql                ucf
 fc-conflist                          mysql_upgrade                      ucfq
 fc-list                              mysqladmin                         ucfr
 fc-match                             mysqlanalyze                       ul
 fc-pattern                           mysqlbinlog                        umount
 fc-query                             mysqlcheck                         uname
 fc-scan                              mysqld_multi                       unbuffer
 fc-validate                          mysqld_safe                        uncompress
 fcgistarter                          mysqldump                          unexpand
 fflas-ffpack-config                  mysqldumpslow                      uniq
 fgrep                                mysqlimport                        unlink
 figlet                               mysqloptimize                      unlzma
 figlet-figlet                        mysqlpump                          unpack200
 figlist                              mysqlrepair                        unshare
 filan                                mysqlreport                        unsquashfs
 file                                 mysqlshow                          unstr
 fincore                              mysqlslap                          unxz
 find                                 mzc                                unzip
 findmnt                              mzpp                               unzipsfx
 finger                               mzscheme                           update-alternatives
 firefox                              mztext                             update-gap-workspace
 fish                                 namei                              update-mime-database
 fish_indent                          nasm                               uptime
 fish_key_reader                      nauty-NRswitchg                    upx
 fixdlsrps                            nauty-addedgeg                     upx-ucl
 fixfmps                              nauty-amtog                        users
 fixpsditps                           nauty-biplabg                      utmpdump
 fixpspps                             nauty-blisstog                     valgrind
 fixscribeps                          nauty-catg                         valgrind-di-server
 fixtpps                              nauty-checks6                      valgrind-listener
 fixwfwps                             nauty-complg                       valgrind.bin
 fixwpps                              nauty-converseg                    vdir
 fixwwps                              nauty-copyg                        verify-uselistorder
 flex                                 nauty-countg                       verify-uselistorder-10
 flex++                               nauty-cubhamg                      vgdb
 flock                                nauty-deledgeg                     vi
 fmt                                  nauty-delptg                       view
 fold                                 nauty-directg                      vim
 fr_cas_help                          nauty-dretodot                     vim.basic
 free                                 nauty-dretog                       vimdiff
 from                                 nauty-genbg                        vimtutor
 ftp-rfc                              nauty-genbgL                       virtfs-proxy-helper
 fullcircle                           nauty-geng                         vmstat
 funzip                               nauty-genquarticg                  w
 fuser                                nauty-genrang                      w.procps
 futurize                             nauty-genspecialg                  wall
 g++                                  nauty-gentourng                    wam2ma
 g++-9                                nauty-gentreeg                     watch
 gac                                  nauty-hamheuristic                 watchgnupg
 gap                                  nauty-labelg                       wc
 gap2deb                              nauty-linegraphg                   wdctl
 gapplication                         nauty-listg                        wget
 gcc                                  nauty-multig                       whatis
 gcc-9                                nauty-newedgeg                     whereis
 gcc-ar                               nauty-pickg                        which
 gcc-ar-9                             nauty-planarg                      whiptail
 gcc-nm                               nauty-ranlabg                      who
 gcc-nm-9                             nauty-shortg                       whoami
 gcc-ranlib                           nauty-showg                        write
 gcc-ranlib-9                         nauty-subdivideg                   x-www-browser
 gcore                                nauty-sumlines                     x86_64
 gcov                                 nauty-twohamg                      x86_64-linux-gnu-addr2line
 gcov-9                               nauty-vcolg                        x86_64-linux-gnu-ar
 gcov-dump                            nauty-watercluster2                x86_64-linux-gnu-as
 gcov-dump-9                          nawk                               x86_64-linux-gnu-c++filt
 gcov-tool                            nc                                 x86_64-linux-gnu-cpp
 gcov-tool-9                          nc.openbsd                         x86_64-linux-gnu-cpp-9
 gdb                                  ncal                               x86_64-linux-gnu-dwp
 gdb-add-index                        ncurses5-config                    x86_64-linux-gnu-elfedit
 gdb-multiarch                        ncurses6-config                    x86_64-linux-gnu-g++
 gdbserver                            ncursesw5-config                   x86_64-linux-gnu-g++-9
 gdbtui                               ncursesw6-config                   x86_64-linux-gnu-gcc
 gdbus                                ndisasm                            x86_64-linux-gnu-gcc-9
 gdbus-codegen                        nef-11d.x                          x86_64-linux-gnu-gcc-ar
 gedit                                nef-4d.x                           x86_64-linux-gnu-gcc-ar-9
 gem                                  nef-5d.x                           x86_64-linux-gnu-gcc-nm
 gem2.7                               nef-6d.x                           x86_64-linux-gnu-gcc-nm-9
 gencat                               nef.x                              x86_64-linux-gnu-gcc-ranlib
 genisoimage                          neqn                               x86_64-linux-gnu-gcc-ranlib-9
 geqn                                 netcat                             x86_64-linux-gnu-gcov
 getafm                               netstat                            x86_64-linux-gnu-gcov-9
 getconf                              networkctl                         x86_64-linux-gnu-gcov-dump
 geteltorito                          newgrp                             x86_64-linux-gnu-gcov-dump-9
 getent                               nice                               x86_64-linux-gnu-gcov-tool
 getfacl                              niceload                           x86_64-linux-gnu-gcov-tool-9
 getopt                               nisdomainname                      x86_64-linux-gnu-gold
 gfan                                 nl                                 x86_64-linux-gnu-gprof
 gfan_bases                           nm                                 x86_64-linux-gnu-ld
 gfan_buchberger                      nmap                               x86_64-linux-gnu-ld.bfd
 gfan_combinerays                     nohup                              x86_64-linux-gnu-ld.gold
 gfan_doesidealcontain                nosetests3                         x86_64-linux-gnu-nm
 gfan_fancommonrefinement             nping                              x86_64-linux-gnu-objcopy
 gfan_fanhomology                     nproc                              x86_64-linux-gnu-objdump
 gfan_fanisbalanced                   nroff                              x86_64-linux-gnu-pkg-config
 gfan_fanlink                         nsenter                            x86_64-linux-gnu-python3-config
 gfan_fanproduct                      nstat                              x86_64-linux-gnu-python3.8-config
 gfan_fansubfan                       numfmt                             x86_64-linux-gnu-ranlib
 gfan_genericlinearchange             nvim                               x86_64-linux-gnu-readelf
 gfan_groebnercone                    obj2yaml                           x86_64-linux-gnu-size
 gfan_groebnerfan                     obj2yaml-10                        x86_64-linux-gnu-strings
 gfan_homogeneityspace                objcopy                            x86_64-linux-gnu-strip
 gfan_homogenize                      objdump                            x86_64-pc-linux-gnu-pkg-config
 gfan_initialforms                    od                                 xargs
 gfan_interactive                     openssl                            xcas
 gfan_ismarkedgroebnerbasis           opt                                xdg-desktop-icon
 gfan_krulldimension                  opt-10                             xdg-desktop-menu
 gfan_latticeideal                    p7zip                              xdg-email
 gfan_leadingterms                    pack200                            xdg-icon-resource
 gfan_list                            pager                              xdg-mime
 gfan_markpolynomialset               pahole                             xdg-open
 gfan_minkowskisum                    paperconf                          xdg-screensaver
 gfan_minors                          parallel                           xdg-settings
 gfan_mixedvolume                     parcat                             xkibitz
 gfan_overintegers                    partx                              xpstat
 gfan_padic                           passmass                           xsubpp
 gfan_polynomialsetunion              passwd                             xxd
 gfan_render                          paste                              xz
 gfan_renderstaircase                 pasteurize                         xzcat
 gfan_resultantfan                    patch                              xzcmp
 gfan_saturation                      patchelf                           xzdiff
 gfan_secondaryfan                    pathchk                            xzegrep
 gfan_stats                           pcap-config                        xzfgrep
 gfan_substitute                      pcapdump                           xzgrep
 gfan_symmetries                      pcapip                             xzless
 gfan_tolatex                         pcappick                           xzmore
 gfan_topolyhedralfan                 pcapuc                             y2racc2.7
 gfan_tropicalbasis                   pcre-config                        yacc
 gfan_tropicalbruteforce              pcre2-config                       yaml2obj
 gfan_tropicalcurve                   pcre2grep                          yaml2obj-10
 gfan_tropicalevaluation              pcre2test                          yes
 gfan_tropicalfunction                pdb3                               ypdomainname
 gfan_tropicalhypersurface            pdb3.8                             zcat
 gfan_tropicalintersection            pdf-slatex                         zcmp
 gfan_tropicallifting                 pdwtags                            zdiff
 gfan_tropicallinearspace             peekfd                             zdump
 gfan_tropicalmultiplicity            perl                               zegrep
 gfan_tropicalrank                    perl5.30-x86_64-linux-gnu          zfgrep
 gfan_tropicalstartingcone            perl5.30.0                         zforce
 gfan_tropicaltraverse                perlbug                            zgrep
 gfan_tropicalweildivisor             perldoc                            zip
 gfan_version                         perlivp                            zipcloak
 giac                                 perlthanks                         zipdetails
 ginstall-info                        perror                             zipgrep
 gio                                  pfunct                             zipinfo
 gio-querymodules                     pgiac                              zipnote
 git                                  pglobal                            zipsplit
 git-icdiff                           pgrep                              zless
 git-receive-pack                     phar                               zmore
 git-shell                            phar.phar                          znew
 git-upload-archive                   phar.phar7.4                       zsh
 git-upload-pack                      phar7.4                            zsh5
 givaro-config                        php
hacker@paths~the-root:/bin$ #!/bin/bash

/challenge/.pwn
BOOM!!!
Here is your flag:
pwn.college{YRCHz7B1s2bSOcgOC_SJHFyAOR1.QX4cTO0wCOzYDN0EzW}
```

### New Learnings
Learnt how to access directories and view them.

### References 
Video given on Pondering paths on pwn.college


## Challenge Name
Program and absolute paths

### Solve
**Flag:** `pwn.college{QLledqyOhUVbVoeya380-AmDYG1.QX1QTN0wCOzYDN0EzW}`

I realized I did the last challenge by mistake. I was a bit confused on how to execute a file before starting the challenge so I searched it up. I was thinking that just like cd,ls,or pwd there must be a fancy command name for running something then figured out you just directly write the directory name. 

```bash
hacker@paths~program-and-absolute-paths:~$ cd /
hacker@paths~program-and-absolute-paths:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{QLledqyOhUVbVoeya380-AmDYG1.QX1QTN0wCOzYDN0EzW}
```

### New Learnings
Learnt how to execute a file from the absolute paths.

### References 
Video given on Pondering paths on pwn.college, and google for finding out how to execute a file



## Challenge Name
Position thy self

### Solve
**Flag:** `pwn.college{gJwgapIxXwfljllKO5VrZIrTOiq.QX2QTN0wCOzYDN0EzW}`

I was trying to change my directory to challenge/run and then realised that in the question it was mentioned that there's a specific directory from where we have to run the code. I had used ls by then and that's when it struck me, so I tried executing the file to find the desired path and then rerun the execution and it worked like a charm. I'm still getting used to changing directories as sometimes i miss a slash and get confused.

```bash
PS C:\Users\HP> ssh -i key hacker@dojo.pwn.college
Connected!
hacker@paths~position-thy-self:~$ cd /challenge
hacker@paths~position-thy-self:/challenge$ /run
bash: /run: Is a directory
hacker@paths~position-thy-self:/challenge$ run
bash: run: command not found
hacker@paths~position-thy-self:/challenge$ cd run
bash: cd: run: Not a directory
hacker@paths~position-thy-self:/challenge$ cd /run
hacker@paths~position-thy-self:/run$ ls
apache2    current-system  firefox-restart-required  log    mysqld  sendsigs.omit.d  sudo     user
challenge  dojo            lock                      mount  screen  shm              systemd  utmp
hacker@paths~position-thy-self:/run$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:/run$ cd /usr/share/doc
hacker@paths~position-thy-self:/usr/share/doc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{gJwgapIxXwfljllKO5VrZIrTOiq.QX2QTN0wCOzYDN0EzW}
```

### New Learnings
Tested my knowledge with the cd command. 

### References 
Video given on Pondering paths on pwn.college

## Challenge Name
Position elsewhere

### Solve
**Flag:** `pwn.college{YiJrmpBQc-xUJLR_jyE4c02vogV.QX3QTN0wCOzYDN0EzW}`

This was really easy as it's the same as the last one, I was able to do it one go, just ran the program once, found the directory, used cd to navigate to the directory and reran the program!

```bash
PS C:\Users\HP> ssh -i key hacker@dojo.pwn.college
Connected!
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/include directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /usr/include
hacker@paths~position-elsewhere:/usr/include$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{YiJrmpBQc-xUJLR_jyE4c02vogV.QX3QTN0wCOzYDN0EzW}
```

### New Learnings
Clarified my thoughts on the cd command.

### References 
Video given on Pondering paths on pwn.college

## Challenge Name
Position yet elsewhere

### Solve
**Flag:** `pwn.college{8G3MssCs3dh1J6e6i_GP1Ug0zX-.QX4QTN0wCOzYDN0EzW}`

Same as the last two, just redoing it 5 times, so this was the same process as the last program, except a barrage of copy pasting.
found it easy as all i had to do was run the program, and cd to the given directory 5 times.

```bash
PS C:\Users\HP> ssh -i key hacker@dojo.pwn.college
Connected!
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Starting level 1.
Incorrect...
You are not currently in the /usr/bin directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /usr/bin
hacker@paths~position-yet-elsewhere:/usr/bin$ /challenge/run
Starting level 1.
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 2
Please use the `cd` utility to change directory to /usr/share/build-essential
hacker@paths~position-yet-elsewhere:/usr/bin$ cd /usr/share/build-essential
hacker@paths~position-yet-elsewhere:/usr/share/build-essential$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 3
Please use the `cd` utility to change directory to /proc/131
hacker@paths~position-yet-elsewhere:/usr/share/build-essential$ cd /proc/131
hacker@paths~position-yet-elsewhere:/proc/131$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 4
Please use the `cd` utility to change directory to /usr/share/zoneinfo/posix/Asia
hacker@paths~position-yet-elsewhere:/proc/131$ cd /usr/share/zoneinfo/posix/Asia
hacker@paths~position-yet-elsewhere:/usr/share/zoneinfo/posix/Asia$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 5
Please use the `cd` utility to change directory to /tmp
hacker@paths~position-yet-elsewhere:/usr/share/zoneinfo/posix/Asia$ cd /tmp
hacker@paths~position-yet-elsewhere:/tmp$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{8G3MssCs3dh1J6e6i_GP1Ug0zX-.QX4QTN0wCOzYDN0EzW}
```

### New Learnings
Clarified my thoughts on the cd command.

### References 
Video given on Pondering paths on pwn.college

## Challenge Name
implicit relative paths, from /

### Solve
**Flag:** `pwn.college{kgcmI7hbEbVNr8sChX7YBhBviFI.QX5QTN0wCOzYDN0EzW}`

I was initially confused on what the question was asking so i tried executing the command over and over again, it just said that we need to run it from the root folder. So I did, but it wasn't working till I realised that since we're supposed to use relative paths, I'm not supposed to put a / in the beginning, since it's implying i'm executing an absolute path while i'm already in the root folder, so I finally cracked the challenge by simply executing challenge/run

```bash
C:\Users\HP>ssh -i key hacker@dojo.pwn.college
Connected!
hacker@paths~implicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~implicit-relative-paths-from-:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@paths~implicit-relative-paths-from-:/$ cd challenge
hacker@paths~implicit-relative-paths-from-:/challenge$ run
bash: run: command not found
hacker@paths~implicit-relative-paths-from-:/challenge$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:/challenge$ /run
bash: /run: Is a directory
hacker@paths~implicit-relative-paths-from-:/challenge$ run
bash: run: command not found
hacker@paths~implicit-relative-paths-from-:/challenge$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{kgcmI7hbEbVNr8sChX7YBhBviFI.QX5QTN0wCOzYDN0EzW}
```

### New Learnings
Realised how execution works via relative paths

### References 
Video given on Pondering paths on pwn.college

## Challenge Name
explicit relative paths, from /

### Solve
**Flag:** `pwn.college{UKlUFvu8-ete5gQxoMavgJroXgc.QXwUTN0wCOzYDN0EzW}`

From my previous knowledge of webdev in vs code, while navigating files we had used ./ for the same directory, so i kind of figured what to do, so i just tried the command directly but then figured i had to be in the directory of the root folder and reran the command using ./

```bash
PS C:\Users\HP> ssh -i key hacker@dojo.pwn.college
Connected!
hacker@paths~explicit-relative-paths-from-:~$ ./challenge/run
bash: ./challenge/run: No such file or directory
hacker@paths~explicit-relative-paths-from-:~$ /./challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{UKlUFvu8-ete5gQxoMavgJroXgc.QXwUTN0wCOzYDN0EzW}
```

### New Learnings
revisited ./ while learning explicit file paths

### References 
Video given on Pondering paths on pwn.college

## Challenge Name
implicit relative path

### Solve
**Flag:** `pwn.college{YncHR16KYZre2wcGfk38Oop61Tr.QXxUTN0wCOzYDN0EzW}`

From the guide given under the challenge, I understood why in the previous challenges run wasn't working, I immediately understood what to do when the hint was given(we had to use .) so i first navigated to the challenge directory and proceeded to use ./ which ran the run command, which usually wouldn't as linux comprehends it as a directory

```bash
PS C:\Users\HP> ssh -i key hacker@dojo.pwn.college
Connected!
hacker@paths~implicit-relative-path:~$ ./challenge
bash: ./challenge: No such file or directory
hacker@paths~implicit-relative-path:~$ /challenge
bash: /challenge: Is a directory
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{YncHR16KYZre2wcGfk38Oop61Tr.QXxUTN0wCOzYDN0EzW}
```

### New Learnings
learnt about how ./ works in the terminal

### References 
Video given on Pondering paths on pwn.college

## Challenge Name
home sweet home

### Solve
**Flag:** `pwn.college{ITnvUHTsjlgHk0S-a9yCJp6y64R.QXzMDO0wCOzYDN0EzW}`

As per the guide we had to write to a location under 3 characters or less, for which we obviously required the help of ~, so initially i assumed a folder was already created under hacker where we had to write the challenge to, but when i used ls, there were no programs, so i just wrote the challenge to a random folder a and it worked out!

```bash
Connected!
hacker@paths~home-sweet-home:~$ echo LOOK:~
LOOK:~
hacker@paths~home-sweet-home:~$ echo LOOK: ~
LOOK: /home/hacker
hacker@paths~home-sweet-home:~$ ls
hacker@paths~home-sweet-home:~$ cd
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{ITnvUHTsjlgHk0S-a9yCJp6y64R.QXzMDO0wCOzYDN0EzW}
```

### New Learnings
I learnt that the LEADING ~ stands for /home/hacker and if you write ~/~ it's comprehended as /home/hacker/~ so it's just the leading ~ that determines the location of the hacker directory. 

### References 
Video given on Pondering paths on pwn.college
