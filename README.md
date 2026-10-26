# Awesome Local Voice AI [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

Open-source building blocks for voice AI that runs on your own hardware: speech recognition, text to speech, voice
activity detection, full voice-agent frameworks, and speech-native models that listen and talk in one.

Every entry is open source and checked by hand. Each section starts with where to begin.

## Contents

- [Which tool do I need?](#which-tool-do-i-need)
- [Speech to text](#speech-to-text)
  - [Real-time transcription](#real-time-transcription)
- [Text to speech](#text-to-speech)
- [Voice activity, wake words and speakers](#voice-activity-wake-words-and-speakers)
- [Voice agent frameworks](#voice-agent-frameworks)
- [Speech-native models](#speech-native-models)
- [Toolkits](#toolkits)
- [Benchmarks](#benchmarks)
- [Getting latency down](#getting-latency-down)
- [Contributing](#contributing)

## Which tool do I need?

| You want to | Start with |
|---|---|
| Transcribe audio files accurately on a GPU | [faster-whisper](#speech-to-text) with `large-v3-turbo` |
| Transcribe on a CPU, a laptop or a phone | [whisper.cpp](#speech-to-text) or [sherpa-onnx](#speech-to-text) |
| Word-level timestamps and who said what | [WhisperX](#speech-to-text) and [pyannote.audio](#voice-activity-wake-words-and-speakers) |
| Natural speech from a small, fast model | [Kokoro](#text-to-speech) |
| Clone a voice from a short sample | [Chatterbox](#text-to-speech), [F5-TTS](#text-to-speech) or [Fish Speech](#text-to-speech) |
| Build a voice agent that handles turn-taking and interruptions | [Pipecat](#voice-agent-frameworks) or [LiveKit Agents](#voice-agent-frameworks) |
| A fully local speech-to-speech pipeline to start from | [Hugging Face speech-to-speech](#voice-agent-frameworks) |

## Speech to text

- [faster-whisper](https://github.com/SYSTRAN/faster-whisper) - Whisper on CTranslate2: up to several times faster than the original with lower memory, on GPU or CPU. Good default.
- [whisper.cpp](https://github.com/ggml-org/whisper.cpp) - Whisper in C/C++ with no Python, running on CPUs, Apple Silicon, mobile and GPUs.
- [WhisperX](https://github.com/m-bain/whisperX) - Batched Whisper with accurate word-level timestamps and speaker diarization.
- [Whisper](https://github.com/openai/whisper) - OpenAI's original multilingual speech recognition models and reference code.
- [NVIDIA NeMo Speech](https://github.com/NVIDIA-NeMo/Speech) - NVIDIA's speech toolkit, home of the Parakeet and Canary models that lead many accuracy and speed benchmarks.
- [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) - Offline speech recognition, TTS, diarization and VAD on ONNX Runtime for desktop, mobile and embedded devices.
- [FunASR](https://github.com/modelscope/FunASR) - Speech recognition toolkit with streaming models, VAD and punctuation, strong for Chinese.
- [Vosk](https://github.com/alphacep/vosk-api) - Lightweight offline recognition for Android, iOS, Raspberry Pi and servers, in 20+ languages.
- [Kyutai STT](https://github.com/kyutai-labs/delayed-streams-modeling) - Kyutai's streaming speech-to-text (and text-to-speech) models built for low latency.

### Real-time transcription

- [RealtimeSTT](https://github.com/KoljaB/RealtimeSTT) - Microphone to text with VAD, wake words and low latency, built on faster-whisper.
- [WhisperLive](https://github.com/collabora/WhisperLive) - Near-live transcription server and clients over WebSocket.
- [HEX](https://github.com/anomalyco/hex) - Local dictation app in Rust: hold a shortcut, speak, and the text is pasted into any app. On-device models, macOS first.
- [WhisperLiveKit](https://github.com/QuentinFuxa/WhisperLiveKit) - Real-time local speech to text built on streaming research (SimulStreaming, WhisperStreaming), with speaker diarization and an OpenAI-compatible API.

## Text to speech

- [Kokoro](https://github.com/hexgrad/kokoro) - 82M-parameter model with natural speech, small enough to run beside an LLM on one GPU or on a CPU. Good default.
- [MOSS-TTS-Nano](https://github.com/OpenMOSS/MOSS-TTS-Nano) - 100M-parameter multilingual TTS with voice cloning that runs in real time on a CPU, with an ONNX build.
- [Chatterbox](https://github.com/resemble-ai/chatterbox) - Expressive TTS with zero-shot voice cloning and emotion control.
- [F5-TTS](https://github.com/SWivid/F5-TTS) - Flow-matching TTS with strong zero-shot voice cloning.
- [Fish Speech](https://github.com/fishaudio/fish-speech) - Multilingual TTS and voice cloning with high quality from short references.
- [CosyVoice](https://github.com/QwenAudio/CosyVoice) - Multilingual TTS with streaming output and voice cloning.
- [Piper](https://github.com/OHF-Voice/piper1-gpl) - Fast, lightweight TTS that runs well on a Raspberry Pi, used by Home Assistant.
- [Coqui TTS](https://github.com/idiap/coqui-ai-TTS) - Maintained fork of the Coqui toolkit with many models, including XTTS voice cloning.
- [GPT-SoVITS](https://github.com/RVC-Boss/GPT-SoVITS) - Few-shot voice cloning: train a usable voice from about a minute of audio, with a web UI.
- [Dia](https://github.com/nari-labs/dia) - Generates multi-speaker dialogue, including laughs and pauses, in one pass.
- [VibeVoice](https://github.com/microsoft/VibeVoice) - Microsoft's open voice models: long-form multi-speaker TTS (up to 90 minutes, 4 speakers), a 0.5B real-time TTS and a multilingual ASR model.
- [Orpheus TTS](https://github.com/canopyai/Orpheus-TTS) - LLM-based TTS with human-like intonation and emotion tags.
- [CSM](https://github.com/SesameAILabs/csm) - Sesame's conversational speech model, which uses conversation context to sound natural.
- [ChatTTS](https://github.com/2noise/ChatTTS) - Speech model tuned for conversational dialogue (AGPL).
- [OpenVoice](https://github.com/myshell-ai/OpenVoice) - Instant voice cloning with control over tone, emotion and accent.
- [OmniVoice](https://github.com/k2-fsa/OmniVoice) - Zero-shot voice cloning TTS from the k2-fsa (next-gen Kaldi) team, covering more than 600 languages.
- [RealtimeTTS](https://github.com/KoljaB/RealtimeTTS) - Streams text to speech as it is generated, with many engines behind one API.

## Voice activity, wake words and speakers

- [Silero VAD](https://github.com/snakers4/silero-vad) - Small, accurate voice activity detector that runs in real time on a CPU. Good default.
- [openWakeWord](https://github.com/dscripka/openWakeWord) - Open wake word detection with pre-trained models and training for custom words.
- [pyannote.audio](https://github.com/pyannote/pyannote-audio) - Speaker diarization: who spoke when, plus speech activity and overlap detection.

## Voice agent frameworks

Turn-taking, interruptions, streaming and transport are the hard parts. These handle them.

- [Pipecat](https://github.com/pipecat-ai/pipecat) - Python framework for real-time voice and multimodal agents, with many STT, LLM and TTS integrations. Good default.
- [LiveKit Agents](https://github.com/livekit/agents) - Framework for real-time voice agents over WebRTC, with turn detection and telephony.
- [TEN Framework](https://github.com/TEN-framework/ten-framework) - Framework for conversational voice agents with real-time, multimodal pipelines.
- [speech-to-speech](https://github.com/huggingface/speech-to-speech) - Hugging Face's modular open pipeline: VAD, STT, LLM and TTS, each swappable.
- [Qwen Audio Agent](https://github.com/QwenAudio/qwen-audio-agent) - Qwen's real-time voice runtime that keeps talking while the agent calls tools or works on a task.

## Speech-native models

Models that take speech in, and sometimes give speech out, without a separate transcription step.

- [Moshi](https://github.com/kyutai-labs/moshi) - Full-duplex speech-text model that listens and speaks at the same time.
- [Ultravox](https://github.com/fixie-ai/ultravox) - Multimodal LLM that understands speech directly, built for real-time voice agents.
- [Qwen2.5-Omni](https://github.com/QwenLM/Qwen2.5-Omni) - End-to-end model that understands text, images, audio and video and answers in text and speech.

## Toolkits

- [SpeechBrain](https://github.com/speechbrain/speechbrain) - PyTorch toolkit covering recognition, enhancement, separation, speaker recognition and more.
- [ESPnet](https://github.com/espnet/espnet) - End-to-end speech processing toolkit for research: ASR, TTS, translation and speech enhancement.
- [CrispASR](https://github.com/CrispStrobe/CrispASR) - One C++ binary (a whisper.cpp fork) that runs Whisper, Parakeet, Canary, Voxtral and many TTS models from GGUF files, with no Python.

## Benchmarks

- [Open ASR Leaderboard](https://github.com/huggingface/open_asr_leaderboard) - Word error rate and speed of open speech recognition models on common test sets.

## Getting latency down

What makes a local voice assistant feel fast, whatever tools you pick:

- **Stream every stage.** Speak each sentence as soon as the LLM finishes it instead of waiting for the full reply.
- **Use VAD for end-of-turn detection** and keep the silence threshold short; it is often the biggest single delay.
- **Keep models resident.** Load STT, LLM and TTS once at startup; cold starts dominate first-response time.
- **Ask for short spoken answers.** A system prompt that asks for one or two sentences cuts time to first audio.
- **Measure time to first audio,** not total time. It is what the user hears.

## Contributing

Suggestions are welcome. A project fits if it is open source, runs locally, and is maintained or widely used. Open a
pull request with one line in the matching section: name, link, and what it does in plain words. Links are checked
every week.

## License

[CC0 1.0](LICENSE). To the extent possible under law, the authors have waived all copyright and related rights.
