# Arch-based Linux Package List Backup and Restore

Repo contains my package list backup for future re-installation

## Commands 
#### Backup package in official repository
```bash
pacman -Qqen > pkglist-repo.txt
```

#### Backup package in arch user repository (AUR)
```bash
pacman -Qqem > pkglist-aur.txt
```

### Re-install all of your package
#### Official repository package
```bash
sudo pacman -S --needed - < pkglist-repo.txt
```

#### AUR packages
```bash
for x in $(< pkglist-aur.txt); do yay -S $x; done
```