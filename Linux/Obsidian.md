Ниже приведены инструкции по установке Obsidian на Linux

`sudo apt install flatpak`
`flatpak --version`
`flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`
`flatpak search obsidian`
`flatpak install md.obsidian.Obsidian`


----

Оригинал инструкции
https://askubuntu.com/questions/1439878/how-to-install-obsidian-1-0-3-on-ubuntu-22-04
1. Install flatpak `sudo apt install flatpak`
2. Check version to make sure it is installed `flatpak --version`
3. Enable Flathub to search apps from command line `flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo`
4. Search is done by `flatpak search <app_name>`
5. Check the Application ID and run the installation with the application ID. I found it easier than choosing the right name. `flatpak install <app-id>`

Then I went on to look for Obsidian from Flathub.

1. Search Obsidian: `flatpak search obsidian`
2. Look for _md.obsidian.Obsidian_ application ID `flatpak install md.obsidian.Obsidian`

After system restart Obsidian showed up in the application launcher.