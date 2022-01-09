<ul>
<ul><h3>Tmux</h3></ul>
  <ul>
    <li><h4>Settings Manager</h4></li>
  <li>Keyboard</li>
  <p> CTRL + ALT + T : launches tmux </p>
    
  <li>tmux config</li>
    <li>Source: <a href="https://www.youtube.com/c/ippsec">IppSec</a></li>
    
```~/.tmux.conf
set -q prefix C-a
bind C-a send-prefix
unbind C-b
    
bind-key j command-prompt -p "join pane from:" "oin-pane -s '%%'"
bind-key s command-prompt -p "send pane to:" "join-pane -t '%%'"
      
set-window-option -g mode-keys vi
      
run-shell /opt/tmux-logging/logging.tmux
```
    
<li>SecLists</li>
<p>https://github.com/danielmiessler/SecLists</p>
    
<li>impacket</li>
<p>https://github.com/SecureAuthCorp/impacket</p>
 
  <h3><ul>IPTables</ul></h3>
  <li><p> iptables -A INPUT -p tcp,udp,icmp -m state --state NEW -j LOG --log-prefix "IPTables New-Connection: " </p></li>
  <p> This puts a log in /var/log/messages whenever a new connection is initiated back to my machine regardless if it's TCP, UDP, or ICMP.</p>
  <p> This will not account for established sessions, only new sessions opened directly to my machine, you can also specify interfaces by appending the -i flag to the end.</p>
  
  <h3><ul>SMB/Samba</ul></h3>
  <p> Add "min protocol = SMB1" under [global] </p>
  
    <h3>Codium</h3>
    <p>sudo apt update && sudo apt install codium</p>
  </ul>
</ul>
