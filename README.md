# VoiceScribe

**VoiceScribe** is a Windows desktop app for speech-to-text transcription — fast, private, and fully offline.  
Capture speech from your **microphone** or directly from **system audio** (any app playing on your speakers), and the transcribed text is automatically typed wherever your cursor is: in any text editor, browser, chat, IDE, or document.

---

## Screenshots

![Dashboard](screenshots/dashboard.png)
![Models Settings](screenshots/models.png)

---

## Key Features

- **Offline by default** — speech recognition runs 100% locally, your voice never leaves your computer. No internet required for transcription.
- **Two audio sources** — capture from a **microphone** or from **system audio** (speakers/headphones). Transcribe a video, podcast, meeting, or any audio playing on your PC — no extra software needed.
- **Works in any app** — text is inserted directly at the cursor position in any active window (browser, Word, Slack, VS Code, etc.).
- **Global hotkey** — start/stop recording from any app with a keyboard shortcut. Fully customizable — set any combination you prefer. Default is `Win+Ctrl`.
- **Multiple languages** — Russian, English, Chinese, Korean, Japanese, Vietnamese, Thai, and many others via dedicated language models.
- **Transcription history** — all your transcriptions are saved and searchable.
- **AI text post-processing** *(optional, requires internet)* — LLM-powered cleanup after each transcription: removes filler words (*"um"*, *"uh"*), fixes sentence boundaries, groups sentences into paragraphs, formats lists and enumerations.
- **Output language / translation** *(optional, requires internet)* — automatically translate the result into a different language. Transcribe in Russian, get output in English — or any other combination.
- **Flexible text insertion modes** — insert at cursor, append to end of field, or replace selected text.
- **Pause detection** — silence automatically starts a new paragraph, so your transcribed text is structured.
- **System tray** support — runs quietly in the background.

---

## Audio Sources

VoiceScribe supports two mutually exclusive input modes, switchable in **Settings → Audio**:

### Microphone
Standard input from any microphone connected to your system. Best for dictation and voice commands.

### System Audio (Loopback)
Captures whatever is currently playing through your speakers or headphones — a video, a podcast, a call, a browser tab. Uses native Windows WASAPI loopback, so no virtual audio cable or third-party software is required.

> **Tip for System Audio:** Use a language-specific Zipformer model for best results. Whisper multilingual models work too but require more RAM and take longer to process.

---

## System Requirements

- Windows 10 / 11 (64-bit)
- 4 GB RAM minimum (8 GB recommended for Whisper large models)
- ~300–600 MB disk space for the app + model

---

## Installation

1. Download the latest installer from the [Releases](../../releases) page.
2. Run `VoiceScribe_Setup.exe` — no admin rights required, no internet needed during install.
3. Launch **VoiceScribe**.

---

## First-Time Setup: Downloading a Model

VoiceScribe requires a speech recognition model before you can start transcribing.  
Models are downloaded once and stored locally. The **Settings → Models** page is split into two sections:

- **Active Model** — shows which model is currently loaded and lets you switch between installed models instantly.
- **Download Models** — browse and download new models by language.

---

### Step 1 — Open Settings → Models → Download Models

Click **Settings** in the left sidebar, then select **Models**.  
Scroll to the **Download Models** section.

### Step 2 — Choose your language and model type

From the **Language** dropdown, choose the language of the audio you'll be transcribing.  
Then pick a model from the **Select Model** dropdown.

#### Which model type should I choose?

There are two families of models:

| Model type | Languages | Speed | Accuracy | RAM |
|---|---|---|---|---|
| **Zipformer** | One language only | ⚡ Very fast | ✅ Excellent for that language | Low |
| **Whisper** | 99 languages (Multilingual) | Slower | Good across languages | Higher |

> **Recommendation:** If you primarily work with one language, always choose a **Zipformer** model for that language (e.g. *Russian*, *English*, *Chinese*, *Korean*).  
> Zipformer models are faster, have lower latency, and are **significantly more accurate** than Whisper for the language they were trained on.  
> Use **Whisper** only if you need to switch between languages frequently or transcribe mixed-language audio.

#### Model size

| Size | Quality | Use case |
|---|---|---|
| ~60–100 MB | Decent | Fast machines, quick testing, low RAM |
| **200–300 MB** | **Best** | **Recommended for everyday use** |

> Larger models handle accents better and make fewer mistakes on uncommon words. The extra download size is worth it for daily use.

### Step 3 — Download

Click **Download** and wait for the progress bar to complete.  
The model will appear in the **Active Model** section once installed.

---

### Step 4 — Select the Active Model

Once a model is downloaded, go to the **Active Model** section at the top of the Models page.

1. Use the **Language** filter to narrow the list to your language.
2. Pick the model from the **Model** dropdown — it loads automatically, no restart needed.

> You can download multiple models and switch between them at any time from this section.

---

### Step 5 (Whisper only) — Set Speech Language

If you are using a **Whisper Multilingual** model, you will see a **Speech Language** dropdown in the Active Model section.

**⚠️ Always set this to the language you are speaking — do not leave it on Auto if you know your language.**

| Setting | When to use |
|---|---|
| **Auto** | Mixed-language audio, or you don't know the language in advance |
| **Your language** (e.g. Russian, Greek, Filipino) | Any time you know what language you'll be speaking |

Setting the language explicitly makes Whisper:
- **Faster** — it skips language detection on every segment
- **More accurate** — it stops guessing and focuses on the right vocabulary
- **Less likely to hallucinate** — Auto mode sometimes produces random text during silence or noise

> **This setting is for the language you _speak_, not the language you want output in.**  
> If you want to translate speech to another language, use **AI Output Language** in **Settings → AI Text Processing**.

---

## Tips

- **Hotkey** — you don't need to keep VoiceScribe in focus. Press your configured hotkey in any window to toggle recording. Default is `Win+Ctrl`, change it in **Settings → Hotkeys**.
- **System Audio** — to transcribe a video or podcast, switch to *System Audio* in **Settings → Audio**, play the media, and press the hotkey. No virtual cable needed.
- **Pause = new paragraph** — natural pauses in speech are detected and converted into paragraph breaks automatically.
- **AI cleanup** — enable **AI Text Processing** in Settings for automatic punctuation and grammar corrections after each transcription.
- **Switching models** — you can install several models and switch the active one in **Settings → Models → Active Model** without restarting the app.
- **Whisper + specific language** — if you use Whisper and notice it occasionally switching to English or producing garbled text, set the Speech Language explicitly instead of using Auto.

---

## Feedback & Support

Have a question, found a bug, or want to suggest a feature?  
Send an email to **noreply.voicescribe@gmail.com** — or use the **Send Feedback** button in **Settings → About**.

---

## License

VoiceScribe is commercial software. A license is required after the trial period.  
Manage your license in **Settings → License**.
