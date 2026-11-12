<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vocabulary Practice — Personality & Communication</title>

<style>
:root {
  --navy: #172b4d;
  --blue: #315b96;
  --light: #eef4fb;
  --accent: #e5a94b;
  --green: #dff3e5;
  --red: #fde5e5;
  --border: #d9e2ef;
  --text: #253247;
}

* { box-sizing: border-box; }

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f4f6fa;
  color: var(--text);
  line-height: 1.6;
}

header {
  background: linear-gradient(135deg, #172b4d, #315b96);
  color: white;
  padding: 38px 20px;
  text-align: center;
}

header h1 { margin: 0 0 8px; font-size: 30px; }
header p { margin: 0; opacity: .9; }

nav {
  position: sticky;
  top: 0;
  z-index: 10;
  background: white;
  padding: 12px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 8px;
  box-shadow: 0 2px 8px #0001;
}

nav a {
  text-decoration: none;
  color: var(--navy);
  background: var(--light);
  padding: 8px 13px;
  border-radius: 20px;
  font-size: 14px;
  font-weight: bold;
}

nav a:hover { background: var(--blue); color: white; }

.container {
  max-width: 1100px;
  margin: auto;
  padding: 22px;
}

section {
  background: white;
  padding: 25px;
  margin: 25px 0;
  border-radius: 16px;
  box-shadow: 0 3px 12px #0000000b;
}

h2 {
  color: var(--navy);
  margin-top: 0;
  border-bottom: 2px solid var(--light);
  padding-bottom: 10px;
}

.instruction {
  background: var(--light);
  border-left: 4px solid var(--blue);
  padding: 12px 16px;
  border-radius: 7px;
  margin: 15px 0 20px;
}

button {
  border: none;
  border-radius: 8px;
  padding: 11px 18px;
  cursor: pointer;
  font-size: 15px;
  font-weight: bold;
  background: var(--blue);
  color: white;
  margin: 5px 4px 5px 0;
}

button:hover { opacity: .88; }
button.secondary { background: #e8edf5; color: var(--navy); }

.cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(210px, 1fr));
  gap: 14px;
}

.flashcard {
  min-height: 130px;
  perspective: 900px;
  cursor: pointer;
}

.flashcard-inner {
  position: relative;
  width: 100%;
  min-height: 130px;
  transition: transform .5s;
  transform-style: preserve-3d;
}

.flashcard.flipped .flashcard-inner { transform: rotateY(180deg); }

.card-front, .card-back {
  position: absolute;
  width: 100%;
  min-height: 130px;
  backface-visibility: hidden;
  border-radius: 12px;
  padding: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  box-shadow: 0 2px 8px #00000012;
}

.card-front {
  background: #eaf1fa;
  color: var(--navy);
  font-weight: bold;
  font-size: 17px;
}

.card-back {
  background: #fff2dc;
  color: #5b431d;
  transform: rotateY(180deg);
}

.hint {
  color: #718096;
  font-size: 13px;
  text-align: center;
  margin-top: 12px;
}

.match-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(290px, 1fr));
  gap: 22px;
}

.match-item {
  background: #f8faff;
  border: 1px solid var(--border);
  border-radius: 9px;
  padding: 12px;
  margin-bottom: 9px;
}

.match-item label {
  display: block;
  font-weight: bold;
  margin-bottom: 7px;
}

select {
  width: 100%;
  padding: 10px;
  border: 1px solid #cbd5e1;
  border-radius: 7px;
  background: white;
  font-size: 14px;
  color: var(--text);
}

.question {
  padding: 14px;
  margin: 12px 0;
  background: #f8faff;
  border: 1px solid var(--border);
  border-radius: 9px;
}

.question.correct, .match-item.correct {
  background: var(--green);
  border-color: #77bd8c;
}

.question.incorrect, .match-item.incorrect {
  background: var(--red);
  border-color: #e69a9a;
}

