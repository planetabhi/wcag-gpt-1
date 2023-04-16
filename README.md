# WCAG GPT 1
Training a GPT model on WCAG success criteria. (Note: As of now, the training data used here is a workaround that was quickly generated using ChatGPT.)

### Install
```npm install``` <br>
```pip install --upgrade openai openai"[datalib]"```

### Create .env
```OPENAI_KEY="<YOUR_SECRET_API_KEY>"```

### Prepare data
```openai tools fine_tunes.prepare_data -f ./data/YOUR_DATA_FILE.jsonl```

### Update uploadFile.js
```fs.createReadStream('./data/YOUR_PREPARED_DATA_FILE.jsonl'),```

### Upload the training data and generate file ID
```node uploadFile.js```

### Update createFineTune.js
```training_file: 'YOUR_FILE_ID'```

### Tune model
```node createFineTune.js```

### Check status
```node listFineTunes.js```

### Try your model
```node createCompletion.js```

