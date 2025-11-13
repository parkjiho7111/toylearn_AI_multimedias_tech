## 프롬프트 유형과 선택 이유
```
코딩 및 프로토타입 생성 / 시각화 능력을 극대화하기 위한 프롬프트 유형 선택

1.지시형 (Instructional Type)
선택 이유: 가장 기본적이고 강력한 유형입니다. AI에게 "HTML, CSS, JS 코드를 생성하라"고 직접적이고 명확하게 '명령'해야 합니다. 모호한 설명이 아닌, '실행 가능한(Runnable)' 결과물을 요구하는 코딩 프롬프트의 핵심입니다.

2.제약조건형 (Constraint Type)
선택 이유: 코딩은 '제약'의 연속입니다. 이 유형은 AI가 헛다리를 짚지 않도록 '전장'을 한정합니다. "단일 HTML 파일로 만들 것", "**Vanilla JS(프레임워크 없음)**를 사용할 것", "다크 모드를 기본으로 할 것" 등 구체적인 제약은 오후 4시 회의에서 즉각 수정해야 하는 프로토타입의 복잡도를 제어하는 핵심 전술입니다.

3.재구성/번역형 (Reconstruction/Translation Type)
선택 이유: 이 챌린지의 핵심 훈련 초점과 정확히 일치합니다. 우리는 AI에게 '추상적인 UI/UX 요구사항'을 '구조화된 코드'라는 완전히 다른 언어로 **'번역(Translate)'**하도록 요청해야 합니다. "타임스탬프 댓글 기능", "데이터 밀집형 테이블"과 같은 자연어 기획을 실제 <div class="comment-timeline"> 같은 코드로 '재구성'하는 능력입니다.

4.역할부여형 (Role-Playing Type)
선택 이유: 그냥 작동하는 코드가 아니라, "회의 중 즉석 수정이 가능한 깨끗한 코드"가 필요합니다. AI에게 "당신은 10년 차 시니어 프론트엔드 개발자이며, 빠르고 효율적인 프로토타이핑 전문가다. 당신의 코드는 모듈화되어 있고 주석이 명확하다"라는 역할을 부여해야 합니다. 이는 코드의 '품질(Quality)'을 보장하는 핵심 지시입니다
```

## 작성 위해 추가로 필요한 필수 요건 3가지
제시된 시나리오만으로는 이해관계자들을 만족시킬 '결정적인' 프로토타입을 만들기에 정보가 부족합니다. 완벽한 문제 해결 프롬프트를 작성하기 위해 다음 3가지 요건이 추가로 필요함


1.핵심 레이아웃 구획 (Key Layout Structure)
필요 이유: "직관적 UI(기획팀)", "데이터 밀집형(운영팀)" 요구는 충돌합니다. AI에게 이 충돌을 해결할 최소한의 와이어프레임을 지시해야 합니다.

2.모의 데이터 구조 (Mock Data Structure)
필요 이유: '데이터 밀집형 테이블'과 '타임스탬프 댓글'은 '데이터' 없이는 시각화할 수 없습니다. AI가 실제 작동하는 것처럼 보이게 만들 **샘플 데이터(JSON 형태)**가 필요합니다.

3.구체적인 기술 스택 한정 (Specific Tech Stack)
필요 이유: "HTML/CSS/JS"는 너무 광범위합니다. '즉석 수정'이라는 목표를 달성하려면, 무거운 프레임워크(React, Vue)를 배제하고 순수 Vanilla JS와 CSS로 한정하거나, 혹은 Bootstrap/Tailwind 같은 특정 CSS 프레임워크 사용 여부를 명시해야 AI가 가장 효율적인 코드를 생성합니다.

## 문제해결 프롬프트

