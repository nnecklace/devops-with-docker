Commands:
docker build -t yle-dl .
docker run -v $(pwd)/downloads:/downloads yle-dl <filename>
