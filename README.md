# An Efficient and Adaptive Noise Cancellation Algorithm for a Closed Environment

## Overview

This project presents an advanced noise cancellation system designed specifically for closed environments. The system implements multiple noise reduction algorithms including Kalman Filter, Wiener Filter, Band-Pass Filter, and Adaptive Active Noise Cancelling (ANC). The algorithms have been optimized to efficiently reduce background noise while preserving the quality of the primary audio signal.

## Model Details

- **Algorithms Implemented**:
  - Kalman Filter
  - Wiener Filter
  - Band-Pass Filter
  - Adaptive Active Noise Cancelling (ANC)

- **Evaluation Results**:

| Filter Type          | SNR (dB) | PSNR (dB) | Dynamic Range (dB) |
|----------------------|----------|-----------|---------------------|
| **Kalman Filter**    | -30.48   | 12.60     | 1.11                |
| **Wiener Filter**    | 58.57    | 72.32     | 117.22              |
| **Band-Pass Filter** | -30.48   | 12.60     | 349.10              |
| **Adaptive ANC**     | 15.32    | 25.68     | 120.25              |

## Intended Use

This noise cancellation system is designed for applications requiring high-quality audio processing in controlled environments. Potential use cases include:
- Conference call background noise reduction
- Audio recording studio noise management
- Hearing aid devices
- Automotive audio systems
- Any closed-environment audio processing application where noise reduction is critical.

## Limitations

- **Environment Specificity**: Optimized for closed environments; performance may vary in open settings
- **ANC Dependency**: Requires a reference noise signal for optimal performance
- **Computational Resources**: Real-time processing may require significant computational power
- **Audio Format**: Primarily tested with common audio formats (MP3, WAV).

## Training Procedure

The algorithms were implemented and tested using the following setup:

- **Development Environment**: Python 3.11
- **Libraries**: NumPy, SciPy, Matplotlib, LibROSA, PyWavelets, PyDub
- **Sample Rate**: 48000 Hz
- **Channel Support**: Mono and Stereo
- **Testing Data**: Sample audio files with varying noise profiles.

### Algorithm Performance:
- **Kalman Filter**: Effective for signals with predictable noise patterns
- **Wiener Filter**: Superior performance in environments with known noise characteristics
- **Band-Pass Filter**: Ideal for scenarios requiring specific frequency preservation
- **Adaptive ANC**: Most effective in real-time noise cancellation applications.

## Framework and Libraries

- **Python Version**: 3.11
- **Key Libraries**:
  - NumPy: 1.26.4
  - SciPy: 1.14.1
  - Matplotlib: 3.10.0
  - LibROSA: 0.10.2.post1
  - PyWavelets: 1.8.0
  - PyDub: 0.25.1
  - SoundFile: 0.13.1

## Usage

To use the noise cancellation algorithms, follow these steps:

### Kalman Filter
```python
from your_project import apply_kalman_filter

audio_signal, sr = sf.read("input_audio.mp3")
denoised_signal = apply_kalman_filter(audio_signal)
sf.write("denoised_audio_kalman.mp3", denoised_signal, sr)
```

### Wiener Filter
```python
from your_project import apply_wiener_filter

audio_signal, sr = sf.read("input_audio.mp3")
denoised_signal = apply_wiener_filter(audio_signal)
sf.write("denoised_audio_wiener.mp3", denoised_signal, sr)
```

### Band-Pass Filter
```python
from your_project import apply_bandpass_filter

audio_signal, sr = sf.read("input_audio.mp3")
denoised_signal = apply_bandpass_filter(audio_signal, lowcut=300.0, highcut=3000.0, fs=sr)
sf.write("denoised_audio_bandpass.mp3", denoised_signal, sr)
```

### Adaptive ANC
```python
from your_project import adaptive_noise_cancelling

audio_signal, sr = sf.read("input_audio.mp3")
noise_signal = your_noise_reference_signal
anc_filtered_signal = adaptive_noise_cancelling(audio_signal, noise_signal)
sf.write("denoised_audio_anc.mp3", anc_filtered_signal, sr)
```

## Conclusion

This noise cancellation system provides multiple robust algorithms for efficient noise reduction in closed environments. Each algorithm offers unique advantages depending on the specific application requirements. The project demonstrates significant potential for integration into various audio processing applications where high-quality sound is essential.
