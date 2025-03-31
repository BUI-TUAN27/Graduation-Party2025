           }

            document.getElementById('invitation-card').style.display = 'none';
            document.getElementById('guess-game').style.display = 'block';
        }

        // Kiểm tra đoán số
        function checkGuess() {
            let guess = document.getElementById('guess').value;
            let luckyNumber = 7;
            let message = '';

            if (parseInt(guess) === luckyNumber) {
                message = '🎉 Chúc mừng bạn, bạn đã đoán đúng! Bạn sẽ được bao anh Tuấn đi uống trà sữa!';
                sendTelegramMessage('🎉 ' + getGuestName() + ' đã đoán đúng số may mắn!');
            } else {
                message = '😞 Rất tiếc, bạn đoán sai rồi. Cảm ơn bạn đã tham gia!';
                sendTelegramMessage('😞 ' + getGuestName() + ' đã đoán sai số may mắn.');
            }

            alert(message);
            setPlayed();  // Lưu trạng thái người chơi đã tham gia
        }
    </script>
</head>
<body>
    <div class="letter-container">
        <img id="letter" class="letter" src="https://i.imgur.com/Q9vSDru.jpeg" alt="Thư mời tốt nghiệp">
        <br>
        <button id="open-button" class="btn" onclick="openInvitation()">📩 Mở Thư</button>
    </div>
    
    <audio id="bg-music" loop>
        <source src="https://raw.githubusercontent.com/BUI-TUAN27/kiyeu/main/nhac/Wxrdie%20-%20M%E1%BB%9CI%20EM%20(ft.%20Mcee%20Blue)%20%5Bprod.%20by%20Machiot%2C%20Marlykid%5D.mp3" type="audio/mpeg">
    </audio>
    
    <div id="invitation-card" class="card">
        <img src="https://i.imgur.com/Q9vSDru.jpeg" alt="Ảnh tiệc tốt nghiệp">
        <h1>🎓 Graduation Party Invitation 🎓</h1>
        <h2>Bùi Trọng Tuấn</h2>
        <p><strong>TO:</strong> <span id="guest-name"></span></p>
        <p class="date">📅 Thời gian: 09:00 - Ngày 06/04/2025</p>
        <p class="date">📍 Địa điểm: Trường THPT Đô Lương 2</p>
        <p><em>Mong bức ảnh thanh xuân của mình có sự góp mặt của bạn!</em></p>
        <div id="countdown" class="countdown"></div>
        <button class="btn" onclick="openGuessGame()">✅ Xác nhận tham gia</button>
    </div>
    
    <div id="guess-game" class="guess-container">
        <h2>🎉 Chúc mừng bạn tham gia trò chơi đoán số 🎉</h2>
        <p>Hãy đoán số may mắn (Số may mắn là 7)</p>
        <input type="number" id="guess" placeholder="Nhập số từ 1 đến 10">
        <button class="btn" onclick="checkGuess()">Đoán số</button>
    </div
