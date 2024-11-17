# NitroProject
www.nitroproject
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Text-to-Speech in English</title>
  <style>
    /* Նիտրո պրոյեկտի դիզայն */
    h2 {
      text-align: center;
      color: #4CAF50; /* Քոլոր կամ ցանկացած գույն */
      font-family: 'Arial', sans-serif;
      font-size: 2em;
      background-color: #000000; /* Բնակարան համար */
      padding: 10px;
      border-radius: 8px;
    }
  </style>
</head>
<body>
  <!-- NitroProject անվանումը վերևում -->
  <h2>NitroProject</h2>

  <h1>Բարև սա այնպիսի կայք է որտեղ դու կարողես տեղադրել քո անգլերեն տեքստը և ես կկարդամ այն քեզ համար</h1>
  <textarea id="text-input" rows="6" cols="40" placeholder="Տեղադրիր տեքստը այստեղ..."></textarea>
  <br>
  <button onclick="speakText()">Հաստատել</button>

  <script>
    function speakText() {
      const text = document.getElementById("text-input").value;

      if (!('speechSynthesis' in window)) {
        alert("SpeechSynthesis API is not supported in this browser.");
        return;
      }

      const speech = new SpeechSynthesisUtterance(text);
      speech.lang = "en-US"; // English (United States)
      speech.pitch = 1;      // Voice pitch
      speech.rate = 1;       // Speaking rate

      const voices = speechSynthesis.getVoices();
      const englishVoice = voices.find(voice => voice.lang === "en-US");

      if (englishVoice) {
        speech.voice = englishVoice;
      }

      window.speechSynthesis.speak(speech);
    }
  </script>
</body>
</html>
