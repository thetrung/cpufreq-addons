cpufreq Addons 
======================================
This small utility was done to customize `cpufreq` tool.

### 1. Usecases
- `cpufreq-set-range` : You want many-cores system to run at lower frequencies at once, for example : 400 ~ 600Mhz only in all cores.
- `cpufreq-setup-PE` : You want a 2P/14E-cores-like system that only run max frequency for 2 first cores then lowest frequency for the rest.

### 2. Setup 
- git clone this repo to your `$HOME`.
- `mv bash_alias .bash_alias` in case you don't have bash_alias yet, else just add aliases for those scripts.
- `sudo chmod +x cpufreq-set-range && sudo chmod +x cpufreq-setup-PE`

~ Enjoy ~
