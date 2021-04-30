---
course_id: mas-110-fundamentals-of-computational-media-design-fall-2008
layout: course_section
parent_title: Assignments
title: 'CsoundXO: Download and Instructions'
type: course
uid: 580501e1fcb35707178de2ac73d47b85

---

These instructions are provided by Wu-Hsi Li. (Courtesy of Wu-Hsi Li. Used with permission.)

Description
-----------

CsoundXO server, CsoundXO Python API, sample sounds, sample Python programs.

Software Download
-----------------

CsoundXO software package, by Barry Vercoe: ([TAR - 37.2 MB](/coursemedia/mas-110-fundamentals-of-computational-media-design-fall-2008/49d393b928aa936eb8f3c00a692bb9bc_csoundxo.tar))

I wouldn't suggest you to download the file through Browse activity since the file management in XO is kind of tricky, but if you're interested, see [http://wiki.laptop.org/go/Journal\_Activity](http://wiki.laptop.org/go/Journal_Activity). Please download csoundxo.tar and Musicpainter.tar from your own computer, and copy to a flash disc.

Installation
------------

1.  plug your flash disc on XO, then open a terminal activity on XO
2.  "su" - become root
3.  "mount" - check the id of your flash disc
4.  "mount /dev/sda1 /mnt" - the device name varies, replace the device name with the actual one
5.  "exit" - exit root mode
6.  "cp /mnt/csoundxo.tar /home/olpc/csoundxo.tar"
7.  "cp /mnt/Musicpainter.tar /home/olpc/Activities/Musicpainter.tar"
8.  "tar -xvf csoundxo.tar"
9.  "su" - become root again
10.  "umount /mnt" - unmount
11.  "exit"

Music Demo 1
------------

A Whitney Houston piece:

1.  Python csndxogui.py
2.  press "launch server"
3.  press "connect" to localhost
4.  press "play 10whit"
5.  press "stop", and "disconnect", and "shutdown"

Music Demo 2
------------

Make two XOs play together on remote machine

1.  get a remote machine
2.  make sure both XOs connect to Internet or to the same mesh
3.  check the IP from the remote machine by "ifconfig" in the terminal
4.  go to the csoundxo folder, run csoundxo (./csoundxo)

On main machine

1.  Python csndxogui.py, press "launch server"
2.  enter the remote IP, press enter
3.  connect to both csound servers, make sure you see green lights on both sides
4.  press "duo performance"
5.  to stop, press "stop", "disconnect", "shutdown"