```
너는 '네오스트림'의 10년 차 시니어 프론트엔드 개발자이자, 긴급한 이해관계자 회의를 위한 신속한 프로토타이핑(Rapid Prototyping) 전문가다.

오늘 오후 4시, 기획(직관적 UI), 디자인(다크 모드), 운영(데이터 밀집형 테이블)팀의 상충되는 요구로 지연되는 '사내 영상 리뷰 대시보드' 프로젝트 회의가 있다. 말로만은 설득이 불가능하다.
아래 [핵심 요구사항]과 [구조]를 완벽하게 반영하여, 회의에서 즉시 보여주고 수정할 수 있는 **단일 HTML 페이지 프로토타입 코드(HTML, CSS, JS 포함)**를 즉시 생성하라.


단일 파일: 모든 HTML, CSS, JavaScript 코드를 하나의 .html 파일 안에 포함시켜라. (<style> 태그와 <script> 태그를 내부에 사용할 것)
라이브러리 금지: 회의 중 즉각적인 수정과 쉬운 이해를 위해, 어떠한 외부 라이브러리(jQuery, React, Vue, Bootstrap 등)도 사용하지 말고, 순수 Vanilla JavaScript와 CSS로만 구현하라.
코드 품질: JavaScript 코드는 즉석에서 기능을 수정하기 쉽도록 **모듈화(함수 분리)**하고, CSS는 각 섹션별로 명확하게 주석을 달아라.
[UI/UX 요구사항 (재구성/번역형)]
디자인 (디자인팀 요구):
[필수] 전체 페이지는 **'트렌디한 다크 모드'**를 기본 테마로 적용하라. (검은색/어두운 회색 배경, 흰색/밝은 회색 텍스트)
레이아웃 (기획/운영팀 요구 조율):
[필수] '2단 컬럼' 레이아웃을 사용한다.
왼쪽 영역 (너비 60%): '영상 리뷰'를 위한 직관적 UI.
(상단) '영상 플레이어 영역': <video> 태그를 사용한 샘플 비디오 플레이스홀더.
(하단) '타임스탬프 댓글 기능':
댓글 입력창 ([01:30] 댓글 내용 입력...)
댓글 리스트 (타임스탬프를 클릭하면 해당 영상 시간으로 이동하는 척하는 기능 구현)
오른쪽 영역 (너비 40%): '데이터 밀집형' UI.
(상단) '승인/반려 버튼': 'Approve'(초록색), 'Reject'(빨간색) 버튼 2개.
(하단) '리뷰 영상 목록 테이블': [모의 데이터]를 사용한 데이터 테이블. (컬럼: ID, 영상 제목, 담당자, 상태)
기능 (JavaScript):
[필수] 타임스탬프 댓글 리스트와 영상 목록 테이블은 아래 [모의 데이터]를 기반으로 동적으로 생성(DOM-based)되어야 한다.
[필수] '승인/반려' 버튼 클릭 시 alert으로 "승인됨", "반려됨"을 표시하라.
[선택] 댓글 입력창에 내용을 넣고 '입력' 버튼을 누르면 댓글 리스트 하단에 새 댓글이 추가되도록 하라.

이 문제해결 프롬프트를 실행하고, 구글의 canvas 기능을 이용한 결과물 만들어줘.

```

## 프롬프트실행결과


