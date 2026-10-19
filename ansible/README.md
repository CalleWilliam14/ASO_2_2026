# Generar clave ssh para conectarse a todas las maquinas:

ssh-keygen -t ed25519 -f /root/.ssh/ansible_ed25519

# Copiar la clave a cada maquina:

ssh-copy-id -i /root/.ssh/ansible_ed25519.pub root@192.168.101.201
ssh-copy-id -i /root/.ssh/ansible_ed25519.pub root@192.168.101.<IP_DEST>

# Comprobar conexion:

ansible servers -m ansible.builtin.ping

# Ejecutar el playbook:

ansible-playbook playbook_samba.yml --ask-vault-pass