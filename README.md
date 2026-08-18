<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="theme-color" content="#fff5e9">
<title>정인하이츠</title>

<style>
*{
    box-sizing:border-box;
    -webkit-tap-highlight-color:transparent;
}

html,body{
    margin:0;
    padding:0;
    width:100%;
    min-height:100%;
}

body{
    font-family:
        "Noto Sans KR",
        "Apple SD Gothic Neo",
        Arial,
        sans-serif;
    background:#fff6ea;
    color:#594438;
}

button,
input,
select{
    font-family:inherit;
}

button{
    border:0;
    cursor:pointer;
    touch-action:manipulation;
}

.screen{
    display:none;
    min-height:100vh;
}

.screen.active{
    display:block;
}

.header{
    text-align:center;
    padding:28px 15px 18px;
}

.header h1{
    margin:0;
    font-size:30px;
    font-weight:900;
    color:#704c39;
}

.header p{
    margin:7px 0 0;
    font-size:14px;
    color:#9b7c69;
}


/* =========================
   건물
========================= */

.building-wrap{
    width:100%;
    padding:5px 16px 20px;
    display:flex;
    justify-content:center;
}

.building{
    width:100%;
    max-width:430px;
    border:5px solid #674737;
    border-radius:20px 20px 12px 12px;
    overflow:hidden;
    background:white;
    box-shadow:0 10px 25px rgba(80,50,30,.15);
}

.floor{
    width:100%;
    min-height:108px;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    text-align:center;
    border-bottom:4px solid #674737;
    padding:12px;
    user-select:none;
    -webkit-user-select:none;
    touch-action:manipulation;
}

.floor:last-child{
    border-bottom:0;
}

.floor:active{
    opacity:.72;
}

.floor-title{
    font-size:21px;
    font-weight:900;
}

.floor-desc{
    margin-top:6px;
    font-size:12px;
    line-height:1.5;
    color:#8c7465;
}

.floor-roof{
    min-height:82px;
    background:#dcecff;
}

.floor-4{
    background:#e3f0d8;
}

.floor-3{
    background:#ffedc9;
}

.floor-2{
    background:#ffe3c1;
}

.floor-1{
    background:#ddd9d3;
}


/* =========================
   검색
========================= */

.main-tools{
    width:100%;
    max-width:430px;
    margin:0 auto;
    padding:0 16px 25px;
}

.search{
    width:100%;
    height:48px;
    border:2px solid #ead7c8;
    border-radius:14px;
    padding:0 15px;
    font-size:15px;
    outline:none;
    background:white;
}

.search:focus{
    border-color:#bd8f70;
}

.tool-row{
    display:flex;
    gap:8px;
    margin-top:9px;
}

.tool-btn{
    flex:1;
    min-height:44px;
    border-radius:13px;
    background:#c9926d;
    color:white;
    font-weight:800;
}

.tool-btn.secondary{
    background:#e7d9cf;
    color:#6c5243;
}

.alert-area{
    width:100%;
    max-width:430px;
    margin:0 auto;
    padding:0 16px 15px;
}

.alert{
    background:#fff0d3;
    border:2px solid #edc98e;
    border-radius:15px;
    padding:12px 14px;
    font-size:13px;
    line-height:1.7;
}


/* =========================
   공통
========================= */

.back{
    display:block;
    width:calc(100% - 32px);
    max-width:430px;
    margin:0 auto 15px;
    min-height:46px;
    border-radius:14px;
    background:#765442;
    color:white;
    font-weight:900;
    font-size:14px;
}

.content{
    width:100%;
    max-width:430px;
    margin:0 auto;
    padding:0 16px 30px;
}


/* =========================
   호실 카드
========================= */

.room{
    background:white;
    border:2px solid #eadbd0;
    border-radius:18px;
    padding:16px;
    margin-bottom:12px;
    box-shadow:0 5px 14px rgba(80,50,30,.08);
}

.room-head{
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:8px;
}

.room-number{
    font-size:22px;
    font-weight:900;
    color:#674737;
}

.room-name{
    margin-top:4px;
    color:#9b7c69;
    font-size:13px;
}

.badge{
    padding:5px 8px;
    border-radius:20px;
    font-size:11px;
    white-space:nowrap;
    background:#eee7e1;
}

.badge.good{
    background:#dff0d9;
    color:#3f7436;
}

.badge.warning{
    background:#fff0c7;
    color:#916b00;
}

