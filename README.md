# Lip Sync using SadTalker

## Overview

This project enables lip synchronization of a static image with an audio file using [SadTalker](https://github.com/OpenTalker/SadTalker). SadTalker is a deep-learning-based framework that generates realistic facial animations from speech audio.

## Features

- Converts text scripts into speech using ElevenLabs TTS.
- Generates lip-synced videos from an input image and audio file.

- Generates lip-synced videos from an input image and audio file.
- Supports head movements and facial expressions.
- Easy-to-use command-line interface.

## Installation

### Prerequisites

- Python 3.7+
- CUDA-enabled GPU (recommended for better performance)
- PyTorch installed with GPU support
- FFmpeg (for video processing)

### Setup

1. Clone the SadTalker repository:
   ```bash
   git clone https://github.com/OpenTalker/SadTalker.git
   cd SadTalker
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Download pre-trained models:
   ```bash
   bash scripts/download_models.sh
   ```

## Usage

### Text-to-Speech Conversion
Use ElevenLabs' TTS service to convert a text script into an audio file directly from their website:

1. Visit [ElevenLabs](https://elevenlabs.io/).
2. Sign in or create an account.
3. Navigate to the 'Text-to-Speech' section.
4. Enter your script and select the desired voice model.
5. Generate and download the audio file.

Once the audio file is downloaded, proceed with the lip-syncing process.


### Running Lip Sync
Use the following command to generate a lip-synced video:

### Running Lip Sync

Use the following command to generate a lip-synced video:

```bash
python inference.py --driven_audio /path/to/audio.wav \
                    --source_image /path/to/image.png \
                    --result_dir /path/to/output_directory
```

### Parameters

- `--driven_audio`: Path to the input speech audio file (WAV format recommended).
- `--source_image`: Path to the input static image.
- `--result_dir`: Directory where the generated video will be saved.

## Example

```bash
python inference.py --driven_audio examples/audio/sample.wav \
                    --source_image examples/source_image/sample.png \
                    --result_dir output
```

The generated video will be saved in the `output` directory.

## Troubleshooting

- **CUDA out of memory**: Reduce the batch size or use a lower-resolution image.
- **Audio not in sync**: Ensure the audio file is properly formatted and sampled at 16kHz.

## References

- SadTalker GitHub: [https://github.com/OpenTalker/SadTalker](https://github.com/OpenTalker/SadTalker)
- Official Paper: [SadTalker: Learning Realistic Facial Animations from Speech](https://arxiv.org/abs/2304.09133)

## License

This project follows the license terms specified in the SadTalker repository.


