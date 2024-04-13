```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<style>

    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
    }

    header {
        background-color: #333;
        color: #fff;
        padding: 20px;
        text-align: center;
    }

    nav ul {
        list-style-type: none;
        padding: 0;
        margin: 0;
        background-color: #f4f4f4;
        overflow: hidden;
    }

    nav ul li {
        float: left;
    }

    nav ul li a {
        display: block;
        padding: 20px;
        text-decoration: none;
        color: #333;
    }

    nav ul li a:hover {
        background-color: #ddd;
    }

    section {
        padding: 20px;
    }

    table {
        width: 100%;
        border-collapse: collapse;
    }

    table, th, td {
        border: 1px solid #ddd;
    }

    th, td {
        padding: 10px;
        text-align: left;
    }

    th {
        background-color: #f2f2f2;
    }

    input[type="text"], input[type="button"] {
        padding: 10px;
        border: 1px solid #ddd;
        border-radius: 5px;
        margin-bottom: 10px;
    }

    input[type="button"] {
        background-color: #4CAF50;
        color: white;
        cursor: pointer;
    }

    input[type="button"]:hover {
        background-color: #45a049;
    }


li{
display: inline;
}

</style>
</head>
<body>
<header>할인점 주문프로그램ver1.0</header>
<nav>
<ul>
<li><a href ="regi.jsp">주문등록</a></li><li><a href ="showNew">주문목록조회</a></li><li><a href ="">점포별주문현황</a></li><li><a href ="">제품코드조회</a></li><li><a href ="main.jsp">홈으로</a></li>

<input type="button" value="주문목록조회" id = "search" onclick="window.location.href='showNew'">

</ul>
</nav>
<section>
<h1>상단의 메뉴를 선택해주세요</h1>
</section>
<footer>


</footer>
<script>
//const orderBtn = document.getElementById("orderBtn")
//orderBtn.addEventLister("click","f()")

//function f{
	
//}
</script>
</body>
```
</html>