.badge.danger{
    background:#ffdada;
    color:#963838;
}

.room-info{
    margin-top:13px;
    font-size:13px;
    line-height:1.8;
    color:#6c5a4f;
}

.alarm{
    margin-top:9px;
    padding:8px 10px;
    border-radius:10px;
    background:#fff7e8;
    color:#80664f;
    font-size:12px;
}

.room-buttons{
    display:flex;
    gap:8px;
    margin-top:13px;
}

.room-buttons button{
    min-height:42px;
    border-radius:12px;
    font-weight:800;
}

.edit{
    flex:1;
    background:#e7c5a9;
    color:#654737;
}

.remove{
    padding:0 14px;
    background:#eee5df;
    color:#765c4e;
}


/* =========================
   주차장
========================= */

.parking-box{
    background:white;
    border:2px solid #d9d3ce;
    border-radius:20px;
    padding:25px 18px;
    text-align:center;
    box-shadow:0 5px 14px rgba(80,50,30,.08);
}

.parking-icon{
    font-size:52px;
}

.parking-title{
    margin-top:8px;
    font-size:24px;
    font-weight:900;
}

.parking-text{
    margin-top:8px;
    color:#8b786c;
    font-size:14px;
    line-height:1.7;
}

.parking-edit{
    margin-top:18px;
    width:100%;
    min-height:45px;
    border-radius:13px;
    background:#d9c8bb;
    color:#654737;
    font-weight:900;
}


/* =========================
   모달
========================= */

.modal-bg{
    position:fixed;
    inset:0;
    z-index:9999;
    display:none;
    align-items:center;
    justify-content:center;
    padding:16px;
    background:rgba(40,25,15,.5);
}

.modal-bg.open{
    display:flex;
}

.modal{
    width:100%;
    max-width:430px;
    max-height:92vh;
    overflow-y:auto;
    background:white;
    border-radius:22px;
    padding:20px;
}

.modal h2{
    margin:0 0 17px;
    color:#674737;
}

.modal h3{
    margin:20px 0 13px;
    color:#765442;
}

.field{
    margin-bottom:13px;
}

.field label{
    display:block;
    margin-bottom:6px;
    font-size:13px;
    font-weight:900;
    color:#765442;
}

.field input,
.field select{
    width:100%;
    height:46px;
    border:2px solid #eadbd0;
    border-radius:12px;
    padding:0 12px;
    outline:none;
    font-size:15px;
    background:white;
}

.field input:focus,
.field select:focus{
    border-color:#c29476;
}

.line{
    border:0;
    border-top:1px solid #eee1d8;
    margin:19px 0;
}

.modal-row{
    display:flex;
    gap:8px;
}

.modal-row button{
    flex:1;
    min-height:45px;
    border-radius:12px;
    font-weight:900;
}

.cancel{
    background:#eee5df;
    color:#705849;
}

.save{
    background:#765442;
    color:white;
}

.delete-all{
    width:100%;
    margin-top:8px;
    min-height:42px;
    border-radius:12px;
    background:#f3d7d7;
    color:#923f3f;
    font-weight:900;
}


/* =========================
   검색 결과
========================= */

.search-results{
    width:100%;
    max-width:430px;
    margin:0 auto;
    padding:0 16px 30px;
}

.search-heading{
    font-size:16px;
    font-weight:900;
    margin-bottom:10px;
}

.no-result{
    text-align:center;
    padding:25px;
    color:#9c897c;
}


/* =========================
   반응형
========================= */

@media(max-width:380px){

    .header h1{
        font-size:26px;
    }

    .floor-title{
        font-size:19px;
    }

    .room-number{
        font-size:20px;
    }

}
</style>
</head>

<body>


<!-- ======================================
     메인
======================================= -->

