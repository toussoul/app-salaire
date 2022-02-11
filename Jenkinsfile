node{
    stage('Clone') {
        checkout scm
    }
    stage('Creation user'){

        '''
        FILE=/etc/resolv.conf
        if [ -f "$FILE" ]; then
            echo "$FILE exists."
        else 
            echo "$FILE does not exist."
        fi

        '''
    }
    stage('Ansible') {
      ansiblePlaybook (
          colorized: true,          
          playbook: 'playbook.yml',
          inventory: 'hosts.yml'
      )
    }
}
