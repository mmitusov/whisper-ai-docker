# Building and runing container
`cd` to the project root directory and run:
```
docker build -t whisper-ai-docker .
docker run -d -p 3005:5000 whisper-ai-docker 
```

If you want to clean project manually:
```
docker container prune
docker image ls 
docker rmi <image_id> 
```

**Change wisper-ai model**
Inside app.py you can specify which model you want to run.
Example: `model = whisper.load_model("small", device=DEVICE)`.
You can choose from: 'tiny', 'base', 'small', 'medium', 'large' and 'large-v2'.

**Troubleshoot**
When running container, internal docker port should always be `5000`, otherwise you wouldn't be able to reach an app API.

# API description
Testing if app is working: GET request to the `/` path. Should get "Whisper Hello World!" in response.

Sending request to transcribe audio: POST request to the `/whisper` path. Body of the request should include form-data with audio file. Example `file: <audio_file>`.

# P.S.
This app was build for my 'ai japanese translator' project: https://github.com/mmitusov/ai-japanese-translator.