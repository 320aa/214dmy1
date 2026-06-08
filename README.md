<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>화학 물질 위험도 사전</title>

<style>
body{
    font-family: Arial, sans-serif;
    background:#f4f6f8;
    text-align:center;
    padding:30px;
}

.container{
    background:white;
    max-width:700px;
    margin:auto;
    padding:25px;
    border-radius:15px;
    box-shadow:0 0 10px rgba(0,0,0,0.2);
}

input{
    padding:10px;
    width:200px;
    font-size:16px;
}

button{
    padding:10px 15px;
    font-size:16px;
    cursor:pointer;
}

.result{
    margin-top:20px;
    padding:15px;
    border-radius:10px;
    background:#eef3f7;
}
</style>
</head>

<body>

<div class="container">
    <h1>🧪 화학 물질 위험도 사전</h1>

    <p>화학식을 입력하세요 (예: HCl, NaOH, H₂O)</p>

    <input type="text" id="searchBox" placeholder="화학식 입력">
    <button onclick="searchChemical()">검색</button>

    <div class="result" id="result">
        화학식을 검색해 보세요.
    </div>
</div>

<script>

const chemicals = {
    "HCL": {
        name:"염산",
        formula:"HCl",
        danger:"🔴 높음",
        hazard:"강산으로 피부와 눈에 화상을 입힐 수 있음",
        caution:"보호장갑, 보호안경 착용"
    },

    "NAOH": {
        name:"수산화나트륨",
        formula:"NaOH",
        danger:"🔴 높음",
        hazard:"강염기성으로 피부 손상 가능",
        caution:"직접 접촉 금지"
    },

    "C2H5OH": {
        name:"에탄올",
        formula:"C₂H₅OH",
        danger:"🟡 중간",
        hazard:"인화성이 높음",
        caution:"화기 근처 사용 금지"
    },

    "H2O2": {
        name:"과산화수소",
        formula:"H₂O₂",
        danger:"🟡 중간",
        hazard:"고농도에서 피부 자극",
        caution:"눈 접촉 주의"
    },

    "H2O": {
        name:"물",
        formula:"H₂O",
        danger:"🟢 낮음",
        hazard:"일반 사용 시 위험 없음",
        caution:"특별한 주의사항 없음"
    }
};

function searchChemical(){

    let input = document
        .getElementById("searchBox")
        .value
        .toUpperCase()
        .replaceAll("₂","2")
        .replaceAll("₅","5");

    const result = document.getElementById("result");

    if(chemicals[input]){
        const info = chemicals[input];

        result.innerHTML = `
        <h2>${info.name}</h2>
        <p><b>화학식:</b> ${info.formula}</p>
        <p><b>위험도:</b> ${info.danger}</p>
        <p><b>위험성:</b> ${info.hazard}</p>
        <p><b>주의사항:</b> ${info.caution}</p>
        `;
    }
    else{
        result.innerHTML = `
        <h2>검색 결과 없음</h2>
        <p>등록되지 않은 화학 물질입니다.</p>
        `;
    }
}

</script>

</body>
</html>