<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>영상 리뷰 대시보드 (프로토타입)</title>
    <style>
        /* --- [CSS] 10년차 개발자의 빠르고 명확한 스타일시트 --- */
        
        /* 1. 기본 및 다크 모드 (디자인팀 요구) */
        :root {
            --bg-dark: #1a1b1e;
            --bg-light: #2c2d30;
            --text-primary: #f0f0f0;
            --text-secondary: #a9a9a9;
            --border-color: #444;
            --accent-green: #28a745;
            --accent-red: #dc3545;
            --accent-blue: #007bff;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
                Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-primary);
            margin: 0;
            padding: 20px;
            font-size: 14px;
        }

        /* 2. 레이아웃 (기획/운영팀 조율) */
        .container {
            display: flex;
            flex-wrap: wrap; /* 모바일 반응형을 위해 추가 */
            gap: 20px;
            max-width: 1400px;
            margin: 0 auto;
        }

        .review-panel {
            flex: 3; /* 너비 비율 (60%) */
            min-width: 400px; /* 최소 너비 */
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .sidebar {
            flex: 2; /* 너비 비율 (40%) */
            min-width: 300px; /* 최소 너비 */
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .widget {
            background-color: var(--bg-light);
            border-radius: 8px;
            border: 1px solid var(--border-color);
            padding: 20px;
        }

        .widget-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-top: 0;
            margin-bottom: 15px;
            color: var(--text-primary);
        }

        /* 3. 왼쪽 영역: 영상 플레이어 (직관적 UI) */
        .video-player video {
            width: 100%;
            height: auto; /* 비율 유지 */
            border-radius: 4px;
            background-color: #000;
        }

        /* 4. 왼쪽 영역: 타임스탬프 댓글 (직관적 UI) */
        #comment-list {
            max-height: 300px;
            overflow-y: auto;
            margin-bottom: 15px;
        }

        .comment {
            margin-bottom: 15px;
            padding-bottom: 10px;
            border-bottom: 1px solid var(--border-color);
        }

        .comment:last-child {
            border-bottom: none;
            margin-bottom: 0;
        }

        .comment-meta {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }

        .comment-user {
            font-weight: 600;
            color: var(--text-primary);
        }

        .comment-time {
            font-weight: 600;
            color: var(--accent-blue);
            cursor: pointer;
            padding: 2px 6px;
            border-radius: 4px;
        }
         .comment-time:hover {
            background-color: var(--border-color);
         }

        .comment-text {
            color: var(--text-secondary);
            line-height: 1.5;
            word-break: break-all; /* 긴 텍스트 줄바꿈 */
        }

        #comment-form {
            display: flex;
            flex-wrap: wrap; /* 모바일 반응형 */
            gap: 10px;
        }

        #comment-form input {
            flex: 1;
            padding: 10px;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            background-color: var(--bg-dark);
            color: var(--text-primary);
            min-width: 100px; /* 최소 너비 */
        }
        
        #comment-form input[type="text"]:first-child {
            flex-grow: 1;
        }
        #comment-form input[type="text"]:nth-child(2) {
            flex-grow: 3;
        }


        #comment-form button {
            padding: 10px 15px;
            flex-shrink: 0; /* 버튼 크기 유지 */
        }

        /* 5. 오른쪽 영역: 승인/반려 버튼 */
        .action-buttons {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .btn {
            padding: 12px;
            border: none;
            border-radius: 4px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: opacity 0.2s;
        }
        .btn:hover {
            opacity: 0.8;
        }
        .btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .btn-approve {
            background-color: var(--accent-green);
            color: white;
        }

        .btn-reject {
            background-color: var(--accent-red);
            color: white;
        }
        
        .btn-submit {
             background-color: var(--accent-blue);
             color: white;
        }
        
        /* 6. 오른쪽 영역: 리뷰 목록 (데이터 밀집형) */
        .video-list {
            overflow-x: auto; /* 테이블이 넘칠 경우 스크롤 */
        }
        .video-list table {
            width: 100%;
            border-collapse: collapse;
            text-align: left;
            min-width: 400px; /* 최소 너비 보장 */
        }

        .video-list th,
        .video-list td {
            padding: 12px 15px;
            border-bottom: 1px solid var(--border-color);
            white-space: nowrap; /* 테이블 내용 줄바꿈 방지 */
        }

        .video-list th {
            font-size: 0.9rem;
            color: var(--text-secondary);
            text-transform: uppercase;
        }

        .video-list td {
            color: var(--text-primary);
        }

        .video-list tbody tr:last-child td {
            border-bottom: none;
        }
        
        .video-list tbody tr:hover {
            background-color: var(--bg-dark);
        }

        /* 상태값 배지 스타일 */
        .status {
            padding: 4px 8px;
            border-radius: 12px;
            font-size: 0.8rem;
            font-weight: 600;
            text-transform: uppercase;
        }
        .status-Pending {
            background-color: #ffc107;
            color: #333;
        }
        .status-Approved {
            background-color: var(--accent-green);
            color: white;
        }
        .status-Rejected {
            background-color: var(--accent-red);
            color: white;
        }
        
        /* 알림 메시지 (alert 대체) */
        #alert-message {
            display: none; /* 평소엔 숨김 */
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            padding: 12px 25px;
            border-radius: 6px;
            font-weight: 600;
            color: white;
            z-index: 1000;
            font-size: 1rem;
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
        }
        #alert-message.success {
            background-color: var(--accent-green);
        }
        #alert-message.error {
            background-color: var(--accent-red);
        }


    </style>
