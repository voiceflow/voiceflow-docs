---
title: Install
deprecated: false
hidden: false
metadata:
  robots: index
---
Install¶
You can use voiceflow-cli by installing a pre-compiled binary (in several ways), using Docker, or compiling it from source. In the below sections, you can find the steps for each approach.

Install a pre-compiled binary¶
homebrew tap¶
Install the Voiceflow CLI:


brew install xavidop/tap/voiceflow
snapcraft¶

sudo snap install voiceflow
aur¶

yay -S cxcli-bin
scoop¶

scoop bucket add voiceflow https://github.com/xavidop/scoop-bucket.git
scoop install voiceflow
chocolatey¶

choco install voiceflow
apt¶

echo 'deb [trusted=yes] https://apt.fury.io/xavidop/ /' | sudo tee /etc/apt/sources.list.d/voiceflow.list
sudo apt update
sudo apt install voiceflow
yum¶

echo '[voiceflow]
name=Vocieflow CLI Repo
baseurl=https://yum.fury.io/xavidop/
enabled=1
gpgcheck=0' | sudo tee /etc/yum.repos.d/voiceflow.repo
sudo yum install voiceflow
nix¶
nixpkgs¶

nix-env -iA voiceflow