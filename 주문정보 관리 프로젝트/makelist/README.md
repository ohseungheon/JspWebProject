```jsp
<%@page import="java.sql.PreparedStatement"%>
<%@page import="dao.DBcon"%>

<%@page import="java.util.ArrayList"%>
<%@page import="java.sql.ResultSet"%>
<%@page import="java.sql.Statement"%>
<%@page import="java.sql.DriverManager"%>
<%@page import="java.sql.Connection"%>
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
 
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
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
        border: 1px solid #ddd; /* 추가된 부분: 테이블 전체에 테두리 적용 */
    }

    th, td {
        padding: 10px;
        text-align: left;
        border: 1px solid #ddd; /* 추가된 부분: 셀 간 경계선 */
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

    li {
        display: inline;
    }

</style>
</head>
<body>
<table>
	<thead>
		<td>할인점코드</td>
		<td>점포명</td>
		<td>주문번호</td>
		<td>주문일자</td>
		<td>제품코드</td>
		<td>제품평</td>
		<td>주문수량</td>
		<td>단가</td>
		<td>소비자가격</td>
		<td>할인가격</td>
	</thead>
	<!-- 반복의 시작 -->
	<c:forEach var="newtbl" items="${list}">
	<tr>
		<td>${newtbl.shopno }</td><td>${newtbl.shopname }</td><td>${newtbl.orderno}</td><td>${newtbl.orderdate}</td><td>${newtbl.pcode}</td>
		<td>${newtbl.pname }</td><td>${newtbl.amount }</td><td>${newtbl.cost }</td><td>${newtbl.hopeprice }</td><td>${newtbl.ondiscount }</td>
	</tr>
	</c:forEach>
	<!-- 반복의 끝 -->
</table>
</body>
</html>
```
