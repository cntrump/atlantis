# Build and Use

```shell
### First install and setup theos
if [ ! -d /opt/theos ]; then
  sudo git clone --recursive https://github.com/theos/theos.git /opt/theos
fi

export THEOS=/opt/theos
export THEOS_DEVICE_IP=YouriPhoneIP

### Build tweak
if [ ! -d atlantis ]; then
  git clone https://github.com/cntrump/atlantis.git
fi

pushd atlantis/theos

# build for release
make -j FOR_RELEASE=1
make package

#before install, make sure install applist, preferenceloader from cydia
make install

### Phone will restart SpringBoard, then Open Settings - Atlantis enable/disable app you want
### restart the target app, and you can see network traffics on Proxyman
popd
```

<img src="assets/settings1.png" width="160"/>
<img src="assets/settings2.png" width="160"/>

![proxyman](assets/ProxyMan.png)
