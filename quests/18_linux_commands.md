```
~ $ cd Commands/
~/Commands $ pwd
/home/node/Commands
~/Commands $ mkdir test
~/Commands $ ls
temp01       temp_01.txt  test
~/Commands $ mkdir notes
~/Commands $ cd notes/
~/Commands/notes $ pwd
/home/node/Commands/notes
~/Commands/notes $ cd ../
~/Commands $ mkdir images videos docs
~/Commands $ ls
docs         notes        temp_01.txt  videos
images       temp01       test
~/Commands $ ls -l
total 24
drwxr-sr-x    2 node     node          4096 Nov  7 03:41 docs
drwxr-sr-x    2 node     node          4096 Nov  7 03:41 images
drwxr-sr-x    2 node     node          4096 Nov  7 03:41 notes
drwxr-sr-x    2 node     node          4096 Nov  7 03:20 temp01
-rw-r--r--    1 node     node             0 Nov  7 03:10 temp_01.txt
drwxr-sr-x    2 node     node          4096 Nov  7 03:40 test
drwxr-sr-x    2 node     node          4096 Nov  7 03:41 videos
~/Commands $ cd docs/
~/Commands/docs $ cd ../
~/Commands $ ls -l
total 24
drwxr-sr-x    2 node     node          4096 Nov  7 03:41 docs
drwxr-sr-x    2 node     node          4096 Nov  7 03:41 images
drwxr-sr-x    2 node     node          4096 Nov  7 03:41 notes
drwxr-sr-x    2 node     node          4096 Nov  7 03:20 temp01
-rw-r--r--    1 node     node             0 Nov  7 03:10 temp_01.txt
drwxr-sr-x    2 node     node          4096 Nov  7 03:40 test
drwxr-sr-x    2 node     node          4096 Nov  7 03:41 videos
~/Commands $ 

```