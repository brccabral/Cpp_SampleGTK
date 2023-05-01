# Sample GTK App

This projet just creates an empty window using GTK libraries.  

To compile, need to have installed `wxWidgets` https://www.wxwidgets.org/

### Ubuntu
```
apt install libgtk-3-dev libgl1-mesa-dev libglu1-mesa-dev libgstreamer-plugins-base1.0-dev libcurl4-openssl-dev libwebkit2gtk-4.0-dev libgspell-1-dev libsecret-1-dev libnotify-dev
```
I chose to install at `/usr/local`.
```
mkdir buildgtk
cd buildgtk
../configure --with-gtk --with-sdl
make -j10
sudo make install --prefix=/usr/local
sudo ldconfig
```
If install at `/usr/local` need to export to `LD_LIBRARY_PATH`.
```
export LD_LIBRARY_PATH="/usr/local/lib:$LD_LIBRARY_PATH"
```