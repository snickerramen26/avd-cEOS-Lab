FROM alpine:latest

RUN apk update && \
    apk add libteam && \
    apk add open-lldp && \
    apk add sudo && \
    apk add tcpdump && \
    apk add scapy && \
    apk add iperf3 && \
    apk add iperf && \
    apk add py3-pip && \
    apk add git

RUN pip3 install tabulate --break-system-packages

RUN git clone https://github.com/UchihaItachiSama/scapy-cli.git /home/alpine/scapy-cli

RUN adduser -u 1000 -G wheel -D alpine && \
    echo "%wheel ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

COPY entrypoint.sh /home/alpine/
RUN chmod +x /home/alpine/entrypoint.sh

USER alpine 

ENTRYPOINT ["/home/alpine/entrypoint.sh"]

CMD []
