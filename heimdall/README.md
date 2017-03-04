# Docker image for Heimdall

https://github.com/Benjamin-Dobell/Heimdall

## Usage

You need to `adb reboot bootloader` beforehand
or start the phone with *VolumeDown + Home + Power*
and accept the disclaimer.

```bash
IMG=<path_to_recovery_img>

source_dir=$(dirname $IMG)
source_file=$(basename $IMG)

docker run -it --rm \
    --device /dev/bus/usb:/dev/bus/usb \
    --volume $source_dir:/data \
    maxjakob/heimdall \
    flash --RECOVERY /data/$source_file --no-reboot --verbose
```
