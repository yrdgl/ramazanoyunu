// Oyun Verileri
const concepts = [
    { id: 1, term: "Sahur", definition: "Oruç tutmak için imsaktan önce yemek yenilen vakit" },
    { id: 2, term: "İmsak", definition: "Oruç başlama vakti" },
    { id: 3, term: "İftar", definition: "Akşam ezanı okununca orucun açılması" },
    { id: 4, term: "Teravih", definition: "Ramazan ayında yatsıdan sonra kılınan sünnet namaz" },
    { id: 5, term: "Mukabele", definition: "Bir kişinin Kur'an okuması, diğerlerinin Mushaf'tan takip etmesi" },
    { id: 6, term: "Fitre", definition: "Ramazan ayında verilen vacip sadaka" },
    { id: 7, term: "Fidye", definition: "Oruç tutamayan kişinin fakiri doyuracak kadar verdiği bedel" },
    { id: 8, term: "Farz Oruç", definition: "Allah'ın emrettiği oruçtur (Ramazan orucu gibi)" },
    { id: 9, term: "Vacip Oruç", definition: "Dinen tutulması gereken oruç (adak orucu gibi)" },
    { id: 10, term: "Sünnet Oruç", definition: "Peygamberimizin tavsiye ettiği oruçlar" },
    { id: 11, term: "Kaza Orucu", definition: "Tutulamayan Ramazan oruçlarının daha sonra tutulması" },
    { id: 12, term: "Kefaret Orucu", definition: "Mazeretsiz bozulan Ramazan orucunun telafisi için tutulan oruçtur" }
];

const matchingConcepts = concepts.slice(0, 7);

const quizQuestions = [
    {
        question: "Sahur nedir?",
        options: [
            "Oruç tutmak için imsaktan önce yemek yenilen vakit",
            "Akşam ezanında orucu açma vakti",
            "Öğle namazından sonraki vakit"
        ],
        correctAnswer: 0,
        explanation: "Sahur, oruç tutmak için imsaktan önce yemek yenilen vakittir. Sahur yapmak sünnettir."
    },
    {
        question: "İmsak vakti ne anlama gelir?",
        options: [
            "Orucun açılma vakti",
            "Oruç başlama vakti",
            "Akşam ezanı vakti"
        ],
        correctAnswer: 1,
        explanation: "İmsak, orucun başladığı vakittir. Bu vakitten sonra yemek içmek orucu bozar."
    },
    {
        question: "İftar ne zaman yapılır?",
        options: [
            "Öğle namazı vakti",
            "Güneş batmadan önce",
            "Akşam ezanı okunduğunda"
        ],
        correctAnswer: 2,
        explanation: "İftar, akşam ezanı okunduğunda yapılır. Oruç bu vakitte açılır."
    },
    {
        question: "Teravih namazı ne zaman kılınır?",
        options: [
            "Ramazan ayında yatsıdan sonra",
            "Sabah namazından önce",
            "Öğle namazından sonra"
        ],
        correctAnswer: 0,
        explanation: "Teravih namazı, Ramazan ayında yatsı namazından sonra kılınan sünnet namazdır."
    },
    {
        question: "Mukabele nedir?",
        options: [
            "Oruç tutma şekli",
            "Bir kişinin Kur'an okuması, diğerlerinin Mushaf'tan takip etmesi",
            "Ramazan ayında verilen sadaka"
        ],
        correctAnswer: 1,
        explanation: "Mukabele, Ramazan ayında bir kişinin Kur'an okuması, diğer kişilerin de Mushaf'tan takip etmesidir."
    },
    {
        question: "Fitre nedir?",
        options: [
            "Oruç başlama vakti",
            "Ramazan ayında verilen vacip sadaka",
            "Bir oruç çeşidi"
        ],
        correctAnswer: 1,
        explanation: "Fitre, Ramazan ayında fakir ve yoksullara verilen vacip sadakadır."
    },
    {
        question: "Fidye ne anlama gelir?",
        options: [
            "Ramazan ayında kılınan namaz",
            "Oruç tutamayan kişinin fakiri doyuracak kadar verdiği bedel",
            "Sahur vakti yenen yemek"
        ],
        correctAnswer: 1,
        explanation: "Fidye, oruç tutamayan kişilerin fakir bir insanı doyuracak kadar verdiği bedeldir."
    },
    {
        question: "Aşağıdakilerden hangisi farz oruçtur?",
        options: [
            "Arefe günü orucu",
            "Ramazan orucu",
            "Pazartesi ve perşembe günleri orucu"
        ],
        correctAnswer: 1,
        explanation: "Ramazan orucu farz oruçtur. Allah tarafından emredilmiştir. Diğerleri ise sünnet oruçlardır."
    },
    {
        question: "Kaza orucu nedir?",
        options: [
            "Tutulamayan Ramazan oruçlarının daha sonra tutulması",
            "Ramazan ayında tutulan oruç",
            "Her gün tutulan oruç"
        ],
        correctAnswer: 0,
        explanation: "Kaza orucu, çeşitli mazeretlerle tutulamayan Ramazan oruçlarının daha sonra tutulmasıdır."
    },
    {
        question: "Oruç tutarken nelere dikkat edilmelidir?",
        options: [
            "Sadece yemek yememek yeterlidir",
            "Kötü sözden, kavga ve tartışmadan uzak durmak; sabırlı ve saygılı olmak",
            "Sadece namaz kılmak yeterlidir"
        ],
        correctAnswer: 1,
        explanation: "Oruç tutarken sadece yemek içmekten kaçınmak yetmez. Aynı zamanda kötü sözden, kavga ve tartışmadan uzak durmalı, sabırlı ve saygılı olmalıyız."
    },
    {
        question: "Aşağıdakilerden hangisi orucu bozan bir durumdur?",
        options: [
            "Unutarak yemek yemek",
            "Bilerek yemek içmek",
            "Diş fırçalamak"
        ],
        correctAnswer: 1,
        explanation: "Bilerek yemek içmek orucu bozar. Unutarak yemek yemek ise orucu bozmaz, ancak hatırlayınca bırakmak gerekir."
    },
    {
        question: "Aşağıdakilerden hangisi orucu bozmaz?",
        options: [
            "Bilerek su içmek",
            "Unutarak yiyip içmek ama hatırlayınca bırakmak",
            "Güneş battı sanıp erken iftar etmek"
        ],
        correctAnswer: 1,
        explanation: "Unutarak yiyip içmek orucu bozmaz. Ancak hatırlayınca derhal bırakmak gerekir. Bu durum mazerettir."
    }
];

