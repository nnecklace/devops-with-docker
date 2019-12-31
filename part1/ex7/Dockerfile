FROM ubuntu:16.04
RUN apt-get update && apt-get install -y curl
COPY start.sh .
RUN chmod +x ./start.sh
CMD ["./start.sh"]
