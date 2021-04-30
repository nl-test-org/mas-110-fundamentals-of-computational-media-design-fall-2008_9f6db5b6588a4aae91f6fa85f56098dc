---
course_id: mas-110-fundamentals-of-computational-media-design-fall-2008
layout: course_section
parent_title: Assignments
title: 'Exercise 3: playing with csoundxo'
type: course
uid: 7882fb354a703a51b148024d1ea8f9ed

---

This material is by Wu-Hsi Li. (Courtesy of Wu-Hsi Li. Used with permission.)

[Download the MusicPainter TAR file]({{< baseurl >}}/sections/assignments/musicpainter_dow) and expand archive to get Musicpainter.activity folder

Try the following steps, and start imagining possible design of musical games over one or multiple laptops.  
  
\# change directory to Musicpainter.activity folder  
\# (cd /home/olpc/Activities/Musicpainter.activity)  
\# run example python file (python exercise.py)  
#  
\# hack the exercise.py program (use text editor like vi to edit your py file)  
\# or use command line programming to try the following program line by line  
\# (execute "python" and type in the program by lines)  
  
from CsoundXOAgent2 import CsoundXOAgent     # import csoundxo  
  
\# I re-wrote the CsoundXOAgent2 so no callback is needed now  
  
csound1 = CsoundXOAgent("localhost", 7000)  
  
\# if you want to connect to a remote server, you need a csoundxo server   
\# running and listening - "cd /home/olpc/csoundxo", and "./csoundxo"  
  
\# sometimes, you leave the program and the network port hasn't been released  
\# you might see "Server: socket failed to bind"  
\# normally, the port will be released after 1 minute, so keep trying  
\# in some cases, you will need to restart the machine  
  
csound1.sendLinevt("i8 0 2 1 0")    
csound1.sendLinevt("i1 0 1 1 7.00")     # format information see below  
csound1.sendLinevt("i1 0 1 1 7.02")  
csound1.sendLinevt("i1 0 1 1 7.04")  
csound1.sendLinevt("i1 0 1 2 7.04")  
csound1.sendLinevt("i1 0 5 2 7.04")  
  
csound1.close()   # shutdown the server  
  
#  
\# line event format  
#  
\# field 1: instrument, 1: piano, 2: accordion, 3: string, 4: pizz, 5: clarinet, 6: guitar, 7: bass, 8: percussion  
\# field 2: start time (sec)  
\# field 3: duration (sec)  
\# field 4: volume, 1.0 = normal  
\# field 5: for percussion instrument, assign 0 ~ 17 for different sounds  
#             for pitch instrument, assign a.bb;  
#             for example 8.00 is a C5, 8.01 is C#5, 8.02 is D5, 7.00 is a C4  
\# you can also send events to multiple csound servers,  
\# assign different IP and have the csoundxo listening in remote machine