```
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 0
tecatech@alpha:~/secure-software-development/lab1$ nano build-docker.sh
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 4
-rw-r--r-- 1 tecatech tecatech 1041 Feb 18 23:24 build-docker.sh
tecatech@alpha:~/secure-software-development/lab1$ chmod +x build-docker.sh
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 4
-rwxr-xr-x 1 tecatech tecatech 1041 Feb 18 23:24 build-docker.sh
tecatech@alpha:~/secure-software-development/lab1$ wget https://pypi.tuna.tsinghua.edu.cn/packages/38/29/044333b3caf5ff1d2394b0e6c6d87df79973f5652ab7deddc46c7eb9d935/Django-1.4.13.tar.gz#sha256=a8fede657378b6862744b19012e7071279b952ecd208fd83227723866068f2c0
tecatech@alpha:~/secure-software-development/lab1$ wget https://www.cpan.org/src/5.0/perl-5.26.3.tar.gz
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 24172
-rw-r--r-- 1 tecatech tecatech  7753532 May 14  2014 Django-1.4.13.tar.gz
-rwxr-xr-x 1 tecatech tecatech     1041 Feb 18 23:24 build-docker.sh
-rw-r--r-- 1 tecatech tecatech 16992333 Nov 29  2018 perl-5.26.3.tar.gz
tecatech@alpha:~/secure-software-development/lab1$ tar -xvf Django-1.4.13.tar.gz && rm Django-1.4.13.tar.gz
tecatech@alpha:~/secure-software-development/lab1$ tar -xvf perl-5.26.3.tar.gz && rm perl-5.26.3.tar.gz
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 20
drwxr-xr-x  7 tecatech tecatech  4096 May 14  2014 Django-1.4.13
-rwxr-xr-x  1 tecatech tecatech  1041 Feb 18 23:24 build-docker.sh
drwxr-xr-x 26 tecatech tecatech 12288 Nov 29  2018 perl-5.26.3
tecatech@alpha:~/secure-software-development/lab1$ sudo ./build-docker.sh
latest: Pulling from owasp/dependency-check
Digest: sha256:c8d795483800c94a433ed4f70bac93ebc8edfbbab395dbc8276a1fc76986b6a6
Status: Image is up to date for owasp/dependency-check:latest
docker.io/owasp/dependency-check:latest
[INFO] Checking for updates
[INFO] Download Started for NVD CVE – Modified
[INFO] Download Complete for NVD CVE – Modified  (1466 ms)
[INFO] Processing Started for NVD CVE – Modified
[INFO] Processing Complete for NVD CVE – Modified  (5418 ms)
[INFO] Begin database maintenance
[INFO] Updated the CPE ecosystem on 125288 NVD records
[INFO] End database maintenance (9466 ms)
[INFO] Skipping RetireJS update since last update was within 24 hours.
[INFO] Skipping Hosted Suppressions file update since last update was within 2 hours.
[INFO] Skipping Known Exploited Vulnerabilities update check since last check was within 24 hours.
[INFO] Begin database defrag
[INFO] End database defrag (4646 ms)
[INFO] Check for updates complete (26108 ms)
[INFO] Analysis Started
[INFO] Finished Archive Analyzer (0 seconds)
[INFO] Finished File Name Analyzer (0 seconds)
[INFO] Finished Dependency Merging Analyzer (0 seconds)
[INFO] Finished Version Filter Analyzer (0 seconds)
[INFO] Finished Hint Analyzer (0 seconds)
[INFO] Created CPE Index (1 seconds)
[INFO] Finished CPE Analyzer (1 seconds)
[INFO] Finished False Positive Analyzer (0 seconds)
[INFO] Finished NVD CVE Analyzer (0 seconds)
[INFO] Finished RetireJS Analyzer (0 seconds)
[INFO] Finished Sonatype OSS Index Analyzer (0 seconds)
[INFO] Finished Vulnerability Suppression Analyzer (0 seconds)
[INFO] Finished Known Exploited Vulnerability Analyzer (0 seconds)
[INFO] Finished Dependency Bundling Analyzer (0 seconds)
[INFO] Finished Unused Suppression Rule Analyzer (0 seconds)
[INFO] Analysis Complete (2 seconds)
[INFO] Writing report to: /report/dependency-check-report.xml
[INFO] Writing report to: /report/dependency-check-report.html
[INFO] Writing report to: /report/dependency-check-report.json
[INFO] Writing report to: /report/dependency-check-report.csv
[INFO] Writing report to: /report/dependency-check-report.sarif
[INFO] Writing report to: /report/dependency-check-jenkins.html
[INFO] Writing report to: /report/dependency-check-junit.xml
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 24
drwxr-xr-x  7 tecatech tecatech  4096 May 14  2014 Django-1.4.13
-rwxr-xr-x  1 tecatech tecatech  1041 Feb 18 23:24 build-docker.sh
drwxr-xr-x  2 root     root      4096 Feb 18 23:28 odc-reports
drwxr-xr-x 26 tecatech tecatech 12288 Nov 29  2018 perl-5.26.3
tecatech@alpha:~/secure-software-development/lab1$ curl https://static.snyk.io/cli/latest/snyk-linux -o snyk
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 68852
drwxr-xr-x  7 tecatech tecatech     4096 May 14  2014 Django-1.4.13
-rwxr-xr-x  1 tecatech tecatech     1041 Feb 18 23:24 build-docker.sh
drwxr-xr-x  2 root     root         4096 Feb 18 23:28 odc-reports
drwxr-xr-x 26 tecatech tecatech    12288 Nov 29  2018 perl-5.26.3
-rw-r--r--  1 tecatech tecatech 70479822 Feb 18 23:32 snyk
tecatech@alpha:~/secure-software-development/lab1$ chmod +x snyk
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 68852
drwxr-xr-x  7 tecatech tecatech     4096 May 14  2014 Django-1.4.13
-rwxr-xr-x  1 tecatech tecatech     1041 Feb 18 23:24 build-docker.sh
drwxr-xr-x  2 root     root         4096 Feb 18 23:28 odc-reports
drwxr-xr-x 26 tecatech tecatech    12288 Nov 29  2018 perl-5.26.3
-rwxr-xr-x  1 tecatech tecatech 70479822 Feb 18 23:32 snyk
tecatech@alpha:~/secure-software-development/lab1$ sudo mv snyk /usr/local/bin/
tecatech@alpha:~/secure-software-development/lab1$ ls -l
total 24
drwxr-xr-x  7 tecatech tecatech  4096 May 14  2014 Django-1.4.13
-rwxr-xr-x  1 tecatech tecatech  1041 Feb 18 23:24 build-docker.sh
drwxr-xr-x  2 root     root      4096 Feb 18 23:28 odc-reports
drwxr-xr-x 26 tecatech tecatech 12288 Nov 29  2018 perl-5.26.3
tecatech@alpha:~/secure-software-development/lab1$ cd perl-5.26.3/
tecatech@alpha:~/secure-software-development/lab1/perl-5.26.3$ ls -l
total 11188
-r--r--r--  1 tecatech tecatech  48075 Mar 23  2018 AUTHORS
-r--r--r--  1 tecatech tecatech   6321 Mar  1  2018 Artistic
-r--r--r--  1 tecatech tecatech   3168 Mar  1  2018 Changes
-r-xr-xr-x  1 tecatech tecatech 593172 Mar 23  2018 Configure
-r--r--r--  1 tecatech tecatech  12632 Mar  1  2018 Copying
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 Cross
-r--r--r--  1 tecatech tecatech   1714 Mar  1  2018 EXTERN.h
-r--r--r--  1 tecatech tecatech 107605 Nov  3  2018 INSTALL
-r--r--r--  1 tecatech tecatech   1271 Mar  1  2018 INTERN.h
-r--r--r--  1 tecatech tecatech 325244 Nov  4  2018 MANIFEST
-r--r--r--  1 tecatech tecatech   3660 Nov 29  2018 META.json
-r--r--r--  1 tecatech tecatech   2908 Nov  3  2018 META.yml
-r-xr-xr-x  1 tecatech tecatech  52538 Nov  4  2018 Makefile.SH
-r--r--r--  1 tecatech tecatech   5484 Mar  1  2018 Makefile.micro
drwxr-xr-x  5 tecatech tecatech   4096 Nov 29  2018 NetWare
-r-xr-xr-x  1 tecatech tecatech   8135 Mar  1  2018 Policy_sh.SH
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 Porting
-r--r--r--  1 tecatech tecatech   5677 Mar  1  2018 README
-r--r--r--  1 tecatech tecatech  20437 Mar 23  2018 README.aix
-r--r--r--  1 tecatech tecatech   5749 Mar  1  2018 README.amiga
-r--r--r--  1 tecatech tecatech   7871 Mar  1  2018 README.android
-r--r--r--  1 tecatech tecatech   8058 Mar  1  2018 README.bs2000
-r--r--r--  1 tecatech tecatech  14602 Mar  1  2018 README.ce
-r--r--r--  1 tecatech tecatech   4691 Mar  1  2018 README.cn
-r--r--r--  1 tecatech tecatech  27199 Mar  1  2018 README.cygwin
-r--r--r--  1 tecatech tecatech  10522 Mar  1  2018 README.dos
-r--r--r--  1 tecatech tecatech   1610 Mar 23  2018 README.freebsd
-r--r--r--  1 tecatech tecatech   1508 Nov  3  2018 README.haiku
-r--r--r--  1 tecatech tecatech  30509 Mar  1  2018 README.hpux
-r--r--r--  1 tecatech tecatech   1993 Mar 23  2018 README.hurd
-r--r--r--  1 tecatech tecatech   4395 Mar  1  2018 README.irix
-r--r--r--  1 tecatech tecatech   7521 Mar 23  2018 README.jp
-r--r--r--  1 tecatech tecatech  12259 Mar  1  2018 README.ko
-r--r--r--  1 tecatech tecatech   1488 Mar  1  2018 README.linux
-r--r--r--  1 tecatech tecatech   1001 Mar  1  2018 README.macos
-r--r--r--  1 tecatech tecatech  12060 Nov  3  2018 README.macosx
-r--r--r--  1 tecatech tecatech   1857 Mar  1  2018 README.micro
-r--r--r--  1 tecatech tecatech   6648 Mar  1  2018 README.netware
-r--r--r--  1 tecatech tecatech   1204 Mar  1  2018 README.openbsd
-r--r--r--  1 tecatech tecatech  93351 Nov  3  2018 README.os2
-r--r--r--  1 tecatech tecatech  15674 Mar 23  2018 README.os390
-r--r--r--  1 tecatech tecatech   4768 Mar  1  2018 README.os400
-r--r--r--  1 tecatech tecatech   5125 Mar  1  2018 README.plan9
-r--r--r--  1 tecatech tecatech   6673 Mar  1  2018 README.qnx
-r--r--r--  1 tecatech tecatech   1529 Mar  1  2018 README.riscos
-r--r--r--  1 tecatech tecatech  29822 Mar 23  2018 README.solaris
-r--r--r--  1 tecatech tecatech  15359 Mar  1  2018 README.symbian
-r--r--r--  1 tecatech tecatech   7778 Mar 23  2018 README.synology
-r--r--r--  1 tecatech tecatech   8492 Mar  1  2018 README.tru64
-r--r--r--  1 tecatech tecatech   4477 Mar 23  2018 README.tw
-r--r--r--  1 tecatech tecatech  24009 Nov  3  2018 README.vms
-r--r--r--  1 tecatech tecatech   3843 Mar  1  2018 README.vos
-r--r--r--  1 tecatech tecatech  39298 Mar 23  2018 README.win32
-r--r--r--  1 tecatech tecatech   4060 Mar 23  2018 TestInit.pm
-r--r--r--  1 tecatech tecatech  24447 Mar 23  2018 XSUB.h
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 amigaos4
-r--r--r--  1 tecatech tecatech    983 Mar  1  2018 asan_ignore
-r--r--r--  1 tecatech tecatech  16104 Mar 23  2018 autodoc.pl
-r--r--r--  1 tecatech tecatech  25771 Mar 23  2018 av.c
-r--r--r--  1 tecatech tecatech   3320 Mar 23  2018 av.h
-r--r--r--  1 tecatech tecatech   4302 Mar  1  2018 caretx.c
-r-xr-xr-x  1 tecatech tecatech  15447 Mar 23  2018 cflags.SH
-r--r--r--  1 tecatech tecatech 972477 Mar 23  2018 charclass_invlists.h
-r-xr-xr-x  1 tecatech tecatech 170845 Mar 23  2018 config_h.SH
-r-xr-xr-x  1 tecatech tecatech  32613 Mar 23  2018 configpm
-r--r--r--  1 tecatech tecatech 221010 Mar 23  2018 configure.com
-r-xr-xr-x  1 tecatech tecatech   2556 Mar  1  2018 configure.gnu
-r--r--r--  1 tecatech tecatech  39536 Mar 23  2018 cop.h
drwxr-xr-x 80 tecatech tecatech   4096 Nov 29  2018 cpan
-r--r--r--  1 tecatech tecatech  12042 Mar  1  2018 cv.h
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 cygwin
-r--r--r--  1 tecatech tecatech   7717 Mar 23  2018 deb.c
drwxr-xr-x 41 tecatech tecatech   4096 Nov 29  2018 dist
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 djgpp
-r--r--r--  1 tecatech tecatech  70361 Mar 23  2018 doio.c
-r--r--r--  1 tecatech tecatech  32646 Mar 23  2018 doop.c
-r--r--r--  1 tecatech tecatech   5501 Mar 23  2018 dosish.h
-r--r--r--  1 tecatech tecatech   9332 Mar  1  2018 dquote.c
-r--r--r--  1 tecatech tecatech   1843 Mar  1  2018 dquote_inline.h
-r--r--r--  1 tecatech tecatech  91208 Mar 23  2018 dump.c
-r--r--r--  1 tecatech tecatech  29856 Mar  1  2018 ebcdic_tables.h
-r--r--r--  1 tecatech tecatech 133870 Mar 23  2018 embed.fnc
-rw-r--r--  1 tecatech tecatech  97289 Mar 23  2018 embed.h
-rw-r--r--  1 tecatech tecatech  18910 Mar 23  2018 embedvar.h
drwxr-xr-x 43 tecatech tecatech   4096 Nov 29  2018 ext
-r--r--r--  1 tecatech tecatech   3211 Mar  1  2018 fakesdio.h
-rw-r--r--  1 tecatech tecatech   4915 Mar 23  2018 feature.h
-r--r--r--  1 tecatech tecatech   1463 Mar  1  2018 form.h
-r--r--r--  1 tecatech tecatech   3834 Mar  1  2018 generate_uudmap.c
-r--r--r--  1 tecatech tecatech   1206 Mar  1  2018 globals.c
-r--r--r--  1 tecatech tecatech   1350 Mar 23  2018 globvar.sym
-r--r--r--  1 tecatech tecatech 111413 Mar 23  2018 gv.c
-r--r--r--  1 tecatech tecatech  10711 Mar 23  2018 gv.h
drwxr-xr-x  3 tecatech tecatech   4096 Nov 29  2018 h2pl
drwxr-xr-x  3 tecatech tecatech   4096 Nov 29  2018 haiku
-r--r--r--  1 tecatech tecatech 123072 Mar 23  2018 handy.h
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 hints
-r--r--r--  1 tecatech tecatech 111197 Mar 23  2018 hv.c
-r--r--r--  1 tecatech tecatech  25571 Mar 23  2018 hv.h
-r--r--r--  1 tecatech tecatech  13413 Mar 23  2018 hv_func.h
-r--r--r--  1 tecatech tecatech  46484 Mar 23  2018 inline.h
-r--r--r--  1 tecatech tecatech   4959 Mar  1  2018 install_lib.pl
-r--r--r--  1 tecatech tecatech  17629 Mar 23  2018 installhtml
-r-xr-xr-x  1 tecatech tecatech   5866 Mar 23  2018 installman
-r-xr-xr-x  1 tecatech tecatech  26797 Mar 23  2018 installperl
-r--r--r--  1 tecatech tecatech  29477 Mar 23  2018 intrpvar.h
-r--r--r--  1 tecatech tecatech   2750 Mar  1  2018 invlist_inline.h
-r--r--r--  1 tecatech tecatech  48806 Mar  1  2018 iperlsys.h
-rw-r--r--  1 tecatech tecatech  90980 Mar 23  2018 keywords.c
-rw-r--r--  1 tecatech tecatech   6587 Mar 23  2018 keywords.h
-r--r--r--  1 tecatech tecatech 126918 Mar 23  2018 l1_char_class_tab.h
drwxr-xr-x 20 tecatech tecatech   4096 Nov 29  2018 lib
-r--r--r--  1 tecatech tecatech 106726 Mar 23  2018 locale.c
-r--r--r--  1 tecatech tecatech  26121 Mar 23  2018 make_ext.pl
-r--r--r--  1 tecatech tecatech   6814 Mar  1  2018 make_patchnum.pl
-r--r--r--  1 tecatech tecatech  31585 Mar 23  2018 makedef.pl
-r-xr-xr-x  1 tecatech tecatech   9258 Mar 23  2018 makedepend.SH
-r--r--r--  1 tecatech tecatech  71935 Mar 23  2018 malloc.c
-r--r--r--  1 tecatech tecatech   1512 Mar  1  2018 malloc_ctl.h
-r--r--r--  1 tecatech tecatech  34845 Mar 23  2018 mathoms.c
-r-xr-xr-x  1 tecatech tecatech   1200 Mar  1  2018 metaconfig.SH
-r--r--r--  1 tecatech tecatech    674 Mar 23  2018 metaconfig.h
-r--r--r--  1 tecatech tecatech  91927 Mar 23  2018 mg.c
-r--r--r--  1 tecatech tecatech   3013 Mar  1  2018 mg.h
-r--r--r--  1 tecatech tecatech   2150 Mar  1  2018 mg_names.inc
-r--r--r--  1 tecatech tecatech   4257 Mar  1  2018 mg_raw.h
-rw-r--r--  1 tecatech tecatech   9336 Mar  1  2018 mg_vtable.h
-r--r--r--  1 tecatech tecatech   5669 Mar 23  2018 miniperlmain.c
-r--r--r--  1 tecatech tecatech   4475 Mar  1  2018 mkppport
-r--r--r--  1 tecatech tecatech    257 Mar  1  2018 mkppport.lst
-r--r--r--  1 tecatech tecatech  43488 Mar 23  2018 mro_core.c
-r-xr-xr-x  1 tecatech tecatech   2686 Mar 23  2018 myconfig.SH
-r--r--r--  1 tecatech tecatech   1693 Mar  1  2018 mydtrace.h
-r--r--r--  1 tecatech tecatech   3392 Mar  1  2018 nostdio.h
-r--r--r--  1 tecatech tecatech  53443 Mar 23  2018 numeric.c
-r--r--r--  1 tecatech tecatech 452134 Mar 23  2018 op.c
-r--r--r--  1 tecatech tecatech  36419 Mar 23  2018 op.h
-r--r--r--  1 tecatech tecatech   5911 Mar  1  2018 op_reg_common.h
-rw-r--r--  1 tecatech tecatech  91887 Mar 23  2018 opcode.h
-rw-r--r--  1 tecatech tecatech   8836 Mar 23  2018 opnames.h
drwxr-xr-x  3 tecatech tecatech   4096 Nov 29  2018 os2
-rw-r--r--  1 tecatech tecatech   3276 Mar  1  2018 overload.h
-rw-r--r--  1 tecatech tecatech   3657 Mar  1  2018 overload.inc
-r--r--r--  1 tecatech tecatech   6087 Mar  1  2018 packsizetables.inc
-r--r--r--  1 tecatech tecatech  82879 Mar 23  2018 pad.c
-r--r--r--  1 tecatech tecatech  17246 Mar 23  2018 pad.h
-r--r--r--  1 tecatech tecatech   6914 Mar 23  2018 parser.h
-r--r--r--  1 tecatech tecatech   5321 Nov 29  2018 patchlevel.h
-r--r--r--  1 tecatech tecatech 140804 Mar 23  2018 perl.c
-r--r--r--  1 tecatech tecatech 243237 Mar 23  2018 perl.h
-rw-r--r--  1 tecatech tecatech   1728 Mar  1  2018 perlapi.c
-rw-r--r--  1 tecatech tecatech   5863 Mar 23  2018 perlapi.h
-r--r--r--  1 tecatech tecatech    491 Mar  1  2018 perldtrace.d
-r--r--r--  1 tecatech tecatech 125282 Mar 23  2018 perlio.c
-r--r--r--  1 tecatech tecatech   9464 Mar  1  2018 perlio.h
-r--r--r--  1 tecatech tecatech    446 Mar  1  2018 perlio.sym
-r--r--r--  1 tecatech tecatech  13761 Mar  1  2018 perliol.h
-r--r--r--  1 tecatech tecatech    527 Mar  1  2018 perlsdio.h
-r--r--r--  1 tecatech tecatech   9690 Mar 23  2018 perlvars.h
-r--r--r--  1 tecatech tecatech  48428 Mar 23  2018 perly.act
-r--r--r--  1 tecatech tecatech  18228 Mar 23  2018 perly.c
-r--r--r--  1 tecatech tecatech   4369 Mar 23  2018 perly.h
-r--r--r--  1 tecatech tecatech  75625 Mar 23  2018 perly.tab
-r--r--r--  1 tecatech tecatech  37847 Mar 23  2018 perly.y
drwxr-xr-x  3 tecatech tecatech   4096 Nov 29  2018 plan9
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 pod
-r--r--r--  1 tecatech tecatech 174836 Mar 23  2018 pp.c
-r--r--r--  1 tecatech tecatech  27577 Mar 23  2018 pp.h
-r--r--r--  1 tecatech tecatech 159432 Mar 23  2018 pp_ctl.c
-r--r--r--  1 tecatech tecatech 145064 Mar 23  2018 pp_hot.c
-r--r--r--  1 tecatech tecatech  86852 Mar 23  2018 pp_pack.c
-rw-r--r--  1 tecatech tecatech  12086 Mar 23  2018 pp_proto.h
-r--r--r--  1 tecatech tecatech  67273 Mar 23  2018 pp_sort.c
-r--r--r--  1 tecatech tecatech 142916 Mar 23  2018 pp_sys.c
-rw-r--r--  1 tecatech tecatech 246629 Mar 23  2018 proto.h
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 qnx
-rw-r--r--  1 tecatech tecatech  16107 Mar 23  2018 reentr.c
-rw-r--r--  1 tecatech tecatech  78270 Mar  1  2018 reentr.h
-rw-r--r--  1 tecatech tecatech 144582 Mar 23  2018 regcharclass.h
-r--r--r--  1 tecatech tecatech 808028 Nov  5  2018 regcomp.c
-r--r--r--  1 tecatech tecatech  47796 Mar 23  2018 regcomp.h
-r--r--r--  1 tecatech tecatech  12510 Mar 23  2018 regcomp.sym
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 regen
-r--r--r--  1 tecatech tecatech    869 Mar 23  2018 regen.pl
-r--r--r--  1 tecatech tecatech   9622 Mar 23  2018 regen_perly.pl
-r--r--r--  1 tecatech tecatech 369684 Mar 23  2018 regexec.c
-r--r--r--  1 tecatech tecatech  34379 Mar 23  2018 regexp.h
-rw-r--r--  1 tecatech tecatech  35834 Mar 23  2018 regnodes.h
-r--r--r--  1 tecatech tecatech   1444 Mar  1  2018 run.c
-r-xr-xr-x  1 tecatech tecatech   2513 Mar  1  2018 runtests.SH
-r--r--r--  1 tecatech tecatech  43470 Mar 23  2018 scope.c
-r--r--r--  1 tecatech tecatech  11905 Mar 23  2018 scope.h
-r--r--r--  1 tecatech tecatech 485601 Mar 23  2018 sv.c
-r--r--r--  1 tecatech tecatech  84256 Mar 23  2018 sv.h
drwxr-xr-x  3 tecatech tecatech   4096 Nov 29  2018 symbian
drwxr-xr-x 20 tecatech tecatech   4096 Nov 29  2018 t
-r--r--r--  1 tecatech tecatech   5250 Mar 23  2018 taint.c
-r--r--r--  1 tecatech tecatech  12013 Mar  1  2018 thread.h
-r--r--r--  1 tecatech tecatech  15535 Mar 23  2018 time64.c
-r--r--r--  1 tecatech tecatech   1576 Mar 23  2018 time64.h
-r--r--r--  1 tecatech tecatech   2030 Mar  1  2018 time64_config.h
-r--r--r--  1 tecatech tecatech 381355 Mar 23  2018 toke.c
-rw-r--r--  1 tecatech tecatech 167129 Mar 23  2018 uconfig.h
-r--r--r--  1 tecatech tecatech  18465 Mar 23  2018 uconfig.sh
-r--r--r--  1 tecatech tecatech  18509 Mar 23  2018 uconfig64.sh
-r--r--r--  1 tecatech tecatech   7990 Mar 23  2018 unicode_constants.h
-r--r--r--  1 tecatech tecatech  27278 Mar 23  2018 universal.c
-r--r--r--  1 tecatech tecatech   5107 Mar 23  2018 unixish.h
-r--r--r--  1 tecatech tecatech 201299 Mar 23  2018 utf8.c
-r--r--r--  1 tecatech tecatech  59111 Mar 23  2018 utf8.h
-r--r--r--  1 tecatech tecatech  67302 Mar 23  2018 utfebcdic.h
-r--r--r--  1 tecatech tecatech 184866 Nov  5  2018 util.c
-r--r--r--  1 tecatech tecatech   9600 Mar 23  2018 util.h
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 utils
-r--r--r--  1 tecatech tecatech    525 Mar 23  2018 utils.lst
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 vms
drwxr-xr-x  2 tecatech tecatech   4096 Nov 29  2018 vos
-r--r--r--  1 tecatech tecatech  25522 Mar 23  2018 vutil.c
-r--r--r--  1 tecatech tecatech   7467 Mar  1  2018 vutil.h
-r--r--r--  1 tecatech tecatech  11142 Mar 23  2018 vxs.inc
-rw-r--r--  1 tecatech tecatech   7816 Mar 23  2018 warnings.h
drwxr-xr-x  5 tecatech tecatech   4096 Nov 29  2018 win32
-r--r--r--  1 tecatech tecatech   3223 Mar  1  2018 write_buildcustomize.pl
tecatech@alpha:~/secure-software-development/lab1/perl-5.26.3$ sudo snyk test --unmanaged

Testing /home/tecatech/secure-software-development/lab1/perl-5.26.3...

Issues:

 ? [High] Buffer Overflow
    Introduced through: https://cpan.org|perl5@5.26.3
    URL: https://security.snyk.io/vuln/SNYK-UNMANAGED-PERL5-2317607

 ? [High] Integer Overflow or Wraparound
    Introduced through: https://cpan.org|perl5@5.26.3
    URL: https://security.snyk.io/vuln/SNYK-UNMANAGED-PERL5-2317616

 ? [High] Out-of-bounds Write
    Introduced through: https://cpan.org|perl5@5.26.3
    URL: https://security.snyk.io/vuln/SNYK-UNMANAGED-PERL5-2327381

Tested 3 dependencies for known issues, found 3 issues.
```