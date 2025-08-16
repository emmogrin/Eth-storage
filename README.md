1️⃣ Enter Ubuntu

[Start here if you're using mobile phone](https://x.com/thecryptoBike/status/1947220001649479951?t=mz_vSrkJBHvnYBpuG4JFWA&s=19)

Skip to the next step if on PC/VPS 


---

2️⃣ Update system & install dependencies
```
apt-get update && apt-get upgrade -y

apt install curl screen iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev ca-certificates -y
```

---

3️⃣ Install NVM & Node.js 18 (manual step)

1. Install NVM:
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```
2. Load NVM into the current shell:
```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```
3. Install Node.js 18 and use it:
```
nvm install 18
nvm use 18
```
> ✅ After this, node and npm should work in the current session.


---

4️⃣ Install EthStorage Ceremony CLI locally
```
mkdir -p ~/trusted-setup-tmp && cd ~/trusted-setup-tmp
npm install @p0tion/phase2cli
```
> This part can be really slow 🐌 on mobile (The price you pay for choosing the cheap path 😂)



---

5️⃣ Authenticate with GitHub
```
npx phase2cli auth
```
Open the URL provided: 
```
https://github.com/login/device
```
Paste the code and authorize EthStorage to access your Gists.




---

6️⃣ Start a screen session ( Vps only)
```
screen -S ceremony
```
This keeps your session running



---

7️⃣ Contribute to the ceremony
```
npx phase2cli contribute -c ethstorage-v1-trusted-setup-ceremony
```
Press Enter for random contribution, or type your own values.


Screen shortcuts:

Minimize: Ctrl+A+D

Resume: screen -r ceremony

Kill inside: Ctrl+C

Kill from outside: screen -XS ceremony quit



---

8️⃣ Clean up after contribution
```
npx phase2cli clean
npx phase2cli logout
rm -rf ~/trusted-setup-tmp
```
> This revokes GitHub authorization and deletes local files.




---

Tips for PC / mobile

Ensure stable Wi-Fi, contribution may take hours.

Keep enough free storage in Termux home.

If your session times out, just re-run npx phase2cli contribute — it resumes from where you left off.


