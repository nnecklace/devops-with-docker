Commands:
1. docker run -d --name test ubuntu:16.04 sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
2. docker exec -it test bash
3. apt-get update
4. apt-get install curl
5. docker stop test
6. docker -i test
7. helsinki.fi
