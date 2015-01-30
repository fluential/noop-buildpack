# noop-buildpack
Empty buildpack that does nothing. It just waits. The idea is that the app deployed to PWS will bootstrap itself via scripts stored in ".profile.d" directory.
If you have a binary that is runnable directly, just start it in your start.sh (or other) script. There's no need to use any buildpack in that case.

## Usage
```bash
$ mkdir app
$ cd app
$ mkdir .profile.d
$ touch .profile.d/start.sh
$ chmod +x .profile.d/start.sh
$ vim .profile.d/start.sh   # edit start.sh to your liking, WD is root directory of the app folder, use any linux64 binaries
$ cf push my-app -b https://github.com/igm/noop-buildpack
```

## Sample
Sample demo project that uses noop-buildpack for serving static files can be found here:
https://github.com/igm/static-files-demo
