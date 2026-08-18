<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no">
<title>정인하이츠 원룸 체크리스트</title>

<style>
*{
    box-sizing:border-box;
    -webkit-tap-highlight-color:transparent;
}

body{
    margin:0;
    font-family:"Arial Rounded MT Bold","Noto Sans KR",sans-serif;
    background:linear-gradient(180deg,#fff8ee,#f7eee4);
    color:#4d3b2f;
}

.page{display:none;}
.page.active{display:block;}

header{
    text-align:center;
    padding:23px 15px 16px;
}

header h1{
    margin:0;
    font-size:29px;
    font-weight:900;
    color:#76523d;
}

header p{
    margin:7px 0 0;
    font-size:13px;
    color:#a17d66;
}

.building-wrap{
    display:flex;
    justify-content:center;
    padding:5px 15px 20px;
}

.building{
    width:min(430px,94vw);
    background:#fff;
    border:5px solid #6c4937;
    border-radius:18px 18px 12px 12px;
    overflow:hidden;
    box-shadow:0 8px 20px rgba(80,50,30,.16);
}

.floor{
    min-height:105px;
    border-bottom:4px solid #6c4937;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    cursor:pointer;
    transition:.15s;
    text-align:center;
    padding:10px;
}

.floor:last-child{
    border-bottom:none;
}

.floor:active{
    transform:scale(.98);
}

.floor-label{
    font-size:20px;
    font-weight:900;
    margin-bottom:7px;
}

.floor-sub{
    font-size:12px;
    color:#8c7668;
    line-height:1.5;
}

.floor-roof{background:#dcecff;min-height:85px;}
.floor-four{background:#e5f1d9;}
.floor-three{background:#ffeecf;}
.floor-two{background:#ffe5c8;}
.floor-parking{background:#e7e1da;}

.controls{
    max-width:430px;
    margin:0 auto;
    padding:0 15px 20px;
}

.search-box{
    width:100%;
    border:2px solid #e5d3c5;
    border-radius:14px;
    padding:13px;
    outline:none;
    background:white;
    font-size:14px;
}

.search-box:focus{
    border-color:#bd8e6d;
}

.btn-row{
    display:flex;
    gap:8px;
    margin-top:10px;
}

button{
    border:none;
    border-radius:13px;
    padding:12px 15px;
    font-family:inherit;
    font-size:14px;
    font-weight:bold;
    cursor:pointer;
}

.notice-btn{
    flex:1;
    background:#dba87d;
    color:white;
}

.reset-btn{
    background:#eadbd0;
    color:#755848;
}

.alert-box{
    max-width:430px;
    margin:0 auto 15px;
    padding:0 15px;
}

.alert-inner{
    background:#fff0d9;
    border:2px solid #edc28d;
    border-radius:15px;
    padding:13px;
    font-size:13px;
    line-height:1.7;
}

.back-btn{
    display:block;
    width:calc(100% - 30px);
    max-width:430px;
    margin:10px auto;
    background:#7a5947;
    color:white;
}

.room-list{
    max-width:430px;
    margin:0 auto;
    padding:5px 15px 30px;
}

.room-card{
    background:white;
    border-radius:18px;
    margin:10px 0;
    padding:16px;
    box-shadow:0 4px 13px rgba(70,45,30,.1);
    border:2px solid #eadbd0;
}

.room-top{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:10px;
}

.room-number{
    font-size:21px;
    font-weight:900;
    color:#654633;
}

.room-name{
    margin-top:5px;
    color:#9a7966;
    font-size:14px;
}

.room-status{
    font-size:11px;
    padding:5px 8px;
    border-radius:20px;
    background:#eee;
    white-space:nowrap;
}

.status-good{
    background:#dff1dc;
    color:#3d7435;
}

.status-warning{
    background:#fff0c7;
    color:#916c00;
}

.status-danger{
    background:#ffdada;
    color:#9c3333;
}

.room-info{
    margin-top:13px;
    font-size:13px;
    line-height:1.8;
    color:#69584e;
}

.room-actions{
    display:flex;
    gap:7px;
    margin-top:12px;
}

.edit-btn{
    flex:1;
    background:#e8c7ad;
    color:#654633;
}

.clear-btn{
    background:#eee5df;
    color:#795f51;
}

.alarm-info{
    margin-top:8px;
    padding:8px;
    background:#fff7e9;
    border-radius:10px;
    font-size:12px;
    color:#80644e;
}

.modal-bg{
    display:none;
    position:fixed;
    z-index:1000;
    inset:0;
    background:rgba(45,30,20,.45);
    padding:20px;
    align-items:center;
    justify-content:center;
}

.modal-bg.show{
    display:flex;
}

.modal{
    width:min(430px,100%);
    max-height:92vh;
    overflow-y:auto;
    background:white;
    border-radius:23px;
    padding:22px;
    box-shadow:0 15px 40px rgba(0,0,0,.2);
}

.modal h2{
    margin:0 0 17px;
    color:#654633;
}

.modal h3{
    margin:18px 0 13px;
    color:#76523d;
}

.modal hr{
    border:0;
    border-top:1px solid #eadbd0;
    margin:18px 0;
}

.form-group{
    margin-bottom:13px;
}

.form-group label{
    display:block;
    font-size:13px;
    font-weight:bold;
    margin-bottom:6px;
    color:#755848;
}

.form-group input,
.form-group select{
    width:100%;
    padding:12px;
    border:2px solid #e7d8ce;
    border-radius:12px;
    outline:none;
    font-size:15px;
    background:white;
}

.form-group input:focus,
.form-group select:focus{
    border-color:#c39779;
}

.modal-buttons{
    display:flex;
    gap:8px;
    margin-top:18px;
}

.save-btn{
    flex:1;
    background:#7a5947;
    color:white;
}

.cancel-btn{
    flex:1;
    background:#eee5df;
    color:#705a4d;
}

.delete-btn{
    width:100%;
    margin-top:8px;
    background:#f4d5d5;
    color:#913d3d;
}

.search-results{
    max-width:430px;
    margin:0 auto;
    padding:0 15px 30px;
}

.search-title{
    font-size:16px;
    font-weight:bold;
    margin:5px 0 12px;
}

.empty{
    text-align:center;
    padding:30px 10px;
    color:#9c897c;
}
</style>
</head>

<body>

<!-- =========================
     메인 화면
========================= -->

<div id="mainPage" class="page active">

<header>
    <h1>🏠 정인하이츠</h1>
    <p>원룸 체크리스트</p>
</header>

<div id="alertBox" class="alert-box"></div>

<div class="building-wrap">
<div class="building">

    <!-- 5층 -->
    <div class="floor floor-roof" onclick="openFloor(5)">
        <div class="floor-label">옥상</div>
        <div class="floor-sub">5층</div>
    </div>

    <!-- 4층 -->
    <div class="floor floor-four" onclick="openFloor(4)">
        <div class="floor-label">4층</div>
        <div class="floor-sub">
            501호 · 502호 · 503호 · 505호
        </div>
    </div>

    <!-- 3층 -->
    <div class="floor floor-three" onclick="openFloor(3)">
        <div class="floor-label">3층</div>
        <div class="floor-sub">
            301호 · 302호 · 303호 · 305호 · 306호 · 307호
        </div>
    </div>

    <!-- 2층 -->
    <div class="floor floor-two" onclick="openFloor(2)">
        <div class="floor-label">2층</div>
        <div class="floor-sub">
            201호 · 202호 · 203호 · 205호 · 206호 · 207호
        </div>
    </div>

    <!-- 1층 -->
    <div class="floor floor-parking" onclick="openParking()">
        <div class="floor-label">🚗 주차장</div>
        <div class="floor-sub">1층</div>
    </div>

</div>
</div>

<div class="controls">

    <input
        id="searchInput"
        class="search-box"
        type="text"
        placeholder="🔍 호실 또는 이름 검색"
        oninput="searchRooms()"
    >

    <div class="btn-row">

        <button
            class="notice-btn"
            onclick="requestNotification()"
        >
            🔔 알림 허용
        </button>

        <button
            class="reset-btn"
            onclick="resetAll()"
        >
            초기화
        </button>

    </div>
</div>

<div id="searchResults" class="search-results"></div>

</div>


<!-- =========================
     층 화면
========================= -->

<div id="floorPage" class="page">

<header>
    <h1 id="floorTitle">2층</h1>
    <p>호실을 눌러 정보를 입력하세요</p>
</header>

<button class="back-btn" onclick="goHome()">
    ← 정인하이츠 건물로 돌아가기
</button>

<div id="roomList" class="room-list"></div>

</div>


<!-- =========================
     주차장
========================= -->

<div id="parkingPage" class="page">

<header>
    <h1>🚗 주차장</h1>
    <p>정인하이츠 1층</p>
</header>

<button class="back-btn" onclick="goHome()">
    ← 정인하이츠 건물로 돌아가기
</button>

<div class="room-list">

<div class="room-card">

    <div class="room-top">

        <div class="room-number">
            1층
        </div>

        <div class="room-status status-good">
            주차장
        </div>

    </div>

    <div class="room-info">
        🚗 정인하이츠 주차장
        <br>
        주차장 관련 메모를 저장할 수 있습니다.
    </div>

    <div class="room-actions">

        <button
            class="edit-btn"
            onclick="editParking()"
        >
            ✏️ 메모 입력
        </button>

    </div>

</div>

</div>
</div>


<!-- =========================
     호실 입력 모달
========================= -->

<div id="roomModal" class="modal-bg">

<div class="modal">

    <h2 id="modalTitle">201호</h2>

    <div class="form-group">
        <label>👤 이름</label>

        <input
            id="roomName"
            type="text"
            placeholder="입주자 이름"
        >
    </div>

    <div class="form-group">
        <label>💰 보증금</label>

        <input
            id="deposit"
            type="text"
            placeholder="예: 500만원"
        >
    </div>

    <div class="form-group">
        <label>🏠 월세</label>

        <input
            id="rent"
            type="text"
            placeholder="예: 40만원"
        >
    </div>

    <div class="form-group">
        <label>📅 계약한 날</label>

        <input
            id="contractDate"
            type="date"
        >
    </div>

    <div class="form-group">
        <label>📅 만기 날</label>

        <input
            id="expiryDate"
            type="date"
        >
    </div>

    <hr>

    <h3>🔔 이 호실 알람 설정</h3>

    <div class="form-group">
        <label>알람 사용</label>

        <select id="alarmEnabled">
            <option value="false">알람 끄기</option>
            <option value="true">알람 켜기</option>
        </select>
    </div>

    <div class="form-group">
        <label>📅 알람 날짜</label>

        <input
            id="alarmDate"
            type="date"
        >
    </div>

    <div class="form-group">
        <label>⏰ 알람 시간</label>

        <input
            id="alarmTime"
            type="time"
        >
    </div>

    <div class="form-group">
        <label>🔊 음성 알람</label>

        <select id="voiceAlarm">

            <option value="false">
                음성 알람 끄기
            </option>

            <option value="true">
                음성 알람 켜기
            </option>

        </select>
    </div>

    <div class="modal-buttons">

        <button
            class="cancel-btn"
            onclick="closeModal()"
        >
            취소
        </button>

        <button
            class="save-btn"
            onclick="saveRoom()"
        >
            저장
        </button>

    </div>

    <button
        class="delete-btn"
        onclick="deleteRoom()"
    >
        🗑️ 이 호실 정보 삭제
    </button>

</div>
</div>


<!-- =========================
     주차장 메모 모달
========================= -->

<div id="parkingModal" class="modal-bg">

<div class="modal">

    <h2>🚗 주차장 메모</h2>

    <div class="form-group">

        <label>메모</label>

        <input
            id="parkingMemo"
            type="text"
            placeholder="주차장 관련 메모"
        >

    </div>

    <div class="modal-buttons">

        <button
            class="cancel-btn"
            onclick="closeParkingModal()"
        >
            취소
        </button>

        <button
            class="save-btn"
            onclick="saveParking()"
        >
            저장
        </button>

    </div>

</div>
</div>


<script>

/* =========================================
   호실 구조
========================================= */

const FLOOR_ROOMS = {

    2: [
        "201",
        "202",
        "203",
        "205",
        "206",
        "207"
    ],

    3: [
        "301",
        "302",
        "303",
        "305",
        "306",
        "307"
    ],

    4: [
        "501",
        "502",
        "503",
        "505"
    ]

};


/* =========================================
   저장 데이터
========================================= */

const STORAGE_KEY =
"jeongin_heights_rooms_v4";

let rooms =
JSON.parse(
    localStorage.getItem(
        STORAGE_KEY
    ) || "{}"
);

let currentRoom = null;


/* =========================================
   데이터 저장
========================================= */

function saveData(){

    localStorage.setItem(
        STORAGE_KEY,
        JSON.stringify(rooms)
    );

}


/* =========================================
   홈으로
========================================= */

function goHome(){

    document
    .querySelectorAll(".page")
    .forEach(
        page =>
        page.classList.remove("active")
    );

    document
    .getElementById("mainPage")
    .classList.add("active");

    renderAlert();

}


/* =========================================
   층 열기
========================================= */

function openFloor(floor){

    if(floor === 5){

        alert("🏠 5층은 옥상입니다.");

        return;

    }

    document
    .querySelectorAll(".page")
    .forEach(
        page =>
        page.classList.remove("active")
    );

    document
    .getElementById("floorPage")
    .classList.add("active");

    document
    .getElementById("floorTitle")
    .textContent =
    floor + "층";

    renderRooms(floor);

}


/* =========================================
   주차장
========================================= */

function openParking(){

    document
    .querySelectorAll(".page")
    .forEach(
        page =>
        page.classList.remove("active")
    );

    document
    .getElementById("parkingPage")
    .classList.add("active");

}


function editParking(){

    document
    .getElementById("parkingMemo")
    .value =
    localStorage.getItem(
        "parkingMemo"
    ) || "";

    document
    .getElementById("parkingModal")
    .classList.add("show");

}


function saveParking(){

    const memo =
    document
    .getElementById("parkingMemo")
    .value;

    localStorage.setItem(
        "parkingMemo",
        memo
    );

    closeParkingModal();

    alert(
        "주차장 메모가 저장되었습니다."
    );

}


function closeParkingModal(){

    document
    .getElementById("parkingModal")
    .classList.remove("show");

}


/* =========================================
   호실 목록 표시
========================================= */

function renderRooms(floor){

    const list =
    document
    .getElementById("roomList");

    list.innerHTML = "";

    const roomNumbers =
    FLOOR_ROOMS[floor] || [];

    roomNumbers.forEach(
        roomNumber => {

            const data =
            rooms[roomNumber] || {};

            const status =
            getExpiryStatus(
                data.expiryDate
            );

            const card =
            document.createElement(
                "div"
            );

            card.className =
            "room-card";

            let alarmHTML = "";

            if(data.alarmEnabled){

                alarmHTML = `

                    <div class="alarm-info">

                        🔔 알람:
                        ${
                            data.alarmDate ||
                            "날짜 없음"
                        }

                        ${
                            data.alarmTime ||
                            ""
                        }

                        ${
                            data.voiceAlarm
                            ? " · 🔊 음성 ON"
                            : " · 음성 OFF"
                        }

                    </div>

                `;

            }

            card.innerHTML = `

                <div class="room-top">

                    <div>

                        <div class="room-number">
                            ${roomNumber}호
                        </div>

                        <div class="room-name">

                            ${
                                data.name
                                ?
                                "👤 " +
                                escapeHtml(data.name)
                                :
                                "이름 미입력"
                            }

                        </div>

                    </div>

                    <div
                        class="room-status
                        ${status.className}"
                    >
                        ${status.text}
                    </div>

                </div>

                <div class="room-info">

                    ${
                        data.deposit
                        ?
                        "💰 보증금: " +
                        escapeHtml(data.deposit) +
                        "<br>"
                        :
                        ""
                    }

                    ${
                        data.rent
                        ?
                        "🏠 월세: " +
                        escapeHtml(data.rent) +
                        "<br>"
                        :
                        ""
                    }

                    ${
                        data.contractDate
                        ?
                        "📅 계약일: " +
                        data.contractDate +
                        "<br>"
                        :
                        ""
                    }

                    ${
                        data.expiryDate
                        ?
                        "🔔 만기일: " +
                        data.expiryDate
                        :
                        ""
                    }

                    ${
                        !data.deposit &&
                        !data.rent &&
                        !data.contractDate &&
                        !data.expiryDate
                        ?
                        "아직 입력된 정보가 없습니다."
                        :
                        ""
                    }

                    ${alarmHTML}

                </div>

                <div class="room-actions">

                    <button
                        class="edit-btn"
                        onclick="
                            openRoom('${roomNumber}')
                        "
                    >
                        ✏️ 정보 입력/수정
                    </button>

                    <button
                        class="clear-btn"
                        onclick="
                            quickDelete('${roomNumber}')
                        "
                    >
                        삭제
                    </button>

                </div>

            `;

            list.appendChild(card);

        }
    );

}


/* =========================================
   호실 열기
========================================= */

function openRoom(roomNumber){

    currentRoom =
    roomNumber;

    const data =
    rooms[roomNumber] || {};

    document
    .getElementById("modalTitle")
    .textContent =
    roomNumber + "호";

    document
    .getElementById("roomName")
    .value =
    data.name || "";

    document
    .getElementById("deposit")
    .value =
    data.deposit || "";

    document
    .getElementById("rent")
    .value =
    data.rent || "";

    document
    .getElementById("contractDate")
    .value =
    data.contractDate || "";

    document
    .getElementById("expiryDate")
    .value =
    data.expiryDate || "";

    document
    .getElementById("alarmEnabled")
    .value =
    String(
        data.alarmEnabled || false
    );

    document
    .getElementById("alarmDate")
    .value =
    data.alarmDate || "";

    document
    .getElementById("alarmTime")
    .value =
    data.alarmTime || "";

    document
    .getElementById("voiceAlarm")
    .value =
    String(
        data.voiceAlarm || false
    );

    document
    .getElementById("roomModal")
    .classList
    .add("show");

}


/* =========================================
   저장
========================================= */

function saveRoom(){

    if(!currentRoom)
        return;

    rooms[currentRoom] = {

        name:
        document
      
