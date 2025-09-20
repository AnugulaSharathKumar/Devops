### Ansible-Playbooks
**1. Ping all host**
```yaml
---
- name: Test Connectivity
  hosts: all
  become: yes
  tasks:
    name: ping all servers
    ping:
```
**2.Install Apache**
```yaml
---
- name:Install Apache
  hosts: all
  become: yes
  tasks:
    apt:
      name: apache
      state: present
```
**3. Start/Stop Service**
```yaml
---
- name: Start and stop the Nginx Service
  hosts: all
  become: yes
  tasks:
   -service:
     name: Start the nginx service
     state: started
     name: Stopped the nginx Service
     state: stopped
```
**4.Create a User**
```yaml
---
- name: Creating user
  hosts: all
  become: yes
  tasks:
    -user:
       name: Devops
       state: present
       group: sudo
```
**5.Change Password**
```yaml
---
-  name: Change password for a Linux user
   hosts: all
   become: yes
   tasks:
    - user:
        name: devops
        password: "{{ 'Password123' | password_hash('sha512') }}"
```
**6. Update Packages**
```yaml
---
- name: Update Packages
  hosts: all
  become: yes
  tasks:
    - apt:                           # Use the apt module (Debian/Ubuntu package manager)
        upgrade: dist                # Perform a full distribution upgrade
```
**7. Copy File**
```yaml
---
```
**8. Download File**
```yaml
---
```
**9. Set Host name**
```yaml
---
```
**10. Create Directory**
```yaml
---
```
**11. Deploy HTML Page**
```yaml
---
```
**12. Check Disk Space**
```yaml
---
```
**13. Install Git**
```yaml
---
- name: Install the Git
  hosts: all
  become: yes
  tasks:
   - apt:
      name: git
      state: present
```
**14. Install Docker**
```yaml
---
- name: Install docker
  hosts: all
  become: yes
  tasks:
   - apt:
      name: docker.io
      state: present
```
**15. Check Uptime**
```yaml
---
```
**16. Configure UFW Firewall**
```yaml
---
```
**17. Deploy Node.js App**
```yaml
---
```
**18. Deploy Flask App**
```yaml
---
```
**19. Install MySQL**
```yaml
---
- name: Install MYSQL
  hosts: DB hosts
  become: yes
  tasks:
   - apt:
      name: mysql-server
      state: present
```
**20. Install PostgreSQL**
```yaml
---
- name: Install PostgreSQL
  hosts: DB hosts
  become: yes
  tasks:
   - apt:
      name: postgresql
      state: present
```
**21. Create MySQL User/DB**
```yaml
---
```
**22. Backup MySQL**
```yaml
---
```
**23. Deploy WAR to Tomcat**
```yaml
---
```
**24. Install Jenkins**
```yaml
---
- name: Install Jenkins
  hosts: CI Hosts
  become: yes
  tasks:
   - apt:
      name: jenkins
      state: present
```
**25. Create Cron Job**
```yaml
---
```
**26. Manage Env Vars**
```yaml
---
```
**27. Set File Permissions**
```yaml
---
```
**28. Configure SSH Access**
```yaml
---
```
**29. Install Prometheus Node Exporter**
```yaml
---
```
**30. Install Grafana**
```yaml
---
- name: Install Grafana
  hosts: Grafana Hosts
  become: yes
  tasks:
   - apt:
      name: grafana
      state: present
```
**31. Deploy Docker Container**
```yaml
---
```
**32. Build Docker Image**
```yaml
---
```
**33. Configure kubectl**
```yaml
---
```
**34. Deploy K8s Manifest**
```yaml
---
```
**35. Monitor Logs**
```yaml
---
```
**36. Rolling Update Web App**
```yaml
---
```
**37. Configure HAProxy**
```yaml
---
```
**38. Install Elasticsearch**
```yaml
---
- name: Install Elasticsearch
  hosts: all
  become: yes
  tasks:
   - apt:
       name: elasticsearch
       state: present
```
**39. Install Kibana**
```yaml
---
- name: Install Kibana
  hosts: all
  become: yes
  tasks:
   - apt:
       name: kibana
       state: present
```
**40. Install Logstash**
```yaml
---
- name: Install Logstash
  hosts: all
  become: yes
  tasks:
   - apt:
      name: logstash
      state: present
     
```
**41. Install Kafka**
```yaml
---
```
**42. Install Zookeeper**
```yaml
---
- name: Install Zookeeper
  hosts: all
  become: yes
  tasks:
    - apt:
        name: zookeeper
        state: present
```
**43. Install RabbitMQ**
```yaml
---
- name: Install RabbitMQ
  hosts: all
  become: yes
  tasks:
   - apt:
       name: rabbitmq-server
       state: present
```
**44. TLS with Let’s Encrypt**
```yaml
---
```
**45. Deploy Terraform**
```yaml
---
```
**46. Ansible with Jenkins**
```yaml
---
```
**47. Run Trivy Scan**
```yaml
---
```
**48. Harden Linux**
```yaml
---
```
**49. Provision AWS EC2**
```yaml
---
```
**50. Multi-tier App Deployment**
```yaml
---
```



