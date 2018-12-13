# Docker

tags: docker, cli, containers

Docker is a tool to wrap projects with a specific infrastructure, which you define. Is like Virtual Machines, but better because it resuses SO resources, filesystem and so on.

This sections aim's to keep a list of useful things to use in docker.

## Keep logs of dead containers

When we run a container and it finishes the main job, it'll be killed and every log will be vanished.
To keep track of dead containers, we need to change the log driver and it's done!

Check [this link](https://stackoverflow.com/questions/43663013/access-logs-of-a-killed-docker-container/43663253) to see how to do that.