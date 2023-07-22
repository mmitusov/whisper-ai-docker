docker build -t whisper-ai-docker .
docker run -d -p 3005:5000 whisper-ai-docker 

docker container prune
docker image ls 
docker rmi 9323fccd61cb 

GET http://localhost:3005 - test
POST http://localhost:3005/whisper - transcribe audio
form-data {file: <audio_file>}

https://github.com/mmitusov/whisper-ai-docker.git