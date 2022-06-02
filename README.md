# mo-docker
Repo for supporting dockerizing Mushroom Observer

TL;DR
./setup

If you want to cleanout all the Docker stuff and start over from a
clean slate:

docker system prune -a


More Details:

You need to have Docker Desktop installed and running.
You can get the latest version from here:

https://www.docker.com/products/docker-desktop/

At work we've been having some issues with the latest version,
4.8.2 (2022-05-18), so I'm currently using 4.8.1 which you can
get from here:

https://docs.docker.com/desktop/release-notes/

Once Docker Desktop is running on your system, check out this
repo and from inside the repo run:

./setup

This should build and launch two containers: mo_app and mo_db.
The mo_db container is a standard MySQL container and it takes
a little while to start up, so after the setup command completes,
the local webserver at http://localhost:3000/ may not be immediately
responsive.  You can check on the health of your containers with:

docker ps

This should list two containers.  If it doesn't, then one or both
containers may have died.  If you run:

docker ps -a

it should list both containers and indicate which ones have exited.
You can see what happened with:

docker logs <container-name>
