# deploy descent box to digital ocean

    ansible-playbook -i deploy/hosts deploy/deploy_digitalocean_playbook.yml  --vault-password-file=conf/vault_pass.txt

wait for DNS to propagate with "nslookup immanentizing.eschaton.quest"

- ansible-playbook -i deploy/hosts deploy/secure_playbook.yml
- ansible-playbook -i deploy/hosts deploy/playbook.yml

# run

- on server:
  - (update ~/.vnc/xstartup or click through errors)
  - vncserver -localhost -nevershared :1
- on local box:
  - ssh -L 59000:localhost:5901 -C -N -F local/ssh_config immanentizing.eschaton.quest
  - vncviewer localhost::59000
  - (or just run the client on the server over X)
- on vnc client:
  - /usr/games/d1x-rebirth -nowindow
- on server:
  - vncserver -kill :1

# notes

- https://retropie.org.uk/forum/topic/28969/what-files-are-needed-for-descent-1-and-2-with-dxx-rebirth-retropie
- maps https://sectorgame.com/dxma/
