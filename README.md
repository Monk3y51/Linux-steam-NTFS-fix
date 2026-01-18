# Linux-steam-NTFS-fix
How to fix proton not working with games stored on a NTFS drive

## why it doesnt work
Proton/ Wine doesnt like ntfs drives, it is possible to store your games on a ntfs drive that windows also uses, this saves you from having to install games 2x on the same pc.

## howto:
### Windows:
go into Windows settings and turn off fast boot

### Linux
go into your disk manager, I am using Fedora with Gnome so I will refer to it at Disks moving forward.

select the ntfs drive with your steam games are installed to

on Disks under the paritions on the SSD is a cog button, clicking this gives an option for `Mount at system startup`.

once in this menu turn on *Mount at system startup*, *Show in user interface* and ensure *Require additional authorisation to mount* is disabled

save and reboot

Now you need to create a symlink between the compatdata folder on your os drive and games drive

To make the symlink copy the following into a text editor: `ln -s [source] [link]`

Set source to your compatdata folder on the Fedora SSD usually found at /home/**YOURUSERNAME**/.steam/steam/steamapps/compatdata

Set link to where the compatdata folder is currently on the Games SSD, once noted down delete the compatdata folder from the Games SSD

Enter the command into terminal to create the link, once done check the compatdata folder on the Games SSD has a little arrow symbol to the top right of it. Reboot and enjoy playing games.
