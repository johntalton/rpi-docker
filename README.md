# Docker files for rpi setup

a set of thin docker files. usefull for development env, or building a serverless system arch, self-hosted air-gapped systems, etc.

## Structure

each docker image (app/env) is rooted on base / raspbian (a locally created image (via one of the many mkimage impl))

## Typical depolyment

pi with raspbian and docker (assumed not other deps.)

local docker reposetory instance setup on swarm where each of these images are published for the swarm to access. along with gitd and other persistent service level apps (gpsd / mosquitto / etc) started on labled mapped docker nodes. 

further nodejs nodes are depolyed mapped to git repositories (via mapping lables and hand spun for development etc)

remaining architecture is assumed nodejs based and left for reader
