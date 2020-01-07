Commands:
docker build -t node-backend .
docker run -p 8000:8000 -v $(pwd)/logs.txt:/logs.txt node-backend
