# cyberrange-kali-githubactions
[![kali cyberrange CI workflow](https://github.com/githubfoam/cyberrange-kali-githubactions/actions/workflows/kali-wf.yml/badge.svg?branch=main)](https://github.com/githubfoam/cyberrange-kali-githubactions/actions/workflows/kali-wf.yml)

~~~~
      Name                    Command                 State                       Ports                  
---------------------------------------------------------------------------------------------------------
kali               /bin/bash                        Up                                                   
metasploitable     /bin/sh                          Up                                                   
owasp-juice-shop   docker-entrypoint.sh npm start   Up           0.0.0.0:3000->3000/tcp,:::3000->3000/tcp
parrotsec-core     /bin/sh -c bash $@               Up                                                   
postgresql         docker-entrypoint.sh postgres    Restarting                                           
webgoat            /bin/sh -c /bin/bash /home ...   Up           8080/tcp, 9090/tcp   
~~~~