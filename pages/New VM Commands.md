- Multipass: #VanMoof 
  cpus=8 memory=8G disk=128G
  
  ```zsh
  git config --global user.email "neeley.corcoran@gmail.com"
  git config --global user.name "neeleythere"
  
  ssh-keygen -t ed25519 -C "neeley@vanmoof.com"
  eval "$(ssh-agent -s)"
  ssh-add ~/.ssh/id_ed25519
  cat ~/.ssh/id_ed25519.pub
  
  ```
  
  ```zsh
  sudo add-apt-repository ppa:deadsnakes/ppa   
  sudo apt update
  sudo apt upgrade
  sudo apt install python3.7-venv python3.7-dev
  python3 -m venv venv
  ```
  add venv to .git/info/exclude
  ```zsh
  source venv/bin/activate
  pip install --upgrade pip
  pip install pre-commit requests zc.buildout coverage
  sudo apt install gcc libevent-dev libfreetype6-dev libjpeg62-dev libldap2-dev libpq-dev libsasl2-dev libxml2-dev libxslt1-dev python-dev-is-python3 postgresql
  sudo apt install -y --no-install-recommends build-essential
  pip install "setuptools<58.0.0"
  ```
  
  Create file `~/odoo/local.cfg`:
  
  ```text
  [buildout]
  extends = buildout.cfg
  
  [odoo]
  options.db_name = odoo
  options.dbfilter = False
  options.http_port = 8069
  options.test_enable = True
  options.without_demo = False
  options.max_cron_threads = 1
  ```
  
  In `~/odoo` run:
  ```zsh
  git config pull.rebase false
  buildout -c local.cfg
  ```