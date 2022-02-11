  node{
      stage('Clone') {
          checkout scm
      }
      stage('test') {
        echo "172.16.171.130 app-salaire.toussoul.form" >> /etc/hosts
        apk add sshpass
        'rm -fr /root/.ssh/*'
        'ssh-keygen -q -t rsa -N \'\' -f "/root/.ssh/id_rsa"'
        sshpass -p "admin" ssh-copy-id  -o stricthostkeychecking=no "root@app-salaire.toussoul.form"
      }
      stage('Ansible') {
        ansiblePlaybook (
            colorized: true,          
            playbook: 'playbook.yml',
            inventory: 'hosts.yml'
        )
      }
  }