.question input {
  width: 100%;
  padding: 11px;
  margin-top: 9px;
  border: 1px solid #cbd5e1;
  border-radius: 7px;
  font-size: 15px;
}

.feedback {
  font-size: 14px;
  margin-top: 7px;
  font-weight: bold;
}

.result {
  padding: 15px;
  border-radius: 9px;
  margin-top: 15px;
  background: var(--light);
  font-weight: bold;
  display: none;
}

footer {
  text-align: center;
  padding: 25px;
  color: #718096;
}

@media(max-width:600px) {
  header h1 { font-size: 24px; }
  section { padding: 17px; }
  .container { padding: 12px; }
}
</style>
</head>

<body>

<header>
  <h1>Vocabulary Practice</h1>
  <p>Personality, Communication & Social Interaction</p>
  <p>Уровень B1–B2</p>
</header>

<nav>
  <a href="#cards">Flashcards</a>
  <a href="#exercise1">Exercise 1</a>
  <a href="#exercise2">Exercise 2</a>
  <a href="#exercise3">Exercise 3</a>
</nav>

<div class="container">

<section id="cards">
  <h2>1. Flashcards — Карточки для запоминания</h2>
  <div class="instruction">
    Нажимай на карточку, чтобы увидеть перевод. Постарайся сначала вспомнить значение самостоятельно.
  </div>
  <div class="cards" id="flashcards"></div>
  <p class="hint">Нажми на карточку, чтобы перевернуть её.</p>
  <button class="secondary" onclick="shuffleCards()">Перемешать карточки</button>
</section>

<section id="exercise1">
  <h2>2. Exercise 1 — Match the expressions with their Russian translations</h2>
  <div class="instruction">
    Соедини английские выражения с правильными переводами.
  </div>
  <div class="match-list" id="exercise1-list"></div>
  <button onclick="checkMatching(1)">Check answers</button>
  <button class="secondary" onclick="resetMatching(1)">Try again</button>
  <div class="result" id="result1"></div>
</section>

<section id="exercise2">
  <h2>3. Exercise 2 — Match the expressions with their definitions</h2>
  <div class="instruction">
    Соедини каждое выражение с подходящим определением на английском языке.
  </div>
  <div class="match-list" id="exercise2-list"></div>
  <button onclick="checkMatching(2)">Check answers</button>
  <button class="secondary" onclick="resetMatching(2)">Try again</button>
  <div class="result" id="result2"></div>
</section>

<section id="exercise3">
  <h2>4. Exercise 3 — Complete the sentences</h2>
  <div class="instruction">
    Заполни пропуски подходящими выражениями из изученного списка.
    Используй каждое выражение не более одного раза.
    Вариантов ответа нет — вспомни выражения самостоятельно.
  </div>
  <div id="exercise3-list"></div>
  <button onclick="checkExercise3()">Check answers</button>
  <button class="secondary" onclick="resetExercise3()">Try again</button>
  <div class="result" id="result3"></div>
</section>

</div>

<footer>
  Vocabulary Practice · Personality & Social Interaction
</footer>

<script>

const vocabulary = [
  ["Wallflower", "Скромный, застенчивый человек, который держится в стороне на вечеринках"],
  ["To feel guilty for", "Чувствовать вину за что-либо"],
  ["Prefer quiet chats to loud crowds", "Предпочитать спокойные беседы шумным компаниям"],
  ["Stimulating", "Стимулирующий, интеллектуально интересный"],
  ["Relate to something", "Находить что-то близким и понятным себе"],
  ["Countless", "Бесчисленный, неисчислимый"],
  ["Life and soul of the party", "Душа компании"],
  ["To point out", "Указывать на что-либо, обращать внимание"],
  ["To bring something to the table", "Вносить свой вклад, предлагать что-то ценное"],
  ["Tend to", "Иметь склонность, обычно делать что-либо"],
  ["Reflective", "Задумчивый, склонный к размышлениям"],
  ["Think things through", "Тщательно всё обдумывать"],
  ["Impetuous", "Импульсивный, порывистый"],
  ["Collaborative assignment", "Совместное задание или проект"],
  ["See the bigger picture", "Видеть общую картину"],
  ["Don't get me wrong", "Не поймите меня неправильно"],
  ["Take something less seriously", "Относиться к чему-либо менее серьёзно"],
  ["Rise to the occasion", "Проявить себя в нужный момент, справиться с ситуацией"],
  ["Take centre stage", "Оказаться в центре внимания"],
  ["On the whole", "В целом"],
  ["In the spotlight", "В центре внимания"],
  ["Social butterfly", "Очень общительный человек, который легко заводит знакомства"]
];

