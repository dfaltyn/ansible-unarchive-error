# ansible-unarchive-error
Demonstrate a problem with ansible-unarchive in ansible 2.0.1.0 running on Centos 7 3.10.0-327.3.1.el7.x86_64

1) Assume you have a host with ansible installed named ansible-server
2) Assume you have an extra host named coffeecup
3) Ensure coffecup is in the file dev (an ansible inventory file)
4) Play the following ansible playbook 

ansible-playbook -i dev -u root -k archive-issue.yml --extra-vars="other_host=coffeecup"

At the end of the play, /$USER/.ansible/tmp/ will contain a dir with the archive. 

This should not be there at the end of the play.

