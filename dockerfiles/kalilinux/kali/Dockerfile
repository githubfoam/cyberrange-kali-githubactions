FROM kalilinux/kali-rolling
LABEL org.opencontainers.image.authors="githubfoam"


#clean start
RUN apt-get update -y && apt-get upgrade -y && apt-get autoremove - && apt-get clean 

# custom packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    aircrack-ng \
    ncat  \
    nmap  \
    hping3

#testing
RUN hping3 -v

