# nightmare
SMRTCON EXP AND VULN SCAN ICEPHISH

1. Update Your System
Open your terminal and run:
sudo apt update && sudo apt full-upgrade -y
This keeps your Kali system up to date.

2. Install Essentials
3. sudo apt install -y build-essential python3 python3-pip python3-venv git curl libssl-dev libffi-dev

4. 3. Install Docker & Docker Compose
   4. Install Docker: sudo apt install -y docker.io
sudo systemctl enable --now docker

Run Docker without sudo: sudo usermod -aG docker $USER
Log out and back in after this command.

Install Docker Compose Plugin:

sudo apt install -y docker-compose-plugin
Check versions:docker --version
docker compose version
4. Install Python and pip
sudo apt install -y python3 python3-pip python3-venv
Check versions:

python3 --version
pip3 --version
5. Install Node.js and npm
We’ll use NodeSource to get the latest version:

curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
Check versions:

node -v
npm -v
6. Install Metasploit Framework
sudo apt install -y metasploit-framework
Launch it with:

msfconsole
7. Install Social-Engineer Toolkit (SET)
sudo apt install -y set
Run it:

setoolkit
8. Install PenTesters Framework (PTF)
git clone https://github.com/trustedsec/ptf.git
cd ptf
pip3 install -r requirements.txt
./ptf
Inside the tool, type:

use modules/install_update_all
9. Install PayloadsAllTheThings
sudo apt install -y payloadsallthethings
Browse payloads:

cd /usr/share/payloadsallthethings
ls
10. Clone the Nightmare Web3 Toolkit
Replace the URL with your actual GitHub repo:
cd /opt
git clone https://github.com/YOURUSERNAME/nightmare-web3-toolkit.git
cd nightmare-web3-toolkit
Install requirements:

pip3 install -r requirements.txt
npm install
11. Set Up Discord Bot
Go to Discord Developer Portal

Create a new app and bot

Copy the Bot Token

Create a .env file in the bot/ folder:

echo "DISCORD_TOKEN=your-discord-token-here" > bot/.env
Important: Never share your bot token. Never commit it to GitHub.

12. Run the Discord Bot
Go into the bot folder:

cd bot
npm install
node index.js
Or for Python:

pip3 install -r requirements.txt
python3 bot.py
13. Add Security to Bot
Edit the bot’s code to only allow specific users. In Python:

ALLOWED_USERS = {"123456789012345678"}
if str(message.author.id) not in ALLOWED_USERS:
    return
In JavaScript (Node.js Discord bot):

const allowedUsers = ["123456789012345678"];
if (!allowedUsers.includes(message.author.id)) return;
14. Make the Bot Auto-Start on Boot
Option 1: PM2 (easiest for Node.js bots)

npm install -g pm2
cd /opt/nightmare-web3-toolkit/bot
pm2 start index.js --name nightmare-bot
pm2 save
pm2 startup systemd
Option 2: Docker restart policy Add this to docker-compose.yml:

restart: unless-stopped
15. Run Exploits from CLI
Examples (replace with real commands):
