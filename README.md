     <img src="https://assets.onecompiler.app/42ryuv2wx/42w5r3zgz/1000000238.jpg" alt="" />
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Class 11 Maths Sets - Interactive DPP for Teacher (Fixed for Codespaces)</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@600&family=Roboto&display=swap');
    * { box-sizing: border-box; }
    body {
      font-family: 'Roboto', sans-serif;
      line-height: 1.6;
      background: linear-gradient(135deg, #79c7e3 0%, #5b9bd5 100%);
      margin: 0; padding: 20px; color: #222; min-height: 100vh;
      display: flex; flex-direction: column; align-items: center;
    }
    .container {
      background: #fff; max-width: 850px; width: 100%; border-radius: 16px;
      box-shadow: 0 8px 25px rgba(0,0,0,0.15);
      padding: 35px 40px 50px; margin-top: 30px;
    }
    header { text-align: center; margin-bottom: 30px; }
    header h1 {
      font-family: 'Montserrat', sans-serif; color: #004176; font-size: 2.8rem; margin: 0; letter-spacing: 2px;
    }
    header p { font-size: 1.2rem; color: #365f8a; margin-top: 6px; font-weight: 600; }
    .student-info {
      background: #e8f0fe; padding: 20px 25px; border-radius: 12px;
      box-shadow: inset 0 0 10px #a9c1fc; margin-bottom: 45px;
    }
    .student-info h2 {
      color: #0f3d91; font-family: 'Montserrat', sans-serif; font-weight: 700;
      margin-top: 0; margin-bottom: 18px; font-size: 1.8rem; letter-spacing: 1px;
    }
    .student-info label { display: block; font-weight: 700; color: #264d9e; margin-bottom: 7px; font-size: 1.05rem; }
    .student-info input[type="text"] {
      width: 100%; padding: 11px 14px; border-radius: 8px; border: 2.5px solid #a7bcf3;
      font-size: 1.1rem; margin-bottom: 20px; font-family: 'Roboto', sans-serif; transition: border-color 0.3s ease;
    }
    .student-info input[type="text"]:focus { border-color: #3557bf; outline: none; }
    form#dppForm { width: 100%; }
    .question-block {
      background: #f5faff; border-radius: 14px; padding: 25px 30px; margin-bottom: 30px;
      box-shadow: 0 6px 18px rgba(41, 124, 255, 0.12); user-select: none; position: relative; transition: background-color 0.3s ease;
    }
    .question-block.answered { background-color: #d0e1ff; box-shadow: 0 6px 18px rgba(0, 97, 255, 0.3); }
    .question-header { font-family: 'Montserrat', sans-serif; font-weight: 700; color: #004aad; font-size: 1.4rem; margin-bottom: 18px; letter-spacing: 0.8px; }
    .question-text { font-weight: 600; font-size: 1.15rem; margin-bottom: 18px; color: #253858; }
    .options { display: flex; flex-direction: column; gap: 14px; margin-bottom: 20px; }
    .options label {
      cursor: pointer; font-size: 1.1rem; padding: 10px 14px; border-radius: 10px;
      border: 2.5px solid transparent; transition: border-color 0.3s ease, background-color 0.3s ease;
      user-select: none; color: #33475b; background: #e9f0ff; font-weight: 600; line-height: 1.3;
    }
    .options input[type="radio"] { display: none; }
    .options input[type="radio"]:checked + label {
      border-color: #2065d1; background-color: #c7d9ff; color: #123a70;
    }
    .question-block.answered .options label { cursor: default; }
    .question-block.answered .options input[type="radio"] { pointer-events: none; }
    .integer-input { margin-bottom: 20px; }
    .integer-input input[type="number"] {
      padding: 10px 15px; font-size: 1.1rem; width: 120px; border-radius: 8px;
      border: 2.5px solid #a7bcf3; font-family: "Roboto", sans-serif; transition: border-color 0.3s ease;
    }
    .integer-input input[type="number"]:focus { border-color: #3557bf; outline: none; }
    .integer-input:disabled input { background: #dbe5ff; cursor: not-allowed; }
    .btn-submit-answer {
      background-color: #1a55d1; color: white; border: none; padding: 11px 26px; border-radius: 10px;
      font-weight: 700; letter-spacing: 0.8px; font-size: 1.05rem; cursor: pointer; user-select: none;
      transition: background-color 0.3s ease; height: 46px; align-self: flex-start;
    }
    .btn-submit-answer:disabled { background-color: #a2baf2; cursor: default; }
    .btn-submit-answer:hover:not(:disabled) { background-color: #133e8f; }
    .feedback-msg { margin-top: 12px; font-weight: 600; font-size: 1.1rem; color: #1f3784; user-select: none; }
    .feedback-msg.congrats { color: #1a8a2c; }
    .feedback-msg.sympathy { color: #bb2c59; }
    .score-card {
      background: #e6fee3; border-radius: 15px; box-shadow: 0 4px 12px rgba(35,195,49,0.1);
      padding: 18px 24px; margin: 38px auto 30px; font-family: 'Montserrat',sans-serif;
      color: #135d1b; font-size: 1.25rem; text-align: center; max-width: 420px; border: 2.5px solid #24c35e;
      font-weight: 700; letter-spacing: 0.8px; transition: background 0.4s, border .3s;
    }
    .score-card.final {
      background: #b6ffe0;
      border: 3.5px solid #24c35e;
      color: #12713f;
      font-size: 1.4rem;
      box-shadow: 0 2px 15px #24c35e44;
    }
    .final-submit { text-align: center; margin-top: 40px; }
    .final-submit button {
      background-color: #133e8f; color: white; font-size: 1.3rem; padding: 16px 52px;
      font-weight: 800; border-radius: 14px; cursor: pointer; transition: background-color 0.3s ease; letter-spacing: 1.5px; user-select: none;
    }
    .final-submit button:hover { background-color: #0e2b66; }
    .modal-overlay {
      position: fixed; top: 0; left: 0; right: 0; bottom: 0;
      background-color: rgba(0,0,0,0.45);
      display: flex; justify-content: center; align-items: center;
      z-index: 4096; opacity: 0; pointer-events: none; transition: opacity 0.3s ease;
    }
    .modal-overlay.active { opacity: 1; pointer-events: all; }
    .modal-content {
      background: white; border-radius: 16px; max-width: 500px; width: 90%;
      padding: 28px 32px 32px; box-shadow: 0 12px 40px rgba(0,0,0,0.2); text-align: center; user-select: none; position: relative; font-family: 'Roboto', sans-serif;
    }
    .modal-content h3 { color: #154a99; font-family: 'Montserrat', sans-serif; font-size: 1.9rem; margin: 0 0 12px; letter-spacing: 0.5px; }
    .modal-content p { color: #33475b; font-size: 1.1rem; line-height: 1.5; margin-bottom: 24px; }
    .modal-close-btn {
      background-color: #154a99; color: white; font-weight: 700; font-size: 1.1rem; border-radius: 12px;
      padding: 10px 28px; border: none; cursor: pointer; letter-spacing: 0.6px; user-select: none; transition: background-color 0.25s ease; border: 2px solid transparent;
    }
    .modal-close-btn:hover { background-color: #0d3263; border-color: #0d3263; }
    @media (max-width: 600px) {
      .container { padding: 25px 8px 28px; margin-top: 15px; }
      header h1 { font-size: 2rem; }
      header p { font-size: 1rem; }
      .question-header { font-size: 1.09rem; }
      .question-text { font-size: 1rem; }
      .btn-submit-answer { width: 100%; padding: 13px 0; }
      .answer-area { flex-direction: column; gap: 16px; }
      .integer-input input[type="number"] { width: 100%; }
      .score-card { font-size: 1.07rem; padding: 12px 5px;}
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <h1>Daily Practice Problems (DPP)</h1>
      <p>The answers you submit will be sent directly to your teacher.</p>
    </header>
    <form id="dppForm" novalidate>
      <section class="student-info">
        <h2>Student Information (Required)</h2>
        <label for="studentName">Student Name</label>
        <input type="text" id="studentName" name="studentName" placeholder="Your full name" required />
        <label for="regNumber">Student Registration Number</label>
        <input type="text" id="regNumber" name="regNumber" placeholder="Your registration number" required />
        <label for="batchCode">Batch Code</label>
        <input type="text" id="batchCode" name="batchCode" placeholder="Your batch code" required />
      </section>
      <!-- QUESTIONS - 9 poll + 1 integer -->
      <div class="question-block" id="q1">
        <div class="question-header">Question 1</div>
        <div class="question-text">Which of the following is the correct notation for an empty set?</div>
        <div class="options">
          <input type="radio" id="q1a" name="answer1" value="A" /><label for="q1a">A. {0}</label>
          <input type="radio" id="q1b" name="answer1" value="B" /><label for="q1b">B. { }</label>
          <input type="radio" id="q1c" name="answer1" value="C" /><label for="q1c">C. ∅</label>
          <input type="radio" id="q1d" name="answer1" value="D" /><label for="q1d">D. {∅}</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="1">Submit Answer</button>
        <div class="feedback-msg" id="feedback1"></div>
      </div>
      <div class="question-block" id="q2">
        <div class="question-header">Question 2</div>
        <div class="question-text">What is the cardinality of the set {a, e, i, o, u}?</div>
        <div class="options">
          <input type="radio" id="q2a" name="answer2" value="A" /><label for="q2a">A. 4</label>
          <input type="radio" id="q2b" name="answer2" value="B" /><label for="q2b">B. 5</label>
          <input type="radio" id="q2c" name="answer2" value="C" /><label for="q2c">C. 6</label>
          <input type="radio" id="q2d" name="answer2" value="D" /><label for="q2d">D. 7</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="2">Submit Answer</button>
        <div class="feedback-msg" id="feedback2"></div>
      </div>
      <div class="question-block" id="q3">
        <div class="question-header">Question 3</div>
        <div class="question-text">Which of the following is a subset of every set?</div>
        <div class="options">
          <input type="radio" id="q3a" name="answer3" value="A" /><label for="q3a">A. The empty set (∅)</label>
          <input type="radio" id="q3b" name="answer3" value="B" /><label for="q3b">B. The universal set (U)</label>
          <input type="radio" id="q3c" name="answer3" value="C" /><label for="q3c">C. Power set</label>
          <input type="radio" id="q3d" name="answer3" value="D" /><label for="q3d">D. Singleton set</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="3">Submit Answer</button>
        <div class="feedback-msg" id="feedback3"></div>
      </div>
      <div class="question-block" id="q4">
        <div class="question-header">Question 4</div>
        <div class="question-text">If A = {1, 2, 3} and B = {2, 3, 4}, what is A ∩ B?</div>
        <div class="options">
          <input type="radio" id="q4a" name="answer4" value="A" /><label for="q4a">A. {1, 2, 3, 4}</label>
          <input type="radio" id="q4b" name="answer4" value="B" /><label for="q4b">B. { }</label>
          <input type="radio" id="q4c" name="answer4" value="C" /><label for="q4c">C. {2, 3}</label>
          <input type="radio" id="q4d" name="answer4" value="D" /><label for="q4d">D. {1, 4}</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="4">Submit Answer</button>
        <div class="feedback-msg" id="feedback4"></div>
      </div>
      <div class="question-block" id="q5">
        <div class="question-header">Question 5</div>
        <div class="question-text">What is the power set of {a, b}?</div>
        <div class="options">
          <input type="radio" id="q5a" name="answer5" value="A" /><label for="q5a">A. {∅, {a}, {b}, {a, b}}</label>
          <input type="radio" id="q5b" name="answer5" value="B" /><label for="q5b">B. {{a}, {b}}</label>
          <input type="radio" id="q5c" name="answer5" value="C" /><label for="q5c">C. {{a, b}}</label>
          <input type="radio" id="q5d" name="answer5" value="D" /><label for="q5d">D. {a, b}</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="5">Submit Answer</button>
        <div class="feedback-msg" id="feedback5"></div>
      </div>
      <div class="question-block" id="q6">
        <div class="question-header">Question 6</div>
        <div class="question-text">Which one is NOT a set?</div>
        <div class="options">
          <input type="radio" id="q6a" name="answer6" value="A" /><label for="q6a">A. {2, 4, 6}</label>
          <input type="radio" id="q6b" name="answer6" value="B" /><label for="q6b">B. Set of even numbers</label>
          <input type="radio" id="q6c" name="answer6" value="C" /><label for="q6c">C. Collection of all beautiful paintings</label>
          <input type="radio" id="q6d" name="answer6" value="D" /><label for="q6d">D. {x : x > 0 and x < 10}</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="6">Submit Answer</button>
        <div class="feedback-msg" id="feedback6"></div>
      </div>
      <div class="question-block" id="q7">
        <div class="question-header">Question 7</div>
        <div class="question-text">If the universal set U = {1,2,3,4,5} and A = {2,4}, what is A′ (complement of A)?</div>
        <div class="options">
          <input type="radio" id="q7a" name="answer7" value="A" /><label for="q7a">A. {2, 4}</label>
          <input type="radio" id="q7b" name="answer7" value="B" /><label for="q7b">B. {1, 3, 5}</label>
          <input type="radio" id="q7c" name="answer7" value="C" /><label for="q7c">C. ∅</label>
          <input type="radio" id="q7d" name="answer7" value="D" /><label for="q7d">D. {1, 2, 3, 4, 5}</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="7">Submit Answer</button>
        <div class="feedback-msg" id="feedback7"></div>
      </div>
      <div class="question-block" id="q8">
        <div class="question-header">Question 8</div>
        <div class="question-text">Which of the following is true about finite and infinite sets?</div>
        <div class="options">
          <input type="radio" id="q8a" name="answer8" value="A" /><label for="q8a">A. Infinite sets have countable number of elements</label>
          <input type="radio" id="q8b" name="answer8" value="B" /><label for="q8b">B. Finite sets have unlimited elements</label>
          <input type="radio" id="q8c" name="answer8" value="C" /><label for="q8c">C. Finite sets have limited elements, infinite sets have unlimited elements</label>
          <input type="radio" id="q8d" name="answer8" value="D" /><label for="q8d">D. Both finite and infinite sets must be empty</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="8">Submit Answer</button>
        <div class="feedback-msg" id="feedback8"></div>
      </div>
      <div class="question-block" id="q9">
        <div class="question-header">Question 9</div>
        <div class="question-text">Set A = {2, 4, 6}, Set B = {1, 2, 3, 4}. Is A a subset of B?</div>
        <div class="options">
          <input type="radio" id="q9a" name="answer9" value="A" /><label for="q9a">A. Yes</label>
          <input type="radio" id="q9b" name="answer9" value="B" /><label for="q9b">B. No</label>
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="9">Submit Answer</button>
        <div class="feedback-msg" id="feedback9"></div>
      </div>
      <div class="question-block" id="q10">
        <div class="question-header">Question 10 (Integer Input)</div>
        <div class="question-text">How many elements are in the power set of a set containing 3 elements?</div>
        <div class="integer-input">
          <input type="number" id="answer10" name="answer10" placeholder="Enter an integer" />
        </div>
        <button type="button" class="btn-submit-answer" data-qnum="10">Submit Answer</button>
        <div class="feedback-msg" id="feedback10"></div>
      </div>
      <!-- SCORE CARD -->
      <div id="scoreCard" class="score-card">Score: 0 / 10 &nbsp; | &nbsp; Correct Answers: 0 out of 10</div>
      <div class="final-submit">
        <button type="submit" id="finalSubmitBtn">Submit Entire DPP</button>
      </div>
    </form>
  </div>

  <!-- Modal for solution -->
  <div class="modal-overlay" id="solutionModal" aria-hidden="true">
    <div class="modal-content" role="dialog" aria-modal="true" aria-labelledby="modalTitle" aria-describedby="modalDesc">
      <h3 id="modalTitle">Solution</h3>
      <p id="modalDesc"></p>
      <button class="modal-close-btn" aria-label="Close solution popup" onclick="closeModal()">Close</button>
    </div>
  </div>

  <script>
    const correctAnswers = {
      1: "C", 2: "B", 3: "A", 4: "C", 5: "A", 6: "C", 7: "B", 8: "C", 9: "B", 10: 8
    };
    const solutions = {
      1: "The correct notation for an empty set is the symbol ∅.",
      2: "The set of vowels {a, e, i, o, u} has 5 elements, so the cardinality is 5.",
      3: "The empty set ∅ is a subset of every set by definition.",
      4: "The intersection A ∩ B contains elements common to both sets: {2, 3}.",
      5: "The power set of {a, b} includes all subsets: ∅, {a}, {b}, and {a, b}.",
      6: "A 'collection of all beautiful paintings' is not well-defined and does not form a set.",
      7: "The complement of A in U contains all elements in U not in A, which is {1, 3, 5}.",
      8: "Finite sets have limited elements; infinite sets have unlimited elements.",
      9: "A = {2, 4, 6} is not a subset of B = {1, 2, 3, 4} because 6 is not in B.",
      10: "The power set of a set with 3 elements has 2³ = 8 elements."
    };

    let score = 0;
    let correctCount = 0;
    let answered = {};

    // Attach event listeners to all submit answer buttons
    document.querySelectorAll(".btn-submit-answer").forEach(button => {
      button.addEventListener("click", () => {
        const qnum = parseInt(button.getAttribute("data-qnum"), 10);
        submitAnswer(qnum);
      });
    });

    // Prevent default submit and handle form submit manually
    document.getElementById("dppForm").addEventListener("submit", function(event) {
      event.preventDefault();
      finalSubmit();
    });

    function updateScoreCard(final = false) {
      const card = document.getElementById("scoreCard");
      card.textContent = `Score: ${score} / 10 \u00A0 | \u00A0 Correct Answers: ${correctCount} out of 10`;
      if(final) card.classList.add("final");
      else card.classList.remove("final");
    }

    function submitAnswer(qnum) {
      if(answered[qnum]) return; // Already answered
      const qBlock = document.getElementById("q" + qnum);
      if (!qBlock) return;
      const feedback = document.getElementById("feedback" + qnum);
      feedback.textContent = "";

      if(qnum === 10) {
        const input = document.getElementById("answer10");
        if(!input) return;
        if(input.value.trim() === "") {
          alert("Please enter your answer for Question 10 before submitting.");
          input.focus();
          return;
        }
        if(isNaN(input.value) || !Number.isInteger(Number(input.value))) {
          alert("Please enter a valid integer for Question 10.");
          input.focus();
          return;
        }
        const studentAnswer = Number(input.value);
        let isCorrect = (studentAnswer === correctAnswers[10]);
        if(isCorrect) {
          feedback.textContent = "🎉 Congratulations! Your answer is correct.";
          feedback.className = "feedback-msg congrats";
          score++;
          correctCount++;
        } else {
          feedback.textContent = "☹️ Sorry, that is incorrect.";
          feedback.className = "feedback-msg sympathy";
        }
        input.disabled = true;
        qBlock.querySelector(".btn-submit-answer").disabled = true;
        showSolution(qnum);
        qBlock.classList.add("answered");
        answered[qnum] = true;
        updateScoreCard();
        return;
      }

      // Poll questions
      const options = qBlock.querySelectorAll("input[type='radio']");
      let selectedValue = null;
      options.forEach(opt => { if(opt.checked) selectedValue = opt.value; });
      if(selectedValue === null) {
        alert("Please select an option for Question " + qnum + " before submitting.");
        return;
      }
      let isCorrect = (selectedValue === correctAnswers[qnum]);
      if(isCorrect) {
        feedback.textContent = "🎉 Congratulations! Your answer is correct.";
        feedback.className = "feedback-msg congrats";
        score++;
        correctCount++;
      } else {
        feedback.textContent = "☹️ Sorry, that is incorrect.";
        feedback.className = "feedback-msg sympathy";
      }
      options.forEach(opt => {
        opt.disabled = true;
        let label = qBlock.querySelector(`label[for="${opt.id}"]`);
        if(label) label.style.pointerEvents = "none";
      });
      qBlock.querySelector(".btn-submit-answer").disabled = true;
      showSolution(qnum);
      qBlock.classList.add("answered");
      answered[qnum] = true;
      updateScoreCard();
    }

    const modal = document.getElementById("solutionModal"), modalDesc = document.getElementById("modalDesc");
    function showSolution(qnum) {
      modalDesc.textContent = solutions[qnum] || "Solution not available.";
      modal.classList.add("active");
      modal.setAttribute("aria-hidden", "false");
      modal.querySelector(".modal-close-btn").focus();
    }
    function closeModal() {
      modal.classList.remove("active");
      modal.setAttribute("aria-hidden", "true");
    }

    function finalSubmit() {
      const studentName = document.getElementById("studentName").value.trim();
      const regNumber = document.getElementById("regNumber").value.trim();
      const batchCode = document.getElementById("batchCode").value.trim();
      if(!studentName || !regNumber || !batchCode) {
        alert("Please fill all the Student Information fields before submitting.");
        return;
      }
      let unanswered = [];
      for(let i=1; i<=10; i++) {
        if(!answered[i]) unanswered.push(i);
      }
      if(unanswered.length > 0) {
        alert("Please submit answers for all questions before final submission. Unanswered: " + unanswered.join(", "));
        return;
      }
      updateScoreCard(true);
      alert(`Thank you ${studentName}!\nYour answers and score (${score}/10) have been recorded and sent to the teacher.\nYou can now close this page or start a new attempt.`);
    }

  </script>
</body>
</html>
