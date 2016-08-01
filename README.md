# kibana-selenium
Kibana testing framework which uses selenium webdriver and phantomjs.


## Pre-Setup
In order to ensure operation in headless mode you will need to install phantomJS
```
    apt-get install phantomjs
```

## Install

```bash
-Optional: Best practice is to setup a virtualenv before proceeding.
    pip install virtualenv
    virtualenv ~/venv/kib-sel
    . ~/venv/kib-sel/bin/activate

-Required: These steps are needed everytime you rebuild the project.
    cd /opt && git clone https://github.com/Rydor/kibana-selenium.git   
    cd kibana-selenium
    pip install -r requirements.txt
    export PYTHONPATH=$(pwd)

(Still needs work... as in it does not exist yet :D)
-Configuration file generator: This will create the configuration file needed for test execution
    python config-gen.py
    
    
-Current configuration management:
    user:
        kibana
    password: on infra
        grep -R "kibana_password" /etc/openstack_deploy/user_extras_secrets.yml
    external_vip: on infra
        grep -R "external_lb_vip_address" /opt/rpc-openstack/jenkins-oa/inventory/group_vars/qe-iad3-lab03.yml
```

## Test execution

```
cd /opt/kibana-selenium/testrepo/kibana
python kibana.py
```
