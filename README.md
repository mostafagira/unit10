<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Quiz: Vocabulary and Grammar</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f4f8;
      padding: 20px;
      max-width: 900px;
      margin: auto;
    }
    .quiz-box {
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    .question {
      font-weight: bold;
      margin-top: 15px;
    }
    .answers label {
      display: block;
      margin-bottom: 5px;
    }
    button {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 16px;
      background-color: #3498db;
      color: white;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }
    #result {
      margin-top: 20px;
      font-size: 1.2em;
      font-weight: bold;
      color: green;
    }
  </style>
</head>
<body>
  <div class="quiz-box">
    <h2>Vocabulary & Grammar Quiz</h2>
    <form id="quizForm"></form>
    <button onclick="submitQuiz()">Submit Answers</button>
    <div id="result"></div>
  </div>

  <script>
    const questions = [
      { q: "1. The antonym of the verb 'trust' is …………………", options: ["recognise", "realise", "depend", "doubt"], answer: "doubt" },
      { q: "2. Police officers are looking ………… the disappearance of two children.", options: ["for", "of", "into", "up"], answer: "into" },
      { q: "3. The shop owner left his elder son in…………………. of the shop.", options: ["change", "charge", "account", "balance"], answer: "charge" },
      { q: "4. The synonym of the verb 'identify' is ………………", options: ["determine", "damage", "remove", "achieve"], answer: "determine" },
      { q: "5. Famous people are always ………… by TV channels.", options: ["interviewed", "offered", "tested", "searched"], answer: "interviewed" },
      { q: "6. The correspondent has refused to reveal his ………………..", options: ["sources", "results", "effects", "doubts"], answer: "sources" },
      { q: "7. Our new manager really cares ……………. his employees.", options: ["of", "about", "out", "at"], answer: "about" },
      { q: "8. The discovery of DNA was a major scientific ……………..……...", options: ["failure", "achievement", "advanced", "revision"], answer: "achievement" },
      { q: "9. At the entrance of Abu Simbel, there are four huge …………….", options: ["baggage", "rest rooms", "sculptures", "views"], answer: "sculptures" },
      { q: "10. Big stores have to ....................... for customers in the Christmas season.", options: ["compete", "complete", "comprehend", "competitive"], answer: "compete" },
      { q: "11. There were floods because it …………………. for three days.", options: ["rains", "had been raining", "has been raining", "was raining"], answer: "had been raining" },
      { q: "12. By the time he was 12, my brother ………………….. 3 languages.", options: ["learns", "learnt", "had learnt", "has learnt"], answer: "had learnt" },
      { q: "13. Jack knew Steve was at the match because Steve ………………… him.", options: ["would phone", "phones", "had phoned", "was phoning"], answer: "had phoned" },
      { q: "14. By the time she …………………….. her report, she had drunk six cups of tea.", options: ["finishes", "finished", "has finished", "was finishing"], answer: "finished" },
      { q: "15. The little children's clothes ………………. dirty from playing all day.", options: ["were being", "are", "have been", "were"], answer: "were" },
      { q: "16. He ……………… for only 3 weeks before failing his test.", options: ["had been driving", "was driving", "drives", "to drive"], answer: "had been driving" },
      { q: "17. The town was flooded. It …………………………. for 3 days.", options: ["had been raining", "has rained", "has been raining", "rains"], answer: "had been raining" },
      { q: "18. Before …………………… this novel, he had become famous.", options: ["wrote", "writing", "had written", "has written"], answer: "writing" },
      { q: "19. When she went out to play, she................ her homework.", options: ["had already done", "has already done", "was already doing", "does"], answer: "had already done" },
      { q: "20. My brother ate all of the cake that our mum .......................", options: ["will make", "has made", "had made", "used to make"], answer: "had made" }
    ];

    const form = document.getElementById("quizForm");

    questions.forEach((item, i) => {
      const block = document.createElement("div");
      block.innerHTML = `
        <div class="question">${item.q}</div>
        <div class="answers">
          ${item.options.map((opt, j) => `
            <label><input type="radio" name="q${i}" value="${opt}" required> ${String.fromCharCode(97 + j)} - ${opt}</label>
          `).join("")}
        </div>
      `;
      form.appendChild(block);
    });

    function submitQuiz() {
      let score = 0;
      questions.forEach((item, i) => {
        const selected = document.querySelector(`input[name="q${i}"]:checked`);
        if (selected && selected.value === item.answer) {
          score++;
        }
      });
      document.getElementById("result").innerText = `✅ You scored ${score} out of ${questions.length}`;
    }
  </script>
</body>
</html>