<section id="home" class="screen active">

    <header class="header">
        <h1>🏠 정인하이츠</h1>
        <p>원룸 체크리스트</p>
    </header>

    <div id="alerts" class="alert-area"></div>

    <div class="building-wrap">

        <div class="building">

            <!-- 5층 -->
            <div
                class="floor floor-roof"
                onclick="openFloor(5)"
            >
                <div class="floor-title">
                    🏠 옥상
                </div>

                <div class="floor-desc">
                    5층
                </div>
            </div>


            <!-- 4층 -->
            <div
                class="floor floor-4"
                onclick="openFloor(4)"
            >
                <div class="floor-title">
                    4층
                </div>

                <div class="floor-desc">
                    501호 · 502호 · 503호 · 505호
                </div>
            </div>


            <!-- 3층 -->
            <div
                class="floor floor-3"
                onclick="openFloor(3)"
            >
                <div class="floor-title">
                    3층
                </div>

                <div class="floor-desc">
                    301호 · 302호 · 303호 · 305호 · 306호 · 307호
                </div>
            </div>


            <!-- 2층 -->
            <div
                class="floor floor-2"
                onclick="openFloor(2)"
            >
                <div class="floor-title">
                    2층
                </div>

                <div class="floor-desc">
                    201호 · 202호 · 203호 · 205호 · 206호 · 207호
                </div>
            </div>


            <!-- 1층 -->
            <div
                class="floor floor-1"
                onclick="openParking()"
            >
                <div class="floor-title">
                    🚗 주차장
                </div>

                <div class="floor-desc">
                    1층
                </div>
            </div>

        </div>

    </div>


    <div class="main-tools">

        <input
            id="search"
            class="search"
            type="text"
            placeholder="🔍 호실 또는 이름 검색"
            oninput="searchRooms()"
        >

        <div class="tool-row">

            <button
                class="tool-btn"
                onclick="allowNotification()"
            >
                🔔 알림 허용
            </button>

            <button
                class="tool-btn secondary"
                onclick="resetEverything()"
            >
                초기화
            </button>

        </div>

    </div>


    <div id="searchResults" class="search-results"></div>

</section>



<!-- ======================================
     층 화면
======================================= -->

<section id="floorScreen" class="screen">

    <header class="header">
        <h1 id="floorName">2층</h1>
        <p>호실을 선택해주세요</p>
    </header>

    <button
        class="back"
        onclick="goHome()"
    >
        ← 정인하이츠로 돌아가기
    </button>

    <div
        id="rooms"
        class="content"
    ></div>

</section>



<!-- ======================================
     옥상
======================================= -->

<section id="roofScreen" class="screen">

    <header class="header">
        <h1>🏠 옥상</h1>
        <p>정인하이츠 5층</p>
    </header>

    <button
        class="back"
        onclick="goHome()"
    >
        ← 정인하이츠로 돌아가기
    </button>

    <div class="content">

        <div class="parking-box">

            <div class="parking-icon">
                🏠
            </div>

            <div class="parking-title">
                옥상
            </div>

            <div class="parking-text">
                정인하이츠 5층 옥상입니다.
            </div>

        </div>

    </div>

</section>



<!-- ======================================
     주차장
======================================= -->

<section id="parkingScreen" class="screen">

    <header class="header">
        <h1>🚗 주차장</h1>
        <p>정인하이츠 1층</p>
    </header>

    <button
        class="back"
        onclick="goHome()"
    >
        ← 정인하이츠로 돌아가기
    </button>

    <div class="content">

        <div class="parking-box">

            <div class="parking-icon">
                🚗
            </div>

            <div class="parking-title">
                주차장
            </div>

            <div class="parking-text">
                정인하이츠 1층 주차장입니다.
                <br>
                주차장 관련 메모를 저장할 수 있습니다.
            </div>

            <button
                class="parking-edit"
                onclick="openParkingMemo()"
            >
                ✏️ 주차장 메모
            </button>

        </div>

    </div>

</section>



<!-- ======================================
     호실 모달
======================================= -->

<div
    id="roomModal"
    class="modal-bg"
>

    <div class="modal">

        <h2 id="modalRoom">
            201호
        </h2>


        <div class="field">

            <label>👤 이름</label>

            <input
                id="name"
                type="text"
                placeholder="입주자 이름"
            >

        </div>


        <div class="field">

            <label>💰 보증금</label>

            <input
                id="deposit"
                type="text"
                placeholder="예: 500만원"
            >

        </div>


        <div class="field">

            <label>🏠 월세</label>

            <input
                id="rent"
                type="text"
                placeholder="예: 40만원"
            >

        </div>


        <div class="field">

            <label>📅 계약한 날</label>

            <input
                id="contract"
                type="date"
            >

        </div>


        <div class="field">

            <label>📅 만기 날</label>

            <input
                id="expiry"
                type="date"
            >

        </div>


        <hr class="line">


        <h3>
            🔔 이 호실 알람
        </h3>


        <div class="field">

            <label>알람</label>

            <select id="alarmEnabled">

                <option value="false">
                    알람 끄기
                </option>

                <option value="true">
                    알람 켜기
                </option>

            </select>

        </div>


        <div class="field">

            <label>알람 날짜</label>

            <input
                id="alarmDate"
                type="date"
            >

        </div>


        <div class="field">

            <label>알람 시간</label>

            <input
                id="alarmTime"
                type="time"
            >

        </div>


        <div class="field">

            <label>🔊 음성 알람</label>

            <select id="voice">

                <option value="false">
                    음성 알람 끄기
                </option>

                <option value="true">
                    음성 알람 켜기
                </option>

            </select>

        </div>


        <div class="modal-row">

            <button
                class="cancel"
                onclick="closeRoomModal()"
            >
                취소
            </button>

            <button
                class="save"
                onclick="saveRoom()"
            >
                저장
            </button>

        </div>


        <button
            class="delete-all"
            onclick="deleteCurrentRoom()"
        >
            🗑️ 이 호실 정보 삭제
        </button>

    </div>

