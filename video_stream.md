---
layout: post
title: Setup the Video Stream
---

In this part of the instructions you will setup the video stream.
First, make sure you have Multipath-TCP (MPTCP) version 0.94.0 installed on your system.
We used Ubuntu 16.04 with kernel version 4.14.24.
See the official [Multipath-TCP website](https://multipath-tcp.org/pmwiki.php/Users/HowToInstallMPTCP?) for installation instruction.
After that, make sure you set the MPTCP options correctly:

```
sudo sysctl -w net.mptcp.mptcp_enabled=1
sudo sysctl -w net.mptcp.mptcp_path_manage=fullmesh
sudo sysctl -w net.mptcp.mptcp_scheduler=redundant
sudo sysctl -w net.mptcp.mptcp_checksum=1
sudo sysctl -w net.mptcp.mptcp_syn_retries=3
```

Up next, install required software, which is docker-ce and docker-compose. For instructions see the guides on their homepage for [docker-ce](https://docs.docker.com/install/linux/docker-ce/ubuntu/) and [docker-compose](https://docs.docker.com/compose/install/).

After that, download and prepare the video. We provide a shell script for that. Checkout out the following repo and run the download script

```sh
git clone https://github.com/umr-ds/seamcon-videostream.git
cd seamcon-videostream
./download_video.sh
```

This will create a directory `./video/`, where all required files are stored.

Our setup reports various statistics about the video stream. Therefore, we deploy a JSON server instance, where these stats are stored in a file called `db.json`. We prepared an empty example, which should be used. Rename the example file and set a symlink so that JSON server uses the right file.

```sh
cp db.json_empty db.json
ln -s db.json .~db.json
```

Additionally, you have to set the endpoint of your JSON server machine. This is done in the file `dashloader/app.js`, line 36150. Just replace the `API_URL` with the IP or the hostname of the machine and the port where the JSON server docker container (which will be started in a second) is running.

Finally, for starting the stream, start all containers with our provided docker compose file.

```sh
docker-compose up -d
```

You should see the video at `http://<IP_OF_YOUR_MACHINE>:8080`. The stats of the video stream are in the `db.json` file. Alternatively, you can see them at `http://<IP_OF_YOUR_MACHINE>:3000`.

Cool, the video stream is running. Now head over to the [final step.](install_apps)