function renderCards(data) {
  const container = document.getElementById("flashcards");
  container.innerHTML = "";

  data.forEach(item => {
    const card = document.createElement("div");
    card.className = "flashcard";
    card.innerHTML = `
      <div class="flashcard-inner">
        <div class="card-front">${item[0]}</div>
        <div class="card-back">${item[1]}</div>
      </div>
    `;
    card.addEventListener("click", () => card.classList.toggle("flipped"));
    container.appendChild(card);
  });
}

function shuffleCards() {
  const shuffled = [...vocabulary].sort(() => Math.random() - 0.5);
  renderCards(shuffled);
}

renderCards(vocabulary);

const translations = [
  "Бесчисленный",
  "Не поймите меня неправильно",
  "Вносить свой вклад, предлагать что-то ценное",
  "Склонный к размышлениям",
  "Душа компании",
  "Предпочитать спокойные беседы шумным компаниям",
  "Иметь склонность, обычно делать что-либо",
  "Совместное задание или проект",
  "Чувствовать вину за что-либо",
  "Видеть общую картину",
  "Оказаться в центре внимания",
  "Стимулирующий, интеллектуально интересный",
  "Импульсивный, порывистый",
  "В целом",
  "Указывать на что-либо",
  "Тщательно всё обдумывать",
  "Очень общительный человек",
  "Находить что-то близким и понятным себе",
  "Проявить себя в нужный момент",
  "Скромный человек, который держится в стороне на вечеринках",
  "Относиться к чему-либо менее серьёзно",
  "В центре внимания"
];

const ex1 = [
  ["A. Wallflower", 20],
  ["B. To feel guilty for", 9],
  ["C. Prefer quiet chats to loud crowds", 6],
  ["D. Stimulating", 12],
  ["E. Relate to something", 18],
  ["F. Countless", 1],
  ["G. Life and soul of the party", 5],
  ["H. To point out", 15],
  ["I. To bring something to the table", 3],
  ["J. Tend to", 7],
  ["K. Reflective", 4],
  ["L. Think things through", 16],
  ["M. Impetuous", 13],
  ["N. Collaborative assignment", 8],
  ["O. See the bigger picture", 10],
  ["P. Don't get me wrong", 2],
  ["Q. Take something less seriously", 21],
  ["R. Rise to the occasion", 19],
  ["S. Take centre stage", 11],
  ["T. On the whole", 14],
  ["U. In the spotlight", 22],
  ["V. Social butterfly", 17]
];

const definitions = [
  "To carefully consider all the possible consequences before making a decision.",
  "A person who is very sociable and enjoys meeting and talking to new people.",
  "To feel responsible or unhappy because you have done something wrong.",
  "To have a natural tendency to behave in a particular way.",
  "A person who is shy and does not easily join in with social activities.",
  "Interesting and exciting because it makes you think or learn something new.",
  "To understand someone's experience because you have experienced something similar.",
  "A person who makes a party enjoyable and keeps everyone entertained.",
  "To contribute useful skills, ideas or qualities to a situation or group.",
  "A person who thinks carefully about their experiences and feelings.",
  "Acting quickly without thinking carefully about the consequences.",
  "A task that requires people to work together.",
  "To understand how individual details are connected and consider the general situation.",
  "To draw someone's attention to a particular fact or detail.",
  "Too many to be counted.",
  "To respond successfully to a difficult situation when people need you.",
  "To attract everyone's attention and become the main person in a situation.",
  "To become the main focus of people's attention.",
  "To avoid treating a situation as more important or serious than it really is.",
  "To enjoy having calm conversations rather than being surrounded by many noisy people.",
  "A phrase used to clarify that you do not want your words to be misunderstood.",
  "Considering everything; generally speaking."
];

