# Desktop Files of Windows Apps

Stored in `~/.local/share/applications/`, desktop files of Windows apps – Adobe Illustrator, Adobe Photoshop, Affinity Designer, Beyond Compare, Lunacy and WInMerge compatible with icons themes and GTK themes.

## Basic and quick installation

<ol>

<li>Open the terminal and you need to create the directories <code>~/Applications/Windows</code>:
  
  **Tip:** If you want to keep the Windows apps in your HDD instead of SSD, avoiding the size increasing, follow:

   ```
   # Create the folder and subfolder in the HDD instead of the SSD
   mkdir -p /data/your_hdd_name/Applications/Windows

   # Symlink HDD to SSD
   ln -sfnr /data/your_hdd_name/Applications/ ~/Applications

   # Initialize new Wine prefix
   WINEPREFIX=~/Applications/Windows wineboot –init
   ```

   If you receives an error that Wine could not find a Gecko package, you need to install Gecko package firstly:

   ```
   wget -O wine-gecko-64.msi 'http://dl.winehq.org/wine/wine-gecko/2.47/wine_gecko-2.47-x86_64.msi'
   WINEPREFIX=~/Applications/Windows wine msiexec /passive /i ./wine-gecko-64.msi
   ```
</li>

<li> Change the system to Windows 10 (for the correct installation of .NET Framework 4.0):

  ```
  WINEPREFIX=~/Applications/Windows winetricks win10
  ```
</li>

<li> The package .NET Framework 4.0 is important for some apps to work with Wine, download and install:

   ```
   wget -O dotnet.exe 'http://download.microsoft.com/download/9/5/A/95A9616B-7A37-4AF6-BC36-D6EA96C8DAAE/dotNetFx40_Full_x86_x64.exe'
   WINEPREFIX=~/Applications/Windows wine ./dotnet.exe /q
   ```
</li>

<li>Open Winecfg:

   ```
   WINEPREFIX=~/Applications/Windows winecfg
   ```
  
  <ol>
      <li>Select the guide ‘Libraries’ and type ‘mscoree’ in the box of ‘New override for library’. Select this library and select ‘Edit’. Select ‘Native (Windows)’.</li>
      <li>Select the guide ‘Staging’ and mark ‘Enable VAAPI as backend for DXVA2 GPU decoding’ and ‘Enable GTK3 Theming’.</li>
  </ol>
</li>

<li>Download and install another important package – .NET Framework 4.7.2:

   ```
   wget -O dotnet47.exe 'http://download.microsoft.com/download/D/D/3/DD35CC25-6E9C-484B-A746-C5BE0C923290/NDP47-KB3186497-x86-x64-AllOS-ENU.exe'
   WINEPREFIX=~/Applications/Windowsr wine ./dotnet47.exe /q
   ```

   If you still receive the same error of missed Gecko package, repeat at the item 1 end.
</li>

</ol>

## Install your favourite Windows app

Please choose one of subfolders at this repository. At the subfolder, you will read the README about how to install an application