# Text to Speech Converter 🎙️

## Description
A simple and intuitive Text to Speech Converter built using HTML, CSS, and JavaScript. This project allows users to input text and convert it into speech using the browser's built-in speech synthesis API.

## Features
- 🗣️ Convert text input to speech.
- 🎚️ Select from multiple available voices.
- 🔄 Real-time voice switching.

## Demo
Link - https://harjotrocks.com/javascript/text-to-speech/

## Technologies Used
- **📝 HTML**: Provides the structure for the user interface.
- **🎨 CSS**: Styles the layout for an appealing design.
- **🤖 JavaScript**: Implements speech synthesis and user interactions.

## How to Use
1. 📂 Clone the repository or download the files.
2. 🗃️ Open `index.html` in a web browser.
3. ✏️ Enter text in the text area.
4. 🎚️ Select a voice from the dropdown menu.
5. 🔊 Click the **Listen** button to hear the text.

## Code Explanation
### 📚 HTML
The HTML file defines the interface elements:
- **Title and Header:** Display the application name.
- **Text Area:** Allows the user to input text.
- **Dropdown Select:** Provides options to choose different voices.
- **Button:** Triggers the speech conversion.

### 🎨 CSS
- Styles the layout with a modern look.
- Aligns components and improves usability.

### 💻 JavaScript
#### Variables
- `speech`: An instance of `SpeechSynthesisUtterance` used for speech conversion.
- `voices`: An array to store available speech synthesis voices.
- `voiceSelect`: The `<select>` element for choosing a voice.

#### Functions
```javascript
window.speechSynthesis.onvoiceschanged = () => {
    voices = window.speechSynthesis.getVoices();
    speech.voice = voices[0];

    voices.forEach((voice, i) => (voiceSelect.options[i] = new Option(voice.name, i)));
};
```
- **`onvoiceschanged`:** Populates the dropdown with available voices.

```javascript
voiceSelect.addEventListener("change", () => {
    speech.voice = voices[voiceSelect.value];
});
```
- **Voice Selection Event:** Updates the selected voice.

```javascript
document.querySelector("button").addEventListener("click", () => {
    speech.text = document.querySelector("textarea").value;
    window.speechSynthesis.speak(speech);
});
```
- **Button Click Event:** Reads the input text aloud when the user clicks the button.


## Improvements
- 🌟 Add support for pitch and speed adjustments.
- 🎵 Implement background sound while reading text.
- 🔗 Provide a download option for audio.

