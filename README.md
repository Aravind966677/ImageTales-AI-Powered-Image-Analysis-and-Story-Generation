# Image Analysis and Story Generation

This Python application combines Azure's Computer Vision, OpenAI, and Speech Services to analyze images, generate creative stories based on the analysis, and convert those stories into speech. The application demonstrates the integration of multiple Azure AI services to create a comprehensive media processing pipeline.

## Features

- Image Analysis: Uses Azure Computer Vision to extract descriptions and text from images
- Story Generation: Leverages Azure OpenAI (GPT-4) to create creative stories based on image analysis
- Text-to-Speech: Converts generated stories into natural-sounding speech using Azure Speech Services
- Automated Output Management: Organizes speech output files with timestamps

## Prerequisites

- Python 3.x
- Azure subscription with the following services:
  - Azure Computer Vision
  - Azure OpenAI
  - Azure Speech Services

## Required Libraries

```bash
pip install azure-cognitiveservices-vision-computervision
pip install openai
pip install azure-cognitiveservices-speech
pip install httpx
```

## Configuration

The application requires the following Azure service credentials:

### Azure Vision API
- `VISION_ENDPOINT`: Your Azure Computer Vision endpoint URL
- `VISION_KEY`: Your Azure Computer Vision API key

### Azure OpenAI API
- `OPENAI_API_KEY`: Your Azure OpenAI API key
- `OPENAI_ENDPOINT`: Your Azure OpenAI endpoint URL
- `DEPLOYMENT_NAME`: Your GPT-4 model deployment name

### Azure Speech Service
- `SPEECH_KEY`: Your Azure Speech Service API key
- `SPEECH_REGION`: Your Azure Speech Service region

## Key Components

### 1. Vision Client (`initialize_vision_client()`)
- Initializes the Azure Computer Vision client
- Handles authentication using provided credentials
- Returns configured client instance for image analysis

### 2. OpenAI Client (`initialize_openai_client()`)
- Sets up Azure OpenAI client with custom HTTP client
- Configures API version and authentication
- Enables interaction with GPT-4 model

### 3. Image Analysis (`analyze_image()`)
- Processes images to extract:
  - Main image caption
  - Text content found in the image
- Returns combined analysis results

### 4. Story Generation (`generate_story()`)
- Uses GPT-4 to create engaging stories based on image analysis
- Implements creative storytelling prompt
- Generates 3-4 paragraph narratives

### 5. Text-to-Speech (`text_to_speech_file()`)
- Converts generated stories to speech
- Uses Jenny Neural voice for natural-sounding output
- Saves audio files with timestamps
- Provides status updates and error handling

## Usage

1. Run the script:
```bash
python main.py
```

2. When prompted, enter the path to your image file:
```
Enter the path to your image (or 'quit' to exit): path/to/your/image.jpg
```

3. The application will:
   - Analyze the image
   - Display analysis results
   - Generate a story
   - Convert the story to speech
   - Save the audio file

4. Output files are saved in the `speech_output` directory with timestamps.

## Error Handling

The application includes comprehensive error handling for:
- Client initialization failures
- Image processing errors
- Story generation issues
- Speech synthesis problems
- File I/O operations

## Output

- Image analysis results are displayed in the console
- Generated stories are shown in text form
- Audio files are saved as WAV files with timestamps
- File sizes are reported for generated audio

## Limitations

- Requires active Azure subscriptions
- Image file must be accessible locally
- Internet connection required for all API operations
- Audio output is limited to WAV format

## Contributing

Feel free to submit issues and enhancement requests!

## License

[Add your chosen license here]
