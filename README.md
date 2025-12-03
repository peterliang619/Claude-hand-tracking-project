# Unspoken - ASL Alphabet Learning App

An interactive web application for learning American Sign Language (ASL) alphabet using real-time hand gesture recognition.

## Features

- **Real-time ASL Recognition**: Uses a pre-trained CLIP-based model with 99.88% accuracy
- **Interactive Learning Levels**: Progressive difficulty levels for learning
- **Hand Tracking Visualization**: Visual feedback with hand skeleton overlay
- **No Installation Required**: Runs entirely in your browser
- **GitHub Pages Compatible**: Host it as a static website

## How It Works

This app uses the [CLIP-ASL Fingerspelling model](https://huggingface.co/aalof/clipvision-asl-fingerspelling) hosted on HuggingFace's Inference API. Your webcam captures frames which are sent to the API for classification, returning the predicted ASL letter with confidence scores.

## Setup

### Basic Setup (Free Tier)

1. Clone this repository
2. Open `index.html` in your browser
3. Allow webcam access when prompted
4. Start learning!

**Note**: Free tier has rate limits and the model may take 10-20 seconds to load on first use.

### Recommended Setup (Higher Rate Limits)

For better performance and fewer rate limits:

1. Create a free HuggingFace account at https://huggingface.co/join
2. Generate an API token at https://huggingface.co/settings/tokens (use "Read" access)
3. Open `asl-recognition.html` in a text editor
4. Find line 364 and add your token:
   ```javascript
   const HF_API_TOKEN = 'hf_your_token_here';
   ```
5. Save and reload the page

## Hosting on GitHub Pages

1. Push this repository to GitHub
2. Go to Settings → Pages
3. Select your branch and root directory
4. Your site will be live at `https://yourusername.github.io/your-repo-name/`

## Technical Details

- **Model**: CLIP Vision fine-tuned for ASL fingerspelling (aalof/clipvision-asl-fingerspelling)
- **Accuracy**: 99.88% on test set
- **Frontend**: Vanilla JavaScript with p5.js
- **Hand Tracking**: ml5.js Handpose model
- **API**: HuggingFace Inference API (no backend needed)

## Browser Requirements

- Modern browser (Chrome, Firefox, Safari, Edge)
- Webcam access
- Internet connection (for API calls)

## Troubleshooting

### "Model Loading" message persists
- The model needs to "wake up" on first request (10-20 seconds)
- Refresh the page and try again

### "Rate Limited" message
- Free tier has request limits
- Add a HuggingFace API token (see Recommended Setup above)
- Reduce classification frequency (edit `CLASSIFICATION_INTERVAL` in code)

### Low accuracy
- Ensure good lighting
- Position your hand clearly in frame
- Try different backgrounds
- The model was trained on specific hand angles - match ASL reference images

## Credits

- ASL Model: [aleksandra-baranowska/clip-asl-fingerspelling](https://github.com/aleksandra-baranowska/clip-asl-fingerspelling)
- Hand Tracking: ml5.js Handpose
- Original concept: Interactive ASL learning platform

## License

MIT License - Feel free to use and modify!
