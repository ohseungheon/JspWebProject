# 로그인 기능 구현

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>


<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Login Page</title>
</head>
<body>
	<% String error=request.getParameter("error");  
		pageContext.setAttribute("error", error);
	%>    
    <h2>Login</h2>
    <form action="loginProcess.jsp" method="post">
        Username: <input type="text" name="username"><br>
        Password: <input type="password" name="password"><br>
        <input type="submit" value="Login">
    </form>
	<c:if test="${error eq 'true'}">
		<p style="color:red; font-size: 10px;">아이디와 패스워드를 다시 확인해주세요</p>
	</c:if>
</body>

</html>
```
```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@ page import="java.util.Map,java.util.HashMap" %>
<%
    // 예시로 사용자 정보를 하드코딩하여 체크
    String username = request.getParameter("username");
    String password = request.getParameter("password");
    
    // 실제로는 데이터베이스에서 사용자 정보를 조회하여 체크해야 함
    
    // 사용자 정보가 올바른 경우 세션에 사용자 정보 저장
    if ("john".equals(username) && "password123".equals(password)) {
        // 세션에 사용자 정보 저장
        session.setAttribute("username", username);
        response.sendRedirect("welcome.jsp"); // 로그인 성공 시 환영 페이지로 이동
    } else {
        // 로그인 실패 시 다시 로그인 페이지로 이동
        response.sendRedirect("login.jsp?error=true");
    }
%>
```

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@ page import="java.util.Map,java.util.HashMap" %>
<%
    // 세션 종료
    session.invalidate();
    response.sendRedirect("login.jsp");
%>

```


```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Welcome Page</title>
</head>
<body>
    <h2>Welcome</h2>
    <%-- 세션에서 사용자 정보 가져오기 --%>
    <% String username = (String) session.getAttribute("username"); %>
    <%-- 환영 메시지 출력 --%>
    <p>Welcome, <%= username %>!</p>
    <a href="logout.jsp">Logout</a>
</body>
</html>

```
