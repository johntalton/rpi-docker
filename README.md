# Docker files for rpi setup

Repo containing images used on a small set of raspberry pi's.  Can be used to assemble local application cluster.  

Because of this use case these images are only published into a local docker repository within the cluster.  



## Images

A set of images falling into these gorups General / Services / Application / Misc.  Each image attpets to build on
existing image.  


### Base

All images are based on this root.  And at this point acts as an alias.

### Console

Most of the tools / toys that one would want inside of a containor to diagnose 
issues related to docker itself (like setting up networks or volumes etc).

This is considered an exceptabily fat containor as it should only be used for dev/diag.

---

### CouchDB (1/2)

Instance of CouchDB uncofigured.  Can be deploied in single mode or swarm.  Left to user.

### Git Deamon

Creates a local git deamon service.  this can aid in local development and in auto deployment systems. 

### GPS Deamon

While this is an application in itself (gpsd) it is considers a service for the cluster, and not external application service.

---

### NodeJS

Basic nodeJS containor for application needs

### NodeJS + GPIO

Similar to NodeJS, but adds some GPIP specific tweeks that shoidn't be included for regurlar applications.

---


### Xorg

Attempt at getting X running inside the containor so that it can be distributed.