// Yıldız Oluştur
function createStars() {
    const starsContainer = document.getElementById('starsContainer');
    for (let i = 0; i < 50; i++) {
        const star = document.createElement('div');
        star.className = 'star';
        star.style.top = Math.random() * 100 + '%';
        star.style.left = Math.random() * 100 + '%';
        star.style.animationDelay = Math.random() * 2 + 's';
        starsContainer.appendChild(star);
    }
}

// Sayfa Geçişleri
function goToStage(stage) {
    document.getElementById('mainPage').classList.add('hidden');
    document.getElementById('etap1Page').classList.add('hidden');
    document.getElementById('etap2Page').classList.add('hidden');
    document.getElementById('etap3Page').classList.add('hidden');

    if (stage === 'etap1') {
        document.getElementById('etap1Page').classList.remove('hidden');
        initMemoryGame();
    } else if (stage === 'etap2') {
        document.getElementById('etap2Page').classList.remove('hidden');
        initMatchingGame();
    } else if (stage === 'etap3') {
        document.getElementById('etap3Page').classList.remove('hidden');
        initQuiz();
    }
}

function goToMain() {
    document.getElementById('mainPage').classList.remove('hidden');
    document.getElementById('etap1Page').classList.add('hidden');
    document.getElementById('etap2Page').classList.add('hidden');
    document.getElementById('etap3Page').classList.add('hidden');
}

// ETAP 1: Memory Match
let memoryCards = [];
let flippedCards = [];
let matchedPairs = [];
let isChecking = false;

function initMemoryGame() {
    memoryCards = [];
    flippedCards = [];
    matchedPairs = [];
    isChecking = false;

    concepts.forEach(concept => {
        memoryCards.push({
            id: `term-${concept.id}`,
            content: concept.term,
            pairId: concept.id,
            type: 'term'
        });
        memoryCards.push({
            id: `def-${concept.id}`,
            content: concept.definition,
            pairId: concept.id,
            type: 'definition'
        });
    });

    memoryCards.sort(() => Math.random() - 0.5);
    renderMemoryGame();
}

function renderMemoryGame() {
    const grid = document.getElementById('memoryGrid');
    grid.innerHTML = '';

    memoryCards.forEach(card => {
        const cardEl = document.createElement('div');
        cardEl.className = 'memory-card';
        cardEl.id = card.id;

        if (flippedCards.includes(card.id) || matchedPairs.includes(card.id)) {
            cardEl.classList.add('flipped');
            if (matchedPairs.includes(card.id)) {
                cardEl.classList.add('matched');
            }
            const front = document.createElement('div');
            front.className = 'card-front';
            if (card.type === 'term') front.classList.add('term');
            front.textContent = card.content;
            cardEl.appendChild(front);
        } else {
            const back = document.createElement('div');
            back.className = 'card-back';
            back.textContent = '?';
            cardEl.appendChild(back);
        }

        cardEl.onclick = () => handleMemoryCardClick(card.id);
        grid.appendChild(cardEl);
    });
}

