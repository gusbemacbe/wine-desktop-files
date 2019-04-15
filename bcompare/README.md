<h1><img align="middle" alt="Beyond Compare" height="85px" src="../images/icons/bcompare.svg?sanitize=true"/> Beyond Compare</h1>

As you are a KDE user, do you prefer the Windows-based app with enabled GTK 4 theming instead of GTK-based app with horrible theme? You are not alone!

## Installing 

<ol>
  <li>Install firstly:

  ```
  wget -O bcompare.exe 'https://www.scootersoftware.com/BCompare-4.2.9.23626.exe'
  WINEPREFIX=~/Applications/Windows wine ./bcompare.exe /q
  ```
  </li>

  <li>Symlink the BCompare executer (`.exe`) to `/sur/bin/bcompare.exe`:
  
  ```
  sudo ln -sfnr ~/Applications/Windows/drive_c/Program\ Files/Beyond\ Compare\ 4/BCompare.exe /usr/bin/BCompare.exe
  ```
  </li>

  <li>Copy the `bcompare.desktop` which is at this repository, or install quickly via a go:
  
  ```
  wget https://raw.githubusercontent.com/gusbemacbe/wine-desktop-files/master/bcompare/bcompare.desktop -P ~/.local/share/applications/
  ```
  </li>

  <li>Run the command <code>update-desktop-database</code> to refresh the list of desktop files.</li>
</ol>

## Observation

Wine generates automatically new desktop files of Wine apps in the folder `~/.local/share/applications/wine/Programs/`. As you have already created manually this desktop file, you can remove the folder `wine`, unless you want to modify the icon name manually. 