Before Optimization:
    Size:971MB
    Dockerfile:
    FROM ubuntu:latest
    RUN apt-get update && apt-get install -y postgresql postgresql-contrib
    RUN apt-get install -y default-jdk
    RUN apt-get install -y leiningen
    COPY . ./
    RUN chmod +x ./start.sh
    RUN lein ring uberjar
    CMD ["./start.sh"]
    EXPOSE 3000

After Optimization:
    Size:398MB
    Dockerfile:
    FROM alpine
    RUN apk update && \
        apk add --no-cache openjdk11 \
        postgresql \
        postgresql-contrib \
        wget

    # Install lein
    RUN wget -P /etc/apk/keys/ https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub
    RUN apk add --no-cache --repository=https://apkproxy.herokuapp.com/sgerrand/alpine-pkg-leiningen leiningen=2.9.1-r0
    RUN apk del wget
    RUN adduser -D leiningen

    COPY . ./
    RUN chmod +x ./start.sh
    RUN lein ring uberjar
    CMD ["./start.sh"]
    EXPOSE 3000
    USER leiningen