function handleMemoryCardClick(cardId) {
    if (isChecking || flippedCards.includes(cardId) || matchedPairs.includes(cardId)) {
        return;
    }

    flippedCards.push(cardId);
    renderMemoryGame();

    if (flippedCards.length === 2) {
        isChecking = true;
        checkMemoryMatch();
    }
}

function checkMemoryMatch() {
    const [first, second] = flippedCards;
    const firstCard = memoryCards.find(c => c.id === first);
    const secondCard = memoryCards.find(c => c.id === second);

    if (firstCard.pairId === secondCard.pairId) {
        showMessage('etap1Message', 'Doğru eşleşme!', 'success');
        matchedPairs.push(first, second);

        setTimeout(() => {
            flippedCards = [];
            isChecking = false;
            hideMessage('etap1Message');
            renderMemoryGame();

            if (matchedPairs.length === memoryCards.length) {
                showMessage('etap1Message', 'Harika! Memory Match tamamlandı!', 'success');
            }
        }, 1000);
    } else {
        setTimeout(() => {
            flippedCards = [];
            isChecking = false;
            renderMemoryGame();
        }, 1000);
    }
}

function resetMemoryGame() {
    initMemoryGame();
    hideMessage('etap1Message');
}

// ETAP 2: Matching Game
let selectedTerm = null;
let selectedDefinition = null;
let matches = [];
let shuffledDefs = [];

function initMatchingGame() {
    selectedTerm = null;
    selectedDefinition = null;
    matches = [];
    shuffledDefs = [...matchingConcepts].sort(() => Math.random() - 0.5);
    renderMatchingGame();
}

function renderMatchingGame() {
    const termsCol = document.getElementById('termsColumn');
    const defsCol = document.getElementById('definitionsColumn');

    termsCol.innerHTML = '';
    defsCol.innerHTML = '';

    matchingConcepts.forEach(concept => {
        const termEl = document.createElement('div');
        termEl.className = 'matching-item left';
        const isMatched = matches.find(m => m.termId === concept.id);
        const isSelected = selectedTerm === concept.id;

        if (isMatched) termEl.classList.add('matched');
        if (isSelected) termEl.classList.add('selected');

        termEl.innerHTML = `
            <div class="text">${concept.term}</div>
            ${isMatched ? '<span class="check-icon">✓</span>' : ''}
        `;

        termEl.onclick = () => handleTermClick(concept.id);
        termsCol.appendChild(termEl);
    });

    shuffledDefs.forEach(concept => {
        const defEl = document.createElement('div');
        defEl.className = 'matching-item right';
        const isMatched = matches.find(m => m.definitionId === concept.id);
        const isSelected = selectedDefinition === concept.id;

        if (isMatched) defEl.classList.add('matched');
        if (isSelected) defEl.classList.add('selected');

        defEl.innerHTML = `
            <div class="text">${concept.definition}</div>
            ${isMatched ? '<span class="check-icon">✓</span>' : ''}
        `;

        defEl.onclick = () => handleDefinitionClick(concept.id);
        defsCol.appendChild(defEl);
    });

    document.getElementById('matchingProgress').textContent = `İlerleme: ${matches.length} / ${matchingConcepts.length}`;
}

function handleTermClick(conceptId) {
    if (matches.find(m => m.termId === conceptId)) return;
    selectedTerm = conceptId;
    hideMessage('etap2Message');
    renderMatchingGame();
}

function handleDefinitionClick(conceptId) {
    if (matches.find(m => m.definitionId === conceptId)) return;
    selectedDefinition = conceptId;
    hideMessage('etap2Message');

    if (selectedTerm !== null) {
        checkMatch(selectedTerm, conceptId);
    } else {
        renderMatchingGame();
    }
}

function checkMatch(termId, defId) {
    if (termId === defId) {
        matches.push({ termId, definitionId: defId });
        selectedTerm = null;
        selectedDefinition = null;
        renderMatchingGame();

        if (matches.length === matchingConcepts.length) {
            showMessage('etap2Message', 'Bulmaca Tamamlandı!', 'success');
        }
    } else {
        showMessage('etap2Message', 'Tekrar dene!', 'error');
        setTimeout(() => {
            selectedTerm = null;
            selectedDefinition = null;
            hideMessage('etap2Message');
            renderMatchingGame();
        }, 1500);
    }
}

function resetMatchingGame() {
    initMatchingGame();
    hideMessage('etap2Message');
}

// ETAP 3: Quiz
let currentQuestion = 0;
let score = 0;
let selectedAnswer = null;
let showResult = false;
let quizCompleted = false;

function initQuiz() {
    currentQuestion = 0;
    score = 0;
    selectedAnswer = null;
    showResult = false;
    quizCompleted = false;
    renderQuiz();
}