</div>



<!-- ======================================
     주차장 메모
======================================= -->

<div
    id="parkingModal"
    class="modal-bg"
>

    <div class="modal">

        <h2>
            🚗 주차장 메모
        </h2>

        <div class="field">

            <label>메모</label>

            <input
                id="parkingMemo"
                type="text"
                placeholder="주차장 관련 메모"
            >

        </div>

        <div class="modal-row">

            <button
                class="cancel"
                onclick="closeParkingMemo()"
            >
                취소
            </button>

            <button
                class="save"
                onclick="saveParkingMemo()"
            >
                저장
            </button>

        </div>

    </div>

</div>



<script>

/* =========================================
   정확한 호실 목록
========================================= */

const FLOORS = {

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
   저장
========================================= */

const KEY =
"jeongin_heights_final";

let data =
JSON.parse(
    localStorage.getItem(KEY) || "{}"
);

let selectedRoom = null;


/* =========================================
   화면 전환
========================================= */

function showScreen(id){

    document
        .querySelectorAll(".screen")
        .forEach(function(screen){

            screen.classList.remove("active");

        });

    document
        .getElementById(id)
        .classList.add("active");

    window.scrollTo(0,0);

}


function goHome(){

    showScreen("home");

    renderAlerts();

}


/* =========================================
   층
========================================= */

function openFloor(floor){

    if(floor === 5){

        showScreen("roofScreen");

        return;

    }

    document
        .getElementById("floorName")
        .textContent =
        floor + "층";

    renderRooms(floor);

    showScreen("floorScreen");

}


/* =========================================
   주차장
========================================= */

function openParking(){

    showScreen("parkingScreen");

}


function openParkingMemo(){

    document
        .getElementById("parkingMemo")
        .value =
        localStorage.getItem(
            "parking_memo"
        ) || "";

    document
        .getElementById("parkingModal")
        .classList.add("open");

}


function closeParkingMemo(){

    document
        .getElementById("parkingModal")
        .classList.remove("open");

}


function saveParkingMemo(){

    localStorage.setItem(
        "parking_memo",
        document
            .getElementById("parkingMemo")
            .value
    );

    closeParkingMemo();

}


/* =========================================
   층의 호실 표시
========================================= */

function renderRooms(floor){

    const container =
        document.getElementById("rooms");

    container.innerHTML = "";

    FLOORS[floor].forEach(
        function(room){

            const item =
                data[room] || {};

            const status =
                expiryStatus(
                    item.expiry
                );

            const div =
                document.createElement("div");

            div.className = "room";

            let information = "";

            if(item.deposit){

                information +=
                    "💰 보증금: " +
                    safe(item.deposit) +
                    "<br>";

            }

            if(item.rent){

                information +=
                    "🏠 월세: " +
                    safe(item.rent) +
                    "<br>";

            }

            if(item.contract){

                information +=
                    "📅 계약일: " +
                    item.contract +
                    "<br>";

            }

            if(item.expiry){

                information +=
                    "🔔 만기일: " +
                    item.expiry;

            }

            if(!information){

                information =
                    "아직 입력된 정보가 없습니다.";

            }


            let alarm = "";

            if(item.alarmEnabled){

                alarm =

                    "<div class='alarm'>" +

                    "🔔 알람: " +
                    (
                        item.alarmDate ||
                        "날짜 없음"
                    ) +

                    " " +

                    (
                        item.alarmTime ||
                        ""
                    ) +

                    (
                        item.voice
                        ? " · 🔊 음성 ON
