# cyberrange-kali-githubactions
[![kali cyberrange CI workflow](https://github.com/githubfoam/cyberrange-kali-githubactions/actions/workflows/kali-wf.yml/badge.svg?branch=main)](https://github.com/githubfoam/cyberrange-kali-githubactions/actions/workflows/kali-wf.yml)

~~~~
       Name                     Command                       State                            Ports                  
---------------------------------------------------------------------------------------------------------------------
kali                bash                             Up                                                              
kali-forensics      /bin/bash                        Up                                                              
metasploitable      /bin/sh                          Up                                                              
owasp-juice-shop    docker-entrypoint.sh npm start   Up                      0.0.0.0:3000->3000/tcp,:::3000->3000/tcp
parrotsec-core      /bin/sh -c bash $@               Up                                                              
postgresql          docker-entrypoint.sh postgres    Up                      0.0.0.0:5432->5432/tcp,:::5432->5432/tcp
webgoat             /bin/sh -c /bin/bash /home ...   Up                      8080/tcp, 9090/tcp                      
zap2docker-stable   bash                             Up (health: starting)                                           
zap2docker-weekly   bash                             Up (health: starting)                                                
~~~~
[![build all kali cyberrange CI workflow](https://github.com/githubfoam/cyberrange-kali-githubactions/actions/workflows/kali-buildall-wf.yml/badge.svg?branch=main)](https://github.com/githubfoam/cyberrange-kali-githubactions/actions/workflows/kali-buildall-wf.yml)  
~~~~
kali-forensics     /bin/bash                        Up                                              
kali-web           bash                             Up                                              
metasploitable     /bin/sh                          Up                                              
owasp-juice-shop   docker-entrypoint.sh npm start   Up      0.0.0.0:3000->3000/tcp,:::3000->3000/tcp
parrotsec-core     /bin/sh -c bash $@               Up                                              
postgresql         docker-entrypoint.sh postgres    Up      0.0.0.0:5432->5432/tcp,:::5432->5432/tcp
webgoat            /bin/sh -c /bin/bash /home ...   Up      8080/tcp, 9090/tcp   
~~~~
~~~~
git clone https://github.com/githubfoam/cyberrange-kali-githubactions.git && cd cyber*
sudo docker-compose --file dockerfiles/kalilinux/docker-compose-kali.yml up -d
sudo docker-compose --file dockerfiles/kalilinux/docker-compose-kali.yml ps
sudo docker exec --tty --interactive kali /bin/bash
~~~~