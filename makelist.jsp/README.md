```jsp
<%@page import="dto.Member"%>
<%@page import="java.util.ArrayList"%>
<%@page import="java.sql.ResultSet"%>
<%@page import="java.sql.Statement"%>
<%@page import="java.sql.DriverManager"%>
<%@page import="java.sql.Connection"%>
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
 
<%@taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core"%>
<%

%>
	
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Member List</title>
 <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }

        h1 {
            text-align: center;
            margin-top: 30px;
            color: #333;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        th,
        td {
            padding: 10px;
            text-align: center;
        }

        th {
            background-color: #4CAF50;
            color: white;
        }

        tr:nth-child(even) {
            background-color: #f2f2f2;
        }

        tr:hover {
            background-color: #ddd;
        }
    </style>
</head>

<body>
<h1>회원목록</h1>
<hr>
<table border="1">

	<thead>
	<tr>
		<th>회원번호</th><th>회원성명</th><th>회원전화</th><th>회원주소</th><th>가입일자</th><th>고객등급</th><th>거주도시</th>
	</tr>
	</thead>
	
	
	<tbody>
	
	<!-- 반복시작 -->
	<c:forEach var="member" items="${list}" >
	
	<tr>
		<td><a href = "update.jsp"?custname=${member.custname }>${member.custno}</td></a>
		<td>${member.custname }</td>
		<td>${member.phone }</td>
		<td>${member.address }</td>
		<td>${member.date }</td>
		<td>${member.grade }</td>
		<td>${member.city }</td>
		
	</tr>

	<!-- 반복끝 -->
	</c:forEach>
	
	</tbody>


</table>

</body>

</html>

```