</head>
<body>
    <!-- alert() 대체를 위한 알림 메시지 영역 -->
    <div id="alert-message"></div>

    <div class="container">
        <!-- ========================== -->
        <!--     왼쪽 영역 (60%)         -->
        <!-- ========================== -->
        <div class="review-panel">
            
            <!-- 1. 영상 플레이어 -->
            <div class="widget">
                <h2 class="widget-title" id="video-title">신규 CF (A안)</h2>
                <div class="video-player">
                    <!-- 실제 영상 대신 플레이스홀더 사용 -->
                    <video controls muted poster="https://placehold.co/1600x900/000000/cccccc?text=Video+Player" id="main-video">
                        <!-- <source src="path/to/video.mp4" type="video/mp4"> -->
                        브라우저가 video 태그를 지원하지 않습니다.
                    </video>
                </div>
            </div>

            <!-- 2. 타임스탬프 댓글 -->
            <div class="widget">
                <h2 class="widget-title">타임스탬프 리뷰</h2>
                
                <!-- 댓글 리스트 (JS로 채워짐) -->
                <div id="comment-list">
                    <!-- JS로 채워짐 -->
                </div>
                
                <!-- 댓글 입력 폼 -->
                <form id="comment-form">
                    <input type="text" id="comment-time-input" placeholder="시간 (예: 01:30)">
                    <input type="text" id="comment-text-input" placeholder="리뷰 코멘트를 입력하세요..." required>
                    <button type="submit" class="btn btn-submit">입력</button>
                </form>
            </div>

        </div>

        <!-- ========================== -->
        <!--     오른쪽 영역 (40%)       -->
        <!-- ========================== -->
        <div class="sidebar">

            <!-- 3. 승인/반려 버튼 -->
            <div class="widget">
                <h2 class="widget-title">리뷰 상태 변경</h2>
                <div class="action-buttons">
                    <button class="btn btn-approve" id="approve-btn">✔ Approve</button>
                    <button class="btn btn-reject" id="reject-btn">✖ Reject</button>
                </div>
            </div>
            
            <!-- 4. 리뷰 영상 목록 -->
            <div class="widget video-list">
                <h2 class="widget-title">전체 리뷰 목록</h2>
                <table>
                    <thead>
                        <tr>
                            <th>ID</th>
                            <th>영상 제목</th>
                            <th>담당자</th>
                            <th>상태</th>
                        </tr>
                    </thead>
                    <!-- JS로 채워질 테이블 본문 -->
                    <tbody id="video-list-body">
                        <!-- JS로 채워짐 -->
                    </tbody>
                </table>
            </div>

        </div>
    </div>

    <script>
        // --- [JavaScript] 10년차 개발자의 모듈화된 프로토타입 스크립트 ---

        // 1. 모의 데이터 (Prompt에서 제공)
        const videoList = [
            { id: 'v001', title: '신규 CF (A안)', manager: '김기획', status: 'Pending' },
            { id: 'v002', title: '메이킹 필름 (B안)', manager: '이운영', status: 'Approved' },
            { id: 'v003', title: 'SNS 숏폼 (ver 1.1)', manager: '박디자인', status: 'Rejected' },
            { id: 'v004', title: '인트로 영상 (최종)', manager: '김기획', status: 'Pending' }
        ];

        const comments = [
            { time: '00:15', user: '박디자인', text: '로고 등장 타이밍 0.5초 당겨주세요.' },
            { time: '01:30', user: '김기획', text: '이 부분 나레이션을 B안으로 교체 검토.' },
            { time: '02:45', user: '이운영', text: '데이터 고지 화면, 법적 문구 추가 필요.' }
        ];

        let currentVideoTitle = videoList[0].title; // 현재 선택된 비디오 제목

        // 2. DOM 요소 캐시
        const videoListBody = document.getElementById('video-list-body');
        const commentList = document.getElementById('comment-list');
        const approveBtn = document.getElementById('approve-btn');
        const rejectBtn = document.getElementById('reject-btn');
        const commentForm = document.getElementById('comment-form');
        const mainVideo = document.getElementById('main-video');
        const videoTitleEl = document.getElementById('video-title');
        const alertMessageEl = document.getElementById('alert-message');
        
        let alertTimeout = null; // 알림 메시지 타임아웃 ID

        /**
         * [기능] 영상 목록 테이블을 동적으로 생성 (운영팀 요구)
         */
        function loadVideoList() {
            videoListBody.innerHTML = ''; // 기존 내용 초기화
            videoList.forEach(video => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${video.id}</td>
                    <td>${video.title}</td>
                    <td>${video.manager}</td>
                    <td><span class="status status-${video.status}">${video.status}</span></td>
                `;
                // (회의 중 즉석 수정 대비) 테이블 행 클릭 시 제목 변경
                row.style.cursor = 'pointer';
                row.addEventListener('click', () => {
                    currentVideoTitle = video.title;
                    videoTitleEl.textContent = video.title;
                    showAppAlert(`'${video.title}' 영상을 선택했습니다.`, 'success');
                });
                videoListBody.appendChild(row);
            });
        }

        /**
         * [기능] 댓글 목록을 동적으로 생성 (기획팀 요구)
         */
        function loadComments() {
            commentList.innerHTML = ''; // 기존 내용 초기화
            comments.forEach(comment => {
                const commentEl = createCommentElement(comment);
                commentList.appendChild(commentEl);
            });
        }

        /**
         * [헬퍼] 개별 댓글 DOM 요소를 생성
         */
        function createCommentElement(comment) {
            const el = document.createElement('div');
            el.className = 'comment';
            
            // 시간(time)을 초(seconds)로 변환 (예: '01:30' -> 90)
            let seconds = 0;
            if (comment.time.includes(':')) {
                const timeParts = comment.time.split(':');
                seconds = (+timeParts[0] * 60) + (+timeParts[1]);
            } else {
                seconds = +comment.time; // 숫자만 있을 경우
            }

            el.innerHTML = `
                <div class="comment-meta">
                    <span class="comment-user">${comment.user}</span>
                    <span class="comment-time" data-time="${seconds}">${comment.time}</span>
                </div>
                <div class="comment-text">${escapeHTML(comment.text)}</div>
            `;

            // 타임스탬프 클릭 이벤트 (프로토타입 기능)
            el.querySelector('.comment-time').addEventListener('click', () => {
                const timeInSeconds = el.querySelector('.comment-time').dataset.time;
                mainVideo.currentTime = timeInSeconds;
                mainVideo.play();
                console.log(`영상 시간을 ${timeInSeconds}초로 이동 (프로토타입)`);
            });

            return el;
        }

        /**
         * [기능] 새 댓글 폼 제출 처리 (선택 사항)
         */
        function handleCommentSubmit(event) {
            event.preventDefault(); // 폼 기본 제출 방지

            const timeInput = document.getElementById('comment-time-input');
            const textInput = document.getElementById('comment-text-input');

            if (!textInput.value) {
                showAppAlert('댓글 내용을 입력해야 합니다.', 'error');
                return;
            }

            const newComment = {
                time: timeInput.value || '00:00', // 기본값
                user: '개발자 (나)', // 현재 사용자 (하드코딩)
                text: textInput.value
            };

            // 새 댓글을 DOM에 추가
            const newCommentEl = createCommentElement(newComment);
            commentList.appendChild(newCommentEl);
            commentList.scrollTop = commentList.scrollHeight; // 스크롤을 맨 아래로
            
            // 폼 초기화
            timeInput.value = '';
            textInput.value = '';
        }
        
        /**
         * [기능] alert()를 대체하는 커스텀 알림 메시지
         * @param {string} message - 표시할 메시지
         * @param {'success' | 'error'} type - 알림 타입
         */
        function showAppAlert(message, type = 'success') {
             // 기존 타임아웃이 있다면 취소
            if (alertTimeout) {
                clearTimeout(alertTimeout);
            }
            
            alertMessageEl.textContent = message;
            alertMessageEl.className = type; // 'success' 또는 'error' 클래스 적용
            alertMessageEl.style.display = 'block';

            // 3초 후에 자동으로 사라짐
            alertTimeout = setTimeout(() => {
                alertMessageEl.style.display = 'none';
            }, 3000);
        }
        
        /**
         * [헬퍼] XSS 방지를 위한 간단한 HTML 이스케이프 함수
         */
        function escapeHTML(str) {
            return str.replace(/[&<>"']/g, function(match) {
                return {
                    '&': '&amp;',
                    '<': '&lt;',
                    '>': '&gt;',
                    '"': '&quot;',
                    "'": '&#39;'
                }[match];
            });
        }


        /**
         * [기능] 모든 이벤트 리스너를 설정
         */
        function setupEventListeners() {
            // 승인/반려 버튼 (커스텀 알림 사용)
            approveBtn.addEventListener('click', () => {
                showAppAlert(`'${currentVideoTitle}' (이)가 [승인] 처리되었습니다.`, 'success');
            });

            rejectBtn.addEventListener('click', () => {
                showAppAlert(`'${currentVideoTitle}' (이)가 [반려] 처리되었습니다.`, 'error');
            });

            // 댓글 폼 제출
            commentForm.addEventListener('submit', handleCommentSubmit);
        }

        /**
         * [실행] DOM이 로드되면 모든 기능을 초기화
         */
        document.addEventListener('DOMContentLoaded', () => {
            console.log("네오스트림 프로토타입 로드 완료. 4시 회의 준비.");
            loadVideoList();
            loadComments();
            setupEventListeners();
        });

    </script>
</body>
</html>
