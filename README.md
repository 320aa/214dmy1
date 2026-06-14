<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>화장품 성분 분석기</title>

<style>
    body {
        font-family: "맑은 고딕", sans-serif;
        margin: 0;
        background-color: #f4f6f9;
        color: #333;
    }

    header {
        background: linear-gradient(135deg, #6aa9ff, #8fd3f4);
        color: white;
        text-align: center;
        padding: 40px 20px;
    }

    nav {
        background-color: #4b79a1;
        padding: 15px;
        text-align: center;
    }

    nav a {
        color: white;
        text-decoration: none;
        margin: 0 15px;
        font-weight: bold;
    }

    section {
        max-width: 1000px;
        margin: 30px auto;
        padding: 30px;
        background-color: white;
        border-radius: 15px;
        box-shadow: 0 3px 10px rgba(0,0,0,0.1);
    }

    h2 {
        color: #4b79a1;
    }

    .search-box {
        text-align: center;
        margin: 20px 0;
    }

    input {
        width: 60%;
        padding: 12px;
        border-radius: 10px;
        border: 1px solid #ccc;
        font-size: 16px;
    }

    button {
        padding: 12px 20px;
        border: none;
        border-radius: 10px;
        background-color: #4b79a1;
        color: white;
        cursor: pointer;
        font-size: 16px;
    }

    button:hover {
        background-color: #355c7d;
    }

    #result {
        margin-top: 30px;
        padding: 20px;
        border-radius: 12px;
        background-color: #eef6ff;
    }

    .ingredient-card {
        margin: 15px 0;
        padding: 20px;
        background-color: #f9fbfd;
        border-left: 6px solid #6aa9ff;
        border-radius: 10px;
    }

    footer {
        text-align: center;
        background-color: #4b79a1;
        color: white;
        padding: 20px;
        margin-top: 40px;
    }
</style>
</head>

<body>

<header>
    <h1>🔍 화장품 성분 분석기</h1>
    <p>화장품 속 성분의 역할과 주의사항을 알아보세요.</p>
</header>

<nav>
    <a href="#about">소개</a>
    <a href="#search">성분 검색</a>
    <a href="#info">성분 정보</a>
</nav>

<section id="about">
    <h2>화장품 성분 분석기란?</h2>

    <p>
        우리가 매일 사용하는 화장품에는 다양한 화학 성분이 포함되어 있습니다.
        이 웹사이트는 주요 화장품 성분의 역할과 주의사항을 쉽게 이해할 수 있도록 제작되었습니다.
    </p>

    <ul>
        <li>✔ 보습 성분 알아보기</li>
        <li>✔ 피부 자극 가능성 확인하기</li>
        <li>✔ 성분의 역할 이해하기</li>
    </ul>
</section>

<section id="search">
    <h2>성분 검색</h2>

    <div class="search-box">
        <input type="text" id="ingredientInput"
               placeholder="예: 히알루론산, 나이아신아마이드">
        <button onclick="searchIngredient()">검색</button>
    </div>

    <div id="result">
        검색 결과가 여기에 표시됩니다.
    </div>
</section>

<section id="info">
    <h2>대표 성분 예시</h2>

    <div class="ingredient-card">
        <h3>히알루론산</h3>
        <p>수분을 끌어당겨 피부 보습을 돕는 성분</p>
    </div>

    <div class="ingredient-card">
        <h3>나이아신아마이드</h3>
        <p>미백 및 피부 장벽 개선에 도움</p>
    </div>

    <div class="ingredient-card">
        <h3>살리실산(BHA)</h3>
        <p>각질 제거와 피지 관리에 사용</p>
    </div>
</section>

<footer>
    <p>고등학교 화학 교과와 연계한 수행평가 프로젝트</p>
</footer>

<script>
const ingredients = {
    "히알루론산": {
        role: "보습 성분",
        effect: "피부 수분 유지",
        caution: "특별한 주의사항은 적음"
    },

    "나이아신아마이드": {
        role: "미백 기능성 성분",
        effect: "피부 톤 개선, 장벽 강화",
        caution: "민감성 피부는 고농도 사용 시 자극 가능"
    },

    "살리실산": {
        role: "각질 제거 성분",
        effect: "피지 조절 및 여드름 관리",
        caution: "건조함이나 자극이 나타날 수 있음"
    },

    "글리세린": {
        role: "보습제",
        effect: "수분 증발 방지",
        caution: "과다 사용 시 끈적임 발생 가능"
    },

    "비타민C": {
        role: "항산화 성분",
        effect: "피부 톤 개선 및 색소 침착 완화",
        caution: "민감성 피부는 따가움을 느낄 수 있음"
    }
};

function searchIngredient() {
    const input =
        document.getElementById("ingredientInput").value.trim();

    const result =
        document.getElementById("result");

    if (ingredients[input]) {

        result.innerHTML = `
            <h3>${input}</h3>

            <p><strong>역할:</strong>
            ${ingredients[input].role}</p>

            <p><strong>효능:</strong>
            ${ingredients[input].effect}</p>

            <p><strong>주의사항:</strong>
            ${ingredients[input].caution}</p>
        `;

    } else {

        result.innerHTML = `
            <p>해당 성분 정보가 없습니다.</p>
            <p>예시: 히알루론산, 나이아신아마이드,
            살리실산, 글리세린, 비타민C</p>
        `;
    }
}
</script>

</body>
</html>
