# Pcsxr_flatpak
https://github.com/iCatButler/pcsxr
A plugin based PlayStation (PSX) emulator with high compatibility

In gnome-shell use tray icon extension to see legacy system tray icons.
https://extensions.gnome.org/extension/1503/tray-icons/

#### install flathub repo and freedesktop sdk 18.08
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.freedesktop.Sdk/x86_64/18.08
```

#### clone and build flatpak from yaml
```
git clone https://github.com/fastrizwaan/Pcsxr_flatpak.git
cd Pcsxr_flatpak

# build
flatpak-builder --force-clean build-dir io.github.pcsxr.yaml

# install 
flatpak-builder --user --install --force-clean build-dir io.github.pcsxr.yaml

# run
flatpak run io.github.pcsxr
```

#### Build a flatpak bundle file from the above built repo:
```
flatpak-builder --repo="repo" --force-clean "build" io.github.pcsxr.yaml
flatpak --user remote-add --no-gpg-verify "pcsxr" "repo"
flatpak build-bundle "repo" "pcsxr.flatpak" io.github.pcsxr  --runtime-repo="https://flathub.org/repo/flathub.flatpakrepo"

flatpak --user install pcsxr.flatpak
flatpak run io.github.pcsxr
```