function renderQuiz() {
    if (quizCompleted) {
        renderQuizResult();
        return;
    }

    const question = quizQuestions[currentQuestion];
    const progress = ((currentQuestion + 1) / quizQuestions.length) * 100;

    document.getElementById('quizProgress').textContent = `Soru ${currentQuestion + 1} / ${quizQuestions.length}`;
    document.getElementById('progressFill').style.width = progress + '%';

    const content = document.getElementById('quizContent');
    content.innerHTML = `
        <div class="question-card">
            <div class="question-text">${question.question}</div>
            <div>
                ${question.options.map((option, index) => {
                    let btnClass = 'option-button';
                    if (showResult) {
                        if (index === question.correctAnswer) {
                            btnClass += ' correct';
                        } else if (index === selectedAnswer) {
                            btnClass += ' wrong';
                        }
                    }
                    return `
                        <button class="${btnClass}" 
                            onclick="handleAnswerClick(${index})"
                            ${selectedAnswer !== null ? 'disabled' : ''}>
                            <strong>${String.fromCharCode(65 + index)})</strong> ${option}
                        </button>
                    `;
                }).join('')}
            </div>
        </div>

        ${showResult ? `
            <div class="result-message ${selectedAnswer === question.correctAnswer ? 'correct' : 'wrong'}">
                <h4>${selectedAnswer === question.correctAnswer ? 'Tebrikler, doğru cevap!' : `Bu kez olmadı. Doğru cevap: ${String.fromCharCode(65 + question.correctAnswer)})`}</h4>
                <p>${question.explanation}</p>
            </div>
        ` : ''}
    `;

    const controls = document.getElementById('quizControls');
    controls.innerHTML = '';

    if (showResult) {
        const nextBtn = document.createElement('button');
        nextBtn.className = 'btn btn-primary';
        nextBtn.textContent = currentQuestion < quizQuestions.length - 1 ? 'Sonraki Soru' : 'Sonucu Gör';
        nextBtn.onclick = handleNextQuestion;
        controls.appendChild(nextBtn);
    }

    const homeBtn = document.createElement('button');
    homeBtn.className = 'btn btn-outline';
    homeBtn.innerHTML = '🏠 Etap Seçe Dön';
    homeBtn.onclick = goToMain;
    controls.appendChild(homeBtn);

    document.getElementById('scoreDisplay').textContent = 
        `Mevcut Puan: ${score} / ${currentQuestion + (showResult ? 1 : 0)}`;
}

function handleAnswerClick(answerIndex) {
    if (selectedAnswer !== null) return;

    selectedAnswer = answerIndex;
    showResult = true;

    if (answerIndex === quizQuestions[currentQuestion].correctAnswer) {
        score++;
    }

    renderQuiz();
}

function handleNextQuestion() {
    if (currentQuestion < quizQuestions.length - 1) {
        currentQuestion++;
        selectedAnswer = null;
        showResult = false;
        renderQuiz();
    } else {
        quizCompleted = true;
        renderQuizResult();
    }
}

function renderQuizResult() {
    const percentage = Math.round((score / quizQuestions.length) * 100);
    let feedback;

    if (percentage >= 80) {
        feedback = {
            title: 'Mükemmel!',
            message: 'Ramazan ve oruç konusunda çok başarılısın! Bilgilerin harika!'
        };
    } else if (percentage >= 50) {
        feedback = {
            title: 'İyi!',
            message: 'Güzel bir performans sergledin. Biraz daha çalışırsan mükemmel olacaksın!'
        };
    } else {
        feedback = {
            title: 'Devam Et!',
            message: 'Daha fazla çalışman gerekiyor. Konuları tekrar gözden geçir ve tekrar dene!'
        };
    }

    document.getElementById('quizContent').innerHTML = `
        <div class="quiz-result">
            <h2>${feedback.title}</h2>
            <div class="score">${score} / ${quizQuestions.length}</div>
            <p>${feedback.message}</p>
            <p class="percentage">Doğru Cevap Oranı: %${percentage}</p>
        </div>
    `;

    const controls = document.getElementById('quizControls');
    controls.innerHTML = `
        <button class="btn btn-primary" onclick="initQuiz()">
            🔄 Tekrar Oyna
        </button>
        <button class="btn btn-outline" onclick="goToMain()">
            🏠 Etap Seçe Dön
        </button>
    `;

    document.getElementById('scoreDisplay').textContent = '';
}

// Yardımcı Fonksiyonlar
function showMessage(elementId, text, type) {
    const el = document.getElementById(elementId);
    el.innerHTML = `<div class="message-box message-${type}">${text}</div>`;
}

function hideMessage(elementId) {
    document.getElementById(elementId).innerHTML = '';
}

// Sayfa Yüklendiğinde
window.onload = function() {
    createStars();
};
