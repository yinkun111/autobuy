FROM daocloud.io/library/nginx:1.9.1
COPY loopsh jenkins.py /usr/local/
WORKDIR /usr/local
ENTRYPOINT ["sh","loopsh"]
CMD /bin/bash loopsh
