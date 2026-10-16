const express = require('express');
const path = require('path');
const app = express();

// Render가 지정해 주는 포트 또는 기본값 3000 사용
const PORT = process.env.PORT || 3000;

// public 폴더 안의 파일들(HTML, JSON 등)을 웹에 공개
app.use(express.static(path.join(__dirname, 'public')));

// 기본 주소로 접속했을 때 index.html 보내주기
app.get('/', (req, res) => {
    res.sendFile(path.join(__dirname, 'public', 'index.html'));
});

// 서버 시작
app.listen(PORT, () => {
    console.log(`Server is running on port ${PORT}`);
});
