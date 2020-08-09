# Configure my personal machine with ansible

Sometimes I need to reinstall my machine and after that there a lot of work to do.

* Install updates
* Add new repositories
* Install packages
* Configure my user groups
* ...

> I'm using the [regolith](https://regolith-linux.org/) as my main [WM](https://en.wikipedia.org/wiki/Window_manager), you can change this on the [respective task file](./roles/wm/tasks/main.yml)

As a programmer, I'm lazy, specially when I need to do **repetitive things**. And when I need to do these **repetitive things**, I tends to do the same thing with some kind of automation tool. For this specific task, I'm using [ansible](https://www.ansible.com/).

All I need todo run the commands bellow after re/install my O.S.([Ubuntu 20.04](https://releases.ubuntu.com/20.04/)) :

```bash
sudo apt update && \
sudo apt dist-upgrade -y && \
sudo apt autoremove && \
sudo reboot
```

Why I reboot the O.S.?

> Because this is a fresh installation and there's a high probability that exists a kernel update.
```bash
sudo apt update && \
sudo apt install software-properties-common git ansible python3-apt && \
git clone git@github.com:eltonplima/configure-my-os-with-ansible.git && \
cd configure-my-os-with-ansible && \
sudo ansible-playbook playbook.yml
```

