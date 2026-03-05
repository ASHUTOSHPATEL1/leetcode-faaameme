# 🎺 LeetCode FAAAAME

> Plays the sad trombone **FAAAAME** sound every time you get a Wrong Answer on LeetCode.

Because you deserve it.

---

## 📸 Demo

When you submit wrong code, this happens:

```
❌ Wrong Answer  →  🎺 FAAAAAAAME
```

A toast notification slides in from the right and the classic sad trombone blasts at full volume. No mercy.

---

## ⚡ Installation

### Option 1 — Download ZIP (easiest)
1. Go to [Releases](../../releases) and download the latest `leetcode-fame-extension.zip`
2. Unzip it
3. Open Chrome → go to `chrome://extensions/`
4. Toggle on **Developer Mode** (top right)
5. Click **Load unpacked** → select the unzipped folder
6. The 🎺 icon appears in your toolbar. You're cooked.

### Option 2 — Clone this repo
```bash
git clone https://github.com/YOUR_USERNAME/leetcode-faaaame.git
```
Then follow steps 3–6 above, pointing to the cloned folder.

---

## 🔔 Triggers sound on

| Error | |
|---|---|
| Wrong Answer | ❌ |
| Time Limit Exceeded | ⏱️ |
| Runtime Error | 💥 |
| Compile Error | 🔧 |
| Memory Limit Exceeded | 🧠 |
| Output Limit Exceeded | 📤 |

---

## 🛠️ How it works

- A **background service worker** re-injects the content script on every LeetCode navigation (LeetCode is a SPA, so the script would otherwise die on submit)
- A **MutationObserver** watches the DOM for result text nodes
- When a failure string is detected, it plays `faaah.mp3` using the Web Audio API
- A debounce guard prevents the sound from firing more than once per submission

---

## 📁 File structure

```
leetcode-faaaame/
├── manifest.json       # Chrome extension config (MV3)
├── background.js       # Service worker - re-injects on SPA navigation
├── content.js          # DOM watcher - detects failures and plays sound
├── faaah.mp3           # The sound 🎺
├── popup.html          # Extension popup UI
├── popup.js            # Test sound button
└── icon*.png           # Extension icons
```

---

## 🤝 Contributing

PRs welcome! Ideas:
- Firefox support
- Custom sound upload
- Failure streak counter
- Different sounds for different errors

---

## 📜 License

MIT — do whatever you want with it.

---

*Built for leetcode grinders who need humbling. May you hear this sound as few times as possible.* 🎺
