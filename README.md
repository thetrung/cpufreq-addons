cpufreq Addons 
======================================
This small utility was done to customize `cpufreq` tool.

### 1. Usecases
- `cpufreq-set-range` : You want many-cores system to run at lower frequencies at once, for example : 400 ~ 600Mhz only in all cores.
- `cpufreq-setup-PE` : You want a 2P/14E-cores-like system that only run max frequency for 2 first cores then lowest frequency for the rest.

### 2. Setup 
- `git clone https://github.com/thetrung/cpufreq-addons` to your `$HOME`.
- `mv bash_aliases .bash_aliases` (in case you don't have `.bash_aliases` yet)

      sudo chmod +x cpufreq-set-range && sudo chmod +x cpufreq-setup-PE
      sudo mv cpufreq-set* /usr/bin/
      sudo mv cpufreq.service /etc/systemd/system/
      sudo systemctl daemon-reload
      sudo systemctl restart cpufreq.service
   

### 3. Auto-Services
    
    cat << EOF | sudo tee /etc/systemd/system/cpufreq.service
    [Unit]
    Description=CPU powersave
    [Service]
    Type=oneshot
    Restart=always
    ExecStart=usr/bin/cpufreq-set-range 400 550
    [Install]
    WantedBy=multi-user.target
    EOF

Start Service :

    sudo systemctl daemon-reload && sudo systemctl enable cpufreq.service

~ Enjoy ~
