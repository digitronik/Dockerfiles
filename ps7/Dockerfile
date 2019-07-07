# docker run -it \
#   -v /tmp/.X11-unix:/tmp/.X11-unix \
#   -v $HOME:/workspace \
#   -e DISPLAY=$DISPLAY \
#   ps7

FROM digitronik/wine

MAINTAINER Nikhil Dhandre <nik.digitronik@live.com>

ADD ps7.zip /opt/

RUN apt-get update && \
    apt-get install -yqq unzip --no-install-recommends && \
    unzip /opt/ps7.zip -d /opt/ && \
    rm -rf /opt/ps7.zip && \
    /usr/bin/winetricks corefonts --unattended

# PS need GUI to install vcrun6 so install fallowing and commit
# docker exec -it <cont> /bin/bash
# echo "/usr/bin/winetricks vcrun6,
# docker commit <cont> <new_image:tag>

ENTRYPOINT ["wine", "/opt/ps7.exe"]
