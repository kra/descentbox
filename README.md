# deploy descent box to digital ocean

    ansible-playbook -i deploy/hosts deploy/deploy_digitalocean_playbook.yml  --vault-password-file=conf/vault_pass.txt

wait for DNS to propagate with "nslookup immanentizing.eschaton.quest"

- ansible-playbook -i deploy/hosts deploy/secure_playbook.yml
- ansible-playbook -i deploy/hosts deploy/playbook.yml

# run

- on server:
  - XXX update ~/.vnc/xstartup startxfce4 &
  - tightvncserver -nolisten tcp -localhost -nevershared :1
- on local box:
  - ssh -L 59000:localhost:5901 -C -N -F local/ssh_config immanentizing.eschaton.quest
  - vncviewer localhost::59000
- on vnc client:
  - /usr/games/d1x-rebirth -nowindow
- on server:
  - tightvncserver -kill :1

# notes

asset file locations
https://retropie.org.uk/forum/topic/28969/what-files-are-needed-for-descent-1-and-2-with-dxx-rebirth-retropie

- for vnc service
- https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-20-04

