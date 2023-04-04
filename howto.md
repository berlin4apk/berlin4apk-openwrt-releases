# berlin4apk-openwrt-releases
build via https://github.com/berlin4apk/openwrt-fastbuild-actions

# OpenWrt custom packages

## Description

GitHub Pages repository for own OpenWrt binary packages feed.

## Usage
```sh
. /etc/os-release
[ -f /lib/libustream-ssl.so ] && echo "libustream already installed" || opkg install libustream-mbedtls
(! grep -q berlin4apk /etc/opkg/customfeeds.conf) && (
wget -q https://berlin4apk.github.io/openwrt-packages/public.key -O /tmp/public.key && 
opkg-key add /tmp/public.key && rm /tmp/public.key &&
echo 'src/gz berlin4apk https://berlin4apk.github.io/openwrt-packages/releases/$VERSION_ID/packages/$OPENWRT_ARCH/packages' >> /etc/opkg/customfeeds.conf &&
echo "Feed added successfully!"
) || echo "Feed added already. Skip."

# then
opkg install [package-name]

#or for snapshot
echo 'src/gz berlin4apk https://berlin4apk.github.io/openwrt-packages/releases/snapshot/$OPENWRT_ARCH/packages' >> /etc/opkg/customfeeds.conf
```

[List packages](./packages/)


## Based on
* [hnw/openwrt-packages](https://github.com/hnw/openwrt-packages)
* [openlumi/wiki](https://github.com/openlumi/wiki)
* [openlumi/openwrt-packages](https://github.com/openlumi/openwrt-packages)
* [openlumi/releases](https://github.com/openlumi/releases)

## Supporting platforms and packages

Work in Progress
  
## Packages

Work in Progress

## License

See [LICENSE](LICENSE) file.

# Disclaimer

I take NO responsibility and / or responsibility for how you choose to use any file available here. By using any of the files available in this repository, you understand that you are AGREEING TO USE AT YOUR OWN RISK. Once again, ALL files available here are for EDUCATION and/or RESEARCH purposes ONLY.

