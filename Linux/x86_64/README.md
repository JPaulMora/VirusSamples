# XorDDoS

$RANDOM = Random String

CC looks like it comes from China. Virus checks constantly for the existence of all these files, regenerating them if they are deleted. Corrupting /lib/libudev.so and then deleting /etc/cron.hourly/$RANDOM.sh makes the DDoS attack stop, probably because it tries to rebuild the binary from the corrupted library.

### bin/

* $RANDOM.sh : This is probably the main executable, although there might be multiple copies of it around the filesystem, each in charge of keeping another one. 

### /etc/cron.hourly/: 
* gcc.sh: This file uncovers another crucial file, and tries to keep persistence.
* $RANDOM.sh: This file is regenerated every time is deleted, same happens with the file in /bin.

### /lib/
* libudev.so: Don’t really know what it is for other than "backup", doesn’t seem to be executed at any time, just copied around.

### Password: Xorddos
