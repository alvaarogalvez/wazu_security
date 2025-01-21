# 28584   Ensure nftables is not installed with iptables. Command: dpkg-query -s nftables Failed

sudo apt-get remove --purge nftables
sudo apt-get autoremove --purge
#comprobamos que lo ha borrado
dpkg-query -s nftables
#reiniciamos el agente
systemctl restart wazuh-agent




# 28590 Ensure auditd is installed. Command: dpkg-query -s auditd Failed

#intalamos
sudo apt-get update
sudo apt-get install auditd

sudo systemctl status auditd

# 28526 Ensure AIDE is installed. Command: dpkg-query -s aide Failed

#instalamos
sudo apt-get update
sudo apt-get install aide

# 28583 Ensure iptables packages are installed. Command: dpkg -s iptables,dpkg -s iptables-persistent Failed

sudo apt-get install iptables-persistent
sudo iptables-save > /etc/iptables/rules.v4
sudo ip6tables-save > /etc/iptables/rules.v6

sudo systemctl enable netfilter-persistent

sudo systemctl restart netfilter-persistent

# 28614 Ensure systemd-journal-remote is installed. Command: dpkg-query -s systemd-journal-remote Failed

sudo apt update
sudo apt install systemd-journal-remote

![Alt text](Pictures/Screenshot_2025-01-21_13_30_20.png)