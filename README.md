<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>마니또</title>
</head>
<body>

<h2>나의 마니또 찾기</h2>

<!-- 입력 폼 -->
<label for="name">이름:</label>
<input type="text" id="name" placeholder="이름을 입력하세요">
<button onclick="findMatch()">확인</button>

<!-- 결과 표시 -->
<div id="result"></div>

<script>
var excelData = [
    { name: "황홍섭", matchingPerson: "김혜리", contact: "010-6549-4939" },
    { name: "김혜리", matchingPerson: "황홍섭", contact: "010-3911-7172" },
    { name: "이송희", matchingPerson: "고재현", contact: "010-5005-9107" },
    { name: "고재현", matchingPerson: "이송희", contact: "010-8317-7813" },
    { name: "김영광", matchingPerson: "이인경", contact: "010-7572-9968" },
    { name: "이인경", matchingPerson: "김영광", contact: "010-6863-6624" },
    { name: "장서진", matchingPerson: "최두원", contact: "010-5012-2130" },
    { name: "최두원", matchingPerson: "장서진", contact: "010-9845-2563" },
    { name: "임규", matchingPerson: "이성헌", contact: "010-2045-4257" },
    { name: "이성헌", matchingPerson: "임규", contact: "010-2557-0122" },
    { name: "박해연", matchingPerson: "최우혁", contact: "010-6863-6624" },
    { name: "최우혁", matchingPerson: "박해연", contact: "010-5012-2130" },
    { name: "김성진", matchingPerson: "김준", contact: "010-9845-2563" },
    { name: "김준", matchingPerson: "김성진", contact: "010-2045-4257" }
    // 필요에 따라 더 많은 데이터 추가 가능
];

function findMatch() {
    // 입력한 이름 가져오기
    var inputName = document.getElementById("name").value;
    
    // 매칭되는 사람 및 연락처 찾기
    var matchingPerson = "매칭되는 사람 없음";
    var contact = "";
    for (var i = 0; i < excelData.length; i++) {
        if (excelData[i].name === inputName) {
            matchingPerson = excelData[i].matchingPerson;
            contact = excelData[i].contact;
            break;
        }
    }

    // 결과 표시
    var resultElement = document.getElementById("result");
    resultElement.innerHTML = "나의 마니또: " + matchingPerson + "<br> 연락처: " + contact;
}
</script>

</body>
</html>
