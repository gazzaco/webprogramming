코어객체 -> 중간고사 전까지 학습한것.

BOM -> Browers object model

DOM -> Document object model
(봄은 브라우저 전체, 창 전체를 의미. 안쪽 창 영역을 얘기할때는 돔)
봄 안에는 돔 포함

서버에 있는 HTML 문서를 브라우저가 표시해줘야함

html,문서를 받으면 태그에 따라서 DOM이 자체적으로 트리 모양으로 DOM객체를 나눔
태그 당 DOM 객체가 하나씩 생성
DOM객체의 종류는 HTML태그 종류만큼있음
이 트리를 DOM이라고 부르는것
항목 하나하나(DOM,객체 하나)를 노드라 함

HTML 태그 (=element) (=트리를 구성하는 노드) (=object)
- 태그이름
- 속성 (ex.id)
- CSS3스타일(인라인css)
- 이벤트 리스너(자바스크립트 함수)
- 콘텐츠

DOM객체의 구성
- 프로퍼티 (ex.id, tagName, innerHTML, style
- 메소드
- 컬렉션
- 이벤트 리스너
- CSS3 스타일

트리 봤을때 같은 라인에 있으면 형제관계, 밑에는 자식 (firstElementChild,lastElementChild)
위에는 부모관계

<body>
  <p id = "a"
    style = "color:blue; background:yellow"
    onclick = "this.style.color = 'teal'">
    이것은 <span style = "color:red">DOM객체 연슴</span>
  </p>
</body>
<script>
  let p = document.getElementById("a");
  let text = p.id
  text +=
</script>
script안에
let p = document.getElementById("바디안에아이디이름");
p.tagName = 태그이름
p.innerHTML = 

---

DOM 객체를 구분할때는 id 태그 속성을 사용 <p id = "a"></p>
<DOM 객체 찾기>
let p = document.getElementById("a"); // id값이 a인 DOM 객체 리턴
p.style.color = "red"; // p 객체의 글자 색을 red로 변경

<script>
function change() {
let span = document.getElementById("mySpan");
span.style.color = "green"; // 글자 색 green
span.style.fontSize = "30px"; // 글자 크기는 30픽셀
span.style.display = "block"; // 블록 박스로 변경
span.style.width = "6em"; // 박스의 폭. 6 글자 크기
span.style.border = "3px dotted magenta"; // 3픽셀 점선 magenta 테두리
span.style.margin = "20px"; // 상하좌우 여백 20px
}
</script>

---


<script>
function change() {
let p = document.getElementById("firstP");
p.innerHTML= "나의 <img src='puppy.png'> 강아지";
}
</script>
</head>
<body>
<h3>innerHTML 활용 : 아래 글자에 클릭하면
예쁜 강아지가 보입니다.</h3>
<hr>
<p id="firstP" style="color:blue"
onclick="change()">
여기에 <span style="color:red">클릭하세요</span>
</p>
</body>

---

this
객체 자신을 가리키는 것., DOM객체에서 객체 자신을 가리키는 용도로 사용
ex) <div onclick = "this.style.backgroundColor = 'orange'">
// <div>태그 자신의 배경을 orange색으로 변경
ex) <button onclick="this.style.backgroundColor='orange'">
// 버튼이 클릭되면 자신의 배경색을 orange로 변경

---

<script>
function change(obj, size, color) { // obj -> 클릭된 HTML요소 가리킴(this가전달됨)
obj.style.color = color; // 약간 함수 느
obj.style.fontSize = size;
}
</script>
</head>
<body>
<h3>this 활용</h3> <hr>
<button onclick="change(this, '30px', 'red')">버튼</button>
<button onclick="change(this, '30px', 'blue')">버튼</button>
<div onclick="change(this, '25px', 'orange')">
여기 클릭하면 크기와
색 변경
</div>
</body>

---

태그 이름으로 찾기
document.getElementsByTagName() 
태그 이름이 같은 모든 DOM객체들 찾아 컬렉션 리턴

---
write()와 writeln()

<body>
<script>
document.write("<h3>동물원에 소풍갑시다</h3>");
document.write("<p style='color:blue'>날씨가 좋아 ");
document.write("소풍갑니다</p>");
document.write(2+3);
document.write("명입니다.<br>"); // 다음 줄로 넘어가기
document.writeln(5); // 다음 줄에 넘어가지 못함
document.writeln("명입니다.<br>");
</script>
</body>

자바스크립트로 태그 사용해서 출력하

----

open(), close()
document열기 닫기.

<script>
let win=null;
function showHTML() {
if(win == null || win.closed)
win = window.open("", "outWin", "width=300,height=200");
let textArea = document.getElementById("srcText");
win.document.open();
win.document.write(textArea.value);
win.document.close();
}
</script>
<body>
<p>아래에 HTML 문서를 작성하고 버튼을 클릭해 보세요.
새 윈도우에 HTML 문서가 출력됩니다.</p>
<textarea id="srcText" rows="10" cols="50"></textarea>
<button onclick="showHTML()">HTML 문서 출력하기</button>
</body>

버튼 클릭하면 새 윈도우 출력


---


웹사이트 기획
다음주발표만하다끝날수도
만명이상의 전세계, 국내대상
만명이상에 게 도움이 되는 사이트를 만들어오기
단, 단, 내가 요거가지고 먹고살아야해
진짜귀중한아이디어야 -> 하지말아요 (?)
호;ㅣ사가 만명이야 -> 회사사이트
보건소잉요하는사람 만명넘음 -> 보건소 사이트
1. 사이트 기획 이 사이트를 만드는 이유, 이 사이트로 이해서 도움받는 대상, 효과
2. 사이트 구축, 깃허브 호스팅
3. 최소인원 만명
4. 러버블(??  AI 사용해서 만드세요
5. 만들고 나면 다시 그 내용을 보고 다시 프롬프트 작성해서 업그레이드 하기 (사이트 바꾸기)
6. 다시 결과나와
7. 다시 바꾸기(업그레이드)(프롬프트) 이걸 몇번 반복해
8. 프롬프트 10개 나오게
9. 모든 코드가 해석이 되어야 함
10. 코드해석안되면 가지고 오세요
11. 바꾸는거 ㄴ폰트, 스타일 뭐 이런거   바꿔도 됨
12. ex) 여성취업지원센터 홈페이지
13. 만명을 만족시키는 사이트
14. 전까지 배운걸로는 만들기 힘드니까 ,AI사용
15. 다음주까지 레포트
16. 레포트는 어떻게 써야하지 ?