const ex2 = [
  ["1. Wallflower", 5],
  ["2. To feel guilty for", 3],
  ["3. Stimulating", 6],
  ["4. Relate to something", 7],
  ["5. Life and soul of the party", 8],
  ["6. To bring something to the table", 9],
  ["7. Tend to", 4],
  ["8. Reflective", 10],
  ["9. Impetuous", 11],
  ["10. Collaborative assignment", 12],
  ["11. See the bigger picture", 13],
  ["12. Think things through", 1],
  ["13. To point out", 14],
  ["14. Countless", 15],
  ["15. Rise to the occasion", 16],
  ["16. Take centre stage", 17],
  ["17. In the spotlight", 18],
  ["18. Social butterfly", 2],
  ["19. Take something less seriously", 19],
  ["20. Prefer quiet chats to loud crowds", 20],
  ["21. Don't get me wrong", 21],
  ["22. On the whole", 22]
];

function renderMatching(number) {
  const list = number === 1 ? ex1 : ex2;
  const options = number === 1 ? translations : definitions;
  const container = document.getElementById(`exercise${number}-list`);

  container.innerHTML = "";

  list.forEach((item, index) => {
    const div = document.createElement("div");
    div.className = "match-item";

    const select = document.createElement("select");
    select.id = `ex${number}-answer-${index}`;
    select.innerHTML = `<option value="">— Choose an answer —</option>`;

    options.forEach((option, optionIndex) => {
      const opt = document.createElement("option");
      opt.value = optionIndex + 1;
      opt.textContent = `${optionIndex + 1}. ${option}`;
      select.appendChild(opt);
    });

    const label = document.createElement("label");
    label.textContent = item[0];

    div.appendChild(label);
    div.appendChild(select);
    container.appendChild(div);
  });
}

renderMatching(1);
renderMatching(2);

function checkMatching(number) {
  const list = number === 1 ? ex1 : ex2;
  let score = 0;

  list.forEach((item, index) => {
    const select = document.getElementById(`ex${number}-answer-${index}`);
    const parent = select.parentElement;
    parent.classList.remove("correct", "incorrect");

    if (Number(select.value) === item[1]) {
      score++;
      parent.classList.add("correct");
    } else {
      parent.classList.add("incorrect");
    }
  });

  const result = document.getElementById(`result${number}`);
  result.style.display = "block";
  result.textContent = `Your score: ${score} / ${list.length}`;
}

function resetMatching(number) {
  const list = number === 1 ? ex1 : ex2;

  list.forEach((item, index) => {
    const select = document.getElementById(`ex${number}-answer-${index}`);
    select.value = "";
    select.parentElement.classList.remove("correct", "incorrect");
  });

  document.getElementById(`result${number}`).style.display = "none";
}

/* EXERCISE 3 */

