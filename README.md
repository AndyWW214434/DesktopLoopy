# 🖼️ Desktop Loopy — macOS Floating Pet

**Desktop Loopy** is a lightweight macOS application that displays a floating, interactive Loopy character in a transparent window. The pet can be clicked to cycle through different states like active, alternate pose, and sleeping. It also greets you based on the time of day when it launches.

---

## 🚀 Features

- 🪟 Borderless, floating window with transparent background  
- 👋 Time-based greeting popup at launch  
- 🖱️ Single-click interaction cycles through Loopy's images:
  - `LoopyGIF.png` (default)
  - `Loop2.png` (alternate)
  - `SleepyLoopy1.png` (sleeping mode)
- 📦 Loads image assets from the application bundle
- 🧼 Clean and minimal UI with rounded corners and shadow
- 🧠 Prepared for draggable behavior (extension included)

---

## 🧱 Architecture

### `AppDelegate.swift`

- Initializes the application window and sets it to floating, borderless, and always on top.
- Configures an `NSImageView` to display Loopy's current image.
- Adds a `NSClickGestureRecognizer` to enable state-switching through single-click.
- Shows a greeting message (`Good morning!`, `Good afternoon!`, or `Good night!`) based on the current system time.
- Manages state through a `clickState` variable that rotates between 0 → 1 → 2 → 0.

### Image State Logic

| State      | Image Name       | Description        |
|------------|------------------|--------------------|
| 0 (default)| `LoopyGIF.png`   | Default Loopy pose |
| 1          | `Loop2.png`      | Alternate image    |
| 2          | `SleepyLoopy1.png` | Sleeping pose     |

---

## 📂 Assets

Ensure the following `.png` files are present in the app bundle:

- `LoopyGIF.png`
- `Loop2.png`
- `SleepyLoopy1.png`

These are loaded using `Bundle.main.url(forResource:withExtension:)`.

---

## 🧪 How to Run

1. Open the project in Xcode.
2. Make sure the PNG assets are added to the bundle.
3. Build and run the app (`⌘R`).
4. You should see the floating Loopy character on your screen.
5. Click Loopy to cycle through the different states.

---

## 🧩 Extensibility Ideas

- Add drag-to-move support using the `initialLocation` extension on `NSWindow`.
- Support animated GIFs or video loops.
- Add sound or speech bubbles on events.
- Store and restore last state using `UserDefaults`.

---

## 🛠️ Tech Stack

- Language: Swift
- Framework: Cocoa (AppKit)
- Target: macOS

---

## 📜 License

MIT License or Proprietary (choose one based on your intent).

---

## 👤 Author

**Andy Wang**  
Feel free to reach out for questions or improvements!
