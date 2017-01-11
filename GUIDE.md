## quickstart

1. ["Fork" this repository on github](https://github.com/Madek/madek-instance/fork)
  *(only required if you want to receive update notifications)*

1. clone it to a computer running Linux or macOS: `git clone git@github:yourUserName/madek-instance my-madek`

1. setup:
  ```sh
  which ansible-playbook || echo "install ansible first!"
  cd my-madek
  git submodule update --init Madek
  cd Madek && git reset --hard origin/release && git submodule update --init --recursive deploy && cd -
  ```

1. prepare a server running [Debian `jessie`](https://www.debian.org/releases/jessie/),
  log in as root via SSH and do `apt-get install python`

1. configure
  - fill in hostname in file `hosts`
  - global config in file `group_vars/madek.yml`
  - per-host config in file `host_vars/madek.example.com.yml`, rename it to match the hostname

1. install `ansible-playbook -i hosts Madek/deploy/play_setup-and-deploy.yml`