const sentences = [
  "Emma doesn't enjoy large parties. She's quite a ______ and usually spends the evening talking to one or two people.",
  "I still ______ missing my best friend's birthday, even though it happened several weeks ago.",
  "I find conversations about psychology really ______ because they make me think about human behaviour.",
  "I can really ______ people who feel nervous before speaking in public.",
  "There are ______ ways to improve your communication skills.",
  "Everyone loves inviting Jack to parties because he's always the ______.",
  "I'd like to ______ one important detail before we make our final decision.",
  "What do you think you can ______ when working in an international team?",
  "I ______ spend my weekends reading or going for long walks rather than attending crowded events.",
  "She's a very ______ person who often spends time thinking about her decisions and experiences.",
  "Don't make a decision immediately. You should ______ before accepting the offer.",
  "His ______ decision surprised everyone because he hadn't considered the possible consequences.",
  "We have to complete a ______, so everyone needs to contribute ideas and do their part.",
  "When working on a difficult problem, it's important to ______ instead of concentrating only on small details.",
  "______, I really enjoyed the conference, although some presentations were too long.",
  "She often ______ arrive early because she likes having enough time to prepare.",
  "______, I think your idea is excellent, but we should consider the possible disadvantages too.",
  "When the manager was unexpectedly absent, Sarah ______ and successfully led the meeting.",
  "He doesn't usually like being the centre of attention, but today he decided to ______ during the presentation.",
  "After winning the competition, the young singer found herself ______.",
  "You should learn to ______ criticism instead of worrying about every small comment.",
  "My cousin is a real ______. She makes friends wherever she goes."
];

const answers3 = [
  ["wallflower"],
  ["feel guilty for"],
  ["stimulating"],
  ["relate to"],
  ["countless"],
  ["life and soul of the party"],
  ["point out"],
  ["bring to the table"],
  ["prefer quiet chats to loud crowds"],
  ["reflective"],
  ["think things through"],
  ["impetuous"],
  ["collaborative assignment"],
  ["see the bigger picture"],
  ["on the whole"],
  ["tends to"],
  ["don't get me wrong", "dont get me wrong"],
  ["rose to the occasion"],
  ["take centre stage", "take center stage"],
  ["in the spotlight"],
  ["take criticism less seriously"],
  ["social butterfly"]
];

function renderExercise3() {
  const container = document.getElementById("exercise3-list");
  container.innerHTML = "";

  sentences.forEach((sentence, index) => {
    const div = document.createElement("div");
    div.className = "question";
    div.id = `q3-${index}`;

    const label = document.createElement("div");
    label.innerHTML = `<strong>${index + 1}.</strong> ${sentence}`;

    const input = document.createElement("input");
    input.type = "text";
    input.id = `answer3-${index}`;
    input.placeholder = "Write your answer here...";

    const feedback = document.createElement("div");
    feedback.className = "feedback";
    feedback.id = `feedback3-${index}`;

    div.appendChild(label);
    div.appendChild(input);
    div.appendChild(feedback);
    container.appendChild(div);
  });
}

renderExercise3();

function normalize(text) {
  return text.toLowerCase()
    .trim()
    .replace(/[.,!?;:'"“”‘’]/g, "")
    .replace(/\s+/g, " ");
}

function checkExercise3() {
  let score = 0;

  answers3.forEach((acceptableAnswers, index) => {
    const input = document.getElementById(`answer3-${index}`);
    const question = document.getElementById(`q3-${index}`);
    const feedback = document.getElementById(`feedback3-${index}`);

    const userAnswer = normalize(input.value);
    const correct = acceptableAnswers.some(answer =>
      normalize(answer) === userAnswer
    );

    question.classList.remove("correct", "incorrect");

    if (correct) {
      score++;
      question.classList.add("correct");
      feedback.textContent = "✓ Correct!";
      feedback.style.color = "#237344";
    } else {
      question.classList.add("incorrect");
      feedback.textContent = input.value.trim()
        ? "✗ Check your answer."
        : "Please complete this sentence.";
      feedback.style.color = "#b83232";
    }
  });

  const result = document.getElementById("result3");
  result.style.display = "block";
  result.textContent = `Your score: ${score} / ${answers3.length}`;
}

function resetExercise3() {
  answers3.forEach((item, index) => {
    const input = document.getElementById(`answer3-${index}`);
    const question = document.getElementById(`q3-${index}`);
    const feedback = document.getElementById(`feedback3-${index}`);

    input.value = "";
    question.classList.remove("correct", "incorrect");
    feedback.textContent = "";
  });

  document.getElementById("result3").style.display = "none";
}

</script>
</body>
</html>
