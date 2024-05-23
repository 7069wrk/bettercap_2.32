# bettercap_2.32

`this repository is to communicate the process to get BETTERCAP to work with UI`

Please note that this process will install GO onto the system.  you can remove it once complete or you can spin up a clean system on which to compile - choice is yours

## Create a place for all this to happen in - I chose /tmp
`sudo mkdir /tmp/bettercap`

`cd /tmp/bettercap`

## NOTE if any of these fail - this process will not be able to be completed. 
`sudo apt-get install -y wget unzip libpcap0.8-dev golang-go libusb-1.0-0-dev libnetfilter-queue-dev`


## let's get the 2.32.0 archive
`wget --continue --quiet https://github.com/bettercap/bettercap/archive/refs/tags/v2.32.0.tar.gz`

## NOT NEEDED IF THIS IS FIRST TRY, but is needed if you are doing this for a second time 
`rm -Rf ./bettercap-2.32.0`

`tar -zxf ./v2.32.0.tar.gz`

`cd bettercap-2.32.0`

`./build.sh all`

## IF you do not see a message like below - this has failed for one reason or another. those reasons will be specific to your environment and access.
```
@ Building for all ...
@ Building linux/amd64 ...
@ Creating archive bettercap_linux_amd64_2.32.0.zip ...
```

## IF no errors, you can CD into build, extract and copy the  compiled BETTERCAP
`cd build`

`unzip bettercap_linux_amd64_2.32.0.zip`

`sudo cp bettercap /usr/bin/bettercap`

`cd ~`

`sudo bettercap -eval "caplets.update; ui.update; q"`

`sudo bettercap -caplet http-ui`

## Now you should be able to open your browser of choice and navigate to 127.0.0.1:80 and you will see the UI

![image](https://github.com/7069wrk/bettercap_2.32/assets/102612356/15df1f15-a988-4f49-8ee0-46f1269d5c20)



# Note - 
## if you want to remove any of the installs that were performed in the beginning - you can do so now.
