# 🎙️ Chatterbox Voice Clone

Clone your own voice with [Resemble AI's Chatterbox](https://github.com/resemble-ai/chatterbox) on free Google Colab GPUs, and turn video scripts into narration in your voice.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/CosmosGuide/chatterbox-voice-clone/blob/main/Chatterbox_Voice_Clone.ipynb)

## What it does

- **Zero-shot voice cloning**: a single 10–30 second recording of you is enough. No training needed.
- **3 models to choose from**:
  - **Multilingual**: Hindi, English and 21 more languages (default)
  - **English (original)**: the best-quality English model
  - **Turbo**: fastest, English only
- **Long scripts**: scripts are split into sentences automatically (including Hindi `।`), generated chunk by chunk and joined with natural pauses.
- **Saved to Google Drive**: your voice sample and every narration (WAV + MP3) go to `MyDrive/VoiceClone/`.
- **Batch mode**: put `.txt` scripts in `MyDrive/VoiceClone/scripts/` and generate them all in one run.

## Quick start

1. Click **Open in Colab** above.
2. `Runtime → Change runtime type → T4 GPU`.
3. **Step 1**: installs Chatterbox. The runtime restarts once, which is expected.
4. **Step 2**: connect Google Drive.
5. **Step 3**: upload a 10–30s recording of your voice. You only do this once.
6. **Step 4**: load a model. Then run **Helper functions**.
7. **Step 5**: paste your script and generate. The MP3 downloads automatically and is also saved in Drive.

On later runs, do Steps 1, 2, 4, Helpers and 5. Your voice sample stays in Drive.

## Drive layout

```
MyDrive/VoiceClone/
├── reference/my_voice.wav   ← your cleaned voice sample
├── scripts/                 ← .txt files for batch mode (moved to scripts/done/ after use)
└── outputs/                 ← generated .wav + .mp3 narrations
```

## Recording a good reference sample

- Quiet room, no background music, no echo, only your voice.
- Speak naturally, in the same tone you use in your videos.
- 15–25 seconds is the sweet spot. Turbo needs at least 5 seconds.
- For Hindi narration, record the sample in Hindi.

## Tuning

| Setting | Default | Effect |
|---|---|---|
| `EXAGGERATION` | 0.5 | Higher means more expressive or dramatic |
| `CFG_WEIGHT` | 0.5 | Lower means slower, more deliberate pacing (try 0.3 with high exaggeration) |
| `TEMPERATURE` | 0.8 | Higher means more variation between takes |
| `SEED` | 42 | Keep it fixed for a consistent delivery. Change it to re-roll a bad take |

Turbo ignores exaggeration and CFG.

## Notes

- Chatterbox is MIT-licensed. Every output carries Resemble AI's inaudible Perth watermark.
- Only clone voices you own or have explicit permission to use.
