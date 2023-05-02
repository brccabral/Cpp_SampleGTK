# Sample GTK App

This projet just creates an empty window using GTK libraries.  

To compile, need to have installed `wxWidgets` https://www.wxwidgets.org/

## Ubuntu
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

## Windows
Download the `Windows ZIP` and extract it at some location, we will call it `%WXWIN%`.  
Go to `%WXWIN%\build\msw` and open the solution file for your Visual Studio version, I opened `wx_vc17.sln`.  
In Visual Studio, menu `Build`, then `Batch Build...`. Select all and click Build. It will take some minutes to complete.  

### Visual Studio

Create a new project by selecting "Windows Desktop Application" template, but delete all code provided. Add classes `cApp` and `cMain` using the code in this project.

### VSCode

Configure CMake to use `wxWidgets_ROOT_DIR`
```
mkdir build
cd build
cmake -DwxWidgets_ROOT_DIR=%WXWIN% ..
```