## youtube-dl

Environment for running [youtube-dl](https://github.com/rg3/youtube-dl) in docker.

* built on top of `alpine` base image
* includes `ffmpeg` in order to allow `youtube-dl` stitch together high quality videos, which are generally served as separate audio and video tracks
* uses `crond` to periodically check for updates on a list of subscribed channels
* 124 MB

### Example usage:

Start the cron daemon:

```bash
$ docker run -it --rm -v "$(pwd):/base" hajitorus/youtube-dl
```

