  node{
      stage('Clone') {
          checkout scm
      }
      stage('Creation user'){
          'apk add sshpass'
          'rm -fr /root/.ssh/'
          'ping app-salaire.toussoul.form'
          'ssh-keygen -q -t rsa -N \'\' -f "/root/ssh/id_rsa"'
          'sshpass -p "admin" ssh-copy-id  -o stricthostkeychecking=no "root@app-salaire.toussoul.form"'
      }
      stage('Ansible') {
        ansiblePlaybook (
            colorized: true,          
            playbook: 'playbook.yml',
            inventory: 'hosts.yml'
        )
      }
  }
