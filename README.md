Tryout UTBK - Alphateka body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f4f4f4; } .container { max-width: 600px; margin: 50px auto; background: white; padding: 20px; border-radius: 10px; box-shadow: 0 0 10px rgba(0,0,0,0.1); } h1, h2 { text-align: center; } .hidden { display: none; } button { background-color: #4CAF50; color: white; padding: 10px 15px; border: none; border-radius: 5px; cursor: pointer; } button:hover { background-color: #45a049; } input[type="text"] { width: 100%; padding: 10px; margin: 10px 0; border: 1px solid #ccc; border-radius: 5px; } .question { margin: 20px 0; } .timer { font-weight: bold; color: red; text-align: right; } 

Tryout UTBK - Alphateka 

Masukkan nama untuk memulai:

Mulai 

Waktu: 00:00

Selanjutnya 

Tryout Selesai! 

Terima kasih telah mengikuti tryout, .

Hasil kamu akan tersedia dalam 5 hari. Silakan kunjungi kembali nanti.

Lihat Hasil 

Skor Tryout 

const subtests = [ { name: 'Penalaran Umum', time: 30, questions: 3 }, { name: 'Penalaran Kuantitatif', time: 20, questions: 3 }, { name: 'Penalaran Matematika', time: 42.5, questions: 3 }, { name: 'Literasi Bahasa Indonesia', time: 42.5, questions: 3 }, { name: 'Literasi Bahasa Inggris', time: 30, questions: 3 }, { name: 'PPU', time: 15, questions: 3 }, { name: 'PBM', time: 25, questions: 3 }, ]; const questions = { 'Penalaran Umum': ['Soal PU 1', 'Soal PU 2', 'Soal PU 3'], 'Penalaran Kuantitatif': ['Soal PK 1', 'Soal PK 2', 'Soal PK 3'], 'Penalaran Matematika': ['Soal PM 1', 'Soal PM 2', 'Soal PM 3'], 'Literasi Bahasa Indonesia': ['Soal LitIndo 1', 'Soal LitIndo 2', 'Soal LitIndo 3'], 'Literasi Bahasa Inggris': ['Soal LitIng 1', 'Soal LitIng 2', 'Soal LitIng 3'], 'PPU': ['Soal PPU 1', 'Soal PPU 2', 'Soal PPU 3'], 'PBM': ['Soal PBM 1', 'Soal PBM 2', 'Soal PBM 3'] }; const answersKey = { 'Penalaran Umum': ['a', 'b', 'c'], 'Penalaran Kuantitatif': ['a', 'b', 'c'], 'Penalaran Matematika': ['a', 'b', 'c'], 'Literasi Bahasa Indonesia': ['a', 'b', 'c'], 'Literasi Bahasa Inggris': ['a', 'b', 'c'], 'PPU': ['a', 'b', 'c'], 'PBM': ['a', 'b', 'c'] }; let username = ''; let currentSubtest = 0; let currentQuestion = 0; let score = {}; let timeLeft = 0; let timerInterval; function startTryout() { username = document.getElementById('username').value.trim(); if (username === '') return alert('Masukkan nama terlebih dahulu.'); document.getElementById('login-container').classList.add('hidden'); document.getElementById('tryout-container').classList.remove('hidden'); startSubtest(); } function startSubtest() { const subtest = subtests[currentSubtest]; currentQuestion = 0; score[subtest.name] = 0; timeLeft = subtest.time * 60; document.getElementById('subtest-title').innerText = subtest.name; showQuestion(); updateTimer(); timerInterval = setInterval(() => { timeLeft--; updateTimer(); if (timeLeft ${soal}`; document.getElementById('answer').value = ''; } function nextQuestion() { const subtest = subtests[currentSubtest]; const userAnswer = document.getElementById('answer').value.trim().toLowerCase(); const correctAnswer = answersKey[subtest.name][currentQuestion]; if (userAnswer === correctAnswer) score[subtest.name]++; currentQuestion++; if (currentQuestion = FIVE_DAYS) { document.getElementById('score-section').classList.remove('hidden'); const ul = document.getElementById('score-list'); ul.innerHTML = ''; for (let [subtest, nilai] of Object.entries(saved.score)) { ul.innerHTML += `${subtest}: ${nilai} poin`; } } else { alert('Hasil baru bisa dilihat setelah 5 hari.'); } } 
