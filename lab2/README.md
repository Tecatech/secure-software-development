```
tecatech@alpha:~/secure-software-development/lab2$ ls -l
total 4
drwxr-xr-x 63 tecatech tecatech 4096 Apr  1 17:00 qemu
tecatech@alpha:~/secure-software-development/lab2$ sudo docker pull neszt/cppcheck-docker
Using default tag: latest
latest: Pulling from neszt/cppcheck-docker
8921db27df28: Pull complete
5e21991f0aaa: Pull complete
Digest: sha256:909ef4e679384750b1b98540d8c3705bfd0a8a7dae1112e99661c0c6772785a0
Status: Downloaded newer image for neszt/cppcheck-docker:latest
docker.io/neszt/cppcheck-docker:latest
tecatech@alpha:~/secure-software-development/lab2$ sudo docker run -t -v $(pwd):/src/ neszt/cppcheck-docker --enable=all --xml --xml-version=2 ./qemu/ 2>report.xml
tecatech@alpha:~/secure-software-development/lab2$ ls -l
total 7168
drwxr-xr-x 63 tecatech tecatech    4096 Apr  1 17:00 qemu
-rw-r--r--  1 tecatech tecatech 7328587 Apr  1 18:00 report.xml
tecatech@alpha:~/secure-software-development/lab2$ cppcheck-htmlreport --report-dir=report/ --file=report.xml --source-dir=qemu/
Creating index.html
Creating style.css file
Creating stats.html (statistics)

Open 'report//index.html' to see the results.
tecatech@alpha:~/secure-software-development/lab2$ ls -l
total 7168
drwxr-xr-x 63 tecatech tecatech    4096 Apr  1 17:00 qemu
drwxr-xr-x  2 tecatech tecatech    4096 Apr  2 19:00 report
-rw-r--r--  1 tecatech tecatech 7328587 Apr  1 18:00 report.xml
```