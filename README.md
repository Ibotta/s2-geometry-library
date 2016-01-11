### install the package development tools
```
sudo apt-get install packaging-dev dh-make bzr-builddeb
```

### create the Debian packages
```
./autogen.sh
fakeroot debian/rules binary
```

### install the Debian packages
```
sudo dpkg -i ../libs2_1.0.0-1_amd64.deb
sudo dpkg -i ../libs2-dev_1.0.0-1_amd64.deb
```
