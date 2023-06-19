##Questions

Question 1-2 Why do we need a multistage build? And explain each step of this dockerfile.
Answer: So we have a standardized way of building our app that doesn't rely on the version of binaries, etc.  of our machine.







##Tips

Tip : Why should we run the container with a flag -e 
to give the environment Variable ?
Answer so we can change the content of the variable at runtime
without re-building the whole image


Tip: Why do we need a volume to be attached to our postgres container?
Answer: So we keep the databases data even after the container has been removed.


Tip: Why do we need a reverse proxy ?
Answer: So we can scale /alter our backend without our end user noticing


Tip: Why is docker-compose so important ?
Answer: It allows us to run a multi-containers project easily.


Tip: Why do we put our images into an online repo ?
Answer: So we can fetch them from anywhere, especially
from github actions and Ansible.