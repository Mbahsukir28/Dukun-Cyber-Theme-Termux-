# Dukun-Cyber-Theme-Termux-

# Script: dukun-cyber.sh

# Install semua paket pendukung
pkg update -y
pkg install figlet toilet lolcat neofetch cmatrix termux-media-player curl -y

# Buat folder suara dan download efek suara
mkdir -p ~/termux-sfx

# Suara startup + efek ketik
curl -o ~/termux-sfx/sukir-startup.mp3 https://github.com/mohd-akram/termux-startup-sfx/raw/main/hacker-startup.mp3
curl -o ~/termux-sfx/typewriter.mp3 https://github.com/fy0/typewriter-sfx/raw/main/typewriter.mp3

# Tambahkan semua ke ~/.bashrc
cat << 'EOF' >> ~/.bashrc

# ======= LOGIN PALSU MBAH SUKIR =======
clear
echo -e "\e[1;32m"
echo "========================================"
echo "     GERBANG RAHASIA MBAH SUKIR         "
echo "========================================"
echo -e "\e[0m"

read -p $'\e[1;31mNama Pengguna Gaib: \e[0m' user
read -sp $'\e[1;31mMantra Rahasia: \e[0m' pass
echo ""
sleep 1
echo "[$(date)] $user - $pass" >> ~/.login_attempts.txt
echo -e "\nAura cocok... akses diterima..."
sleep 1
clear

# ======= MANTRA PEMBUKA DAN ASCII KERIS =======
termux-media-player play ~/termux-sfx/typewriter.mp3 > /dev/null 2>&1

echo -e "\e[1;33mMembuka portal cyber...\e[0m"
sleep 2

echo -e "\e[1;32mMbah Sukir membaca mantra:\e[0m"
sleep 1
echo -e "\e[3;32m\"Ojo lali karo niat, sambung karo server ghaib...\"
\"Ketik sembarang tapi hasil sakti mandraguna...\"\e[0m"
sleep 2

# ASCII ART KERIS
echo -e "\e[1;32m"
cat << 'KERIS'
       )  (
      (   ) )
       ) ( (
     _______)_
  .-'---------|  
 ( C|/\/\/\/\/|
  '-./\/\/\/\/|
    '_________'
     '-------'
KERIS
echo -e "\e[0m"

sleep 2
termux-media-player play ~/termux-sfx/sukir-startup.mp3 > /dev/null 2>&1
cmatrix -C green -u 3 -b -n &
sleep 2
killall cmatrix > /dev/null 2>&1
clear

figlet "MBAH SUKIR" | lolcat
neofetch
echo -e "\e[1;32mSugeng rawuh, $user. Dunia digital dalam kendalimu.\e[0m"

# PROMPT MBAH SUKIR
PS1="\e[1;35m[DUKUN@SUKIR \W]>\e[0m "

# ALIAS DUKUN CYBER
alias santet='nmap'
alias terawang='nikto'
alias ngintip='tcpdump'
alias mantrain='cmatrix -C green -u 3 -b'
alias kabur='exit'
alias sakti='echo "Mantra berhasil dijalankan oleh Mbah Sukir..."'

EOF

echo -e "\e[1;32mUpgrade Dukun Cyber Full Power selesai! Buka ulang Termux untuk aktifkan kekuatanmu, brayy.\e[0m"
