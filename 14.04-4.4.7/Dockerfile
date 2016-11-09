FROM ubuntu:14.04

ENV HOST="0.0.0.0" \
	PORT="8100"

ENV SOCKET="socket,host=${HOST},port=${PORT};urp;StarOffice.ServiceManager" 

RUN sudo apt-get update &&\
    sudo apt-get install -y software-properties-common &&\
    sudo apt-add-repository ppa:libreoffice/libreoffice-4-4 &&\
    sudo apt-get update -y &&\
    sudo apt-get upgrade -y &&\
    sudo apt-get install -y libreoffice libreoffice-avmedia-backend-gstreamer libreoffice-base libreoffice-base-core libreoffice-base-drivers libreoffice-calc libreoffice-common libreoffice-core libreoffice-draw libreoffice-gnome libreoffice-gtk libreoffice-impress libreoffice-java-common libreoffice-math libreoffice-pdfimport libreoffice-report-builder-bin libreoffice-sdbc-firebird libreoffice-sdbc-hsqldb libreoffice-style-galaxy libreoffice-writer librsvg2-2 librsvg2-common &&\
    sudo apt-get clean &&\
    sudo rm -rf /var/lib/apt/lists/*
    
USER root
ENTRYPOINT ["soffice", "--nofirststartwizard", "--nologo", "--headless", "--accept='$SOCKET'"]