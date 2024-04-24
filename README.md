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
    { name: "김영광", matchingPerson: "최예경", contact: "010-6542-0764" },
    { name: "최예경", matchingPerson: "김영광", contact: "010-6863-6624" }
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
