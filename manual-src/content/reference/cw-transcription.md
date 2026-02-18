---
title: "CW Transcription"
description: "Morse code decoding and auto-fill"
weight: 11
showToc: true
---

CW Transcription decodes Morse code audio from your radio, helping you copy callsigns and exchange information.

## Enabling Transcription

1. Open the **Logger** tab
2. Tap the **CW** button
3. Grant microphone permission when prompted

The transcription panel appears below the logger.

## How It Works

1. **Audio capture** - Microphone picks up your radio's audio
2. **Tone detection** - Goertzel algorithm identifies CW tones
3. **Frequency tracking** - Automatically locks onto the dominant tone
4. **Decoding** - Morse patterns converted to text
5. **Display** - Decoded text shown in real-time

## Transcription Display

### Live Transcript

Characters appear as they're decoded. The display shows:

- Decoded text
- Current character in progress
- Timing indicators

### Conversation View

For extended QSOs, the chat-style view shows:
- Separated transmissions
- Timestamps
- Your transmission vs. theirs (if identifiable)

## Frequency Tracking

### Automatic

The decoder automatically finds and tracks the CW tone:
- Detects dominant tone frequency
- Adjusts as tuning drifts
- Works across typical CW pitch ranges (400-900 Hz)

### Manual

If automatic tracking struggles:
1. Tap the frequency indicator
2. Adjust manually
3. Tap to lock

## WPM Estimation

The decoder estimates sending speed (words per minute):
- Displayed in the panel
- Adapts to the sender's speed
- Helps gauge copying difficulty

## Callsign Detection

The decoder identifies likely callsigns:
- Highlighted in the transcript
- Tap to auto-fill the Logger callsign field
- Common patterns recognized (W/K/N prefix, etc.)

## Auto-Fill Integration

When a callsign is detected:

1. Callsign appears highlighted
2. Tap to fill the Logger
3. QRZ lookup triggers automatically
4. Continue copying the QSO

## Tips for Best Results

### Audio Setup

- Hold phone near speaker, or use audio cable
- Reduce background noise
- Moderate volume (not too loud, not too quiet)

### Tuning

- Center the signal in your passband
- Use narrow filter if available
- Reduce QRM by tuning away from interference

### Limitations

CW transcription works best with:
- Clean, well-spaced sending
- Single signal (no QRM)
- Standard timing

Challenging for:
- Very fast sending (35+ WPM)
- Poor sending (irregular timing)
- Heavy QRM/QRN
- Multiple overlapping signals

## Accuracy

Machine CW decoding isn't perfect. Use transcription as an aid, not a replacement for developing your own ear. When in doubt:
- Ask for repeats
- Verify callsigns via QRZ lookup
- Use your own ears for critical info

## Audio Processing

### Goertzel Algorithm

The decoder uses the Goertzel algorithm for efficient tone detection:
- Computes signal strength at specific frequencies
- More efficient than FFT for single-frequency detection
- Runs in real-time on device

### Adaptive Thresholds

Background noise is analyzed to set:
- Tone detection threshold
- Noise gate level
- Helps distinguish signal from noise

## See Also

- [Logger](/reference/logger/) - Log decoded contacts
- [Settings](/reference/settings/) - Audio preferences
