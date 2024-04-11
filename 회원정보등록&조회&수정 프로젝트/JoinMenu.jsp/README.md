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
        background-color: #f0f0f0;
    }

    form {
        background-color: #fff;
        border-radius: 5px;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        padding: 20px;
        margin: 50px auto;
        max-width: 400px;
    }

    h1 {
        text-align: center;
    }

    input[type="text"], input[type="submit"] {
        width: 100%;
        padding: 10px;
        margin-bottom: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
        box-sizing: border-box;
    }

    input[type="submit"] {
        background-color: #4CAF50;
        color: white;
        border: none;
        cursor: pointer;
    }

    input[type="submit"]:hover {
        background-color: #45a049;
    }

    .error-message {
        color: red;
        margin-top: 5px;
    }

</style>
</head>
<body>
<form action="join" method="post">
회원번호(자동발생)<input type="text" id ="custno" name="info" value= "100007"><br>
회원성명<input type="text" id ="name" name="info" ><br>
회원전화<input type="text" id ="phone" name="info"><br>
회원주소<input type="text" id ="addr" name="info"><br>
가입일자<input type="text" id ="date" name="info"><br>
고객등급(A:vip,B:일반,C:직원)<input type="text" id ="grade" name="info"><br>
거주도시<input type="text" id ="city" name ="info"><br>
<input type="submit"  id = "submit" value="등록">

</form>

<a href = "search">링크이동</a>
<form action = "search" method="post" >
<input type="submit" id = "search" value="조회">
</form>


</body>
<script>

	//Integer result = (Integer) session.getAttribute("result");
//	if (result != null){
	//	pageContext.setAttribute("result", result);
//}else{
//		result=0;
//	}
	let result = <%= request.getAttribute("result") %>

	
	let submit = document.getElementById("submit");
	let nameInput = document.getElementById('name');
	submit.addEventListener('click', showAlert);
	search.addEventListener('click', function(event) {
	    //event.preventDefault();
	});
    // 알림 표시 함수
    function showAlert() {
		 let search = document.getElementById("search");
    	 let nameValue = nameInput.value.trim();
         if (nameValue === "") {
        	 	console.log("-------"+result)
             alert("회원 이름을 입력해주세요!");
             nameInput.focus();
             event.preventDefault();
         }
         if(result==1){
        	 
        	 alert("등록성공!");
         }else  {
             alert("등록 실패!");
         }
         
    }
</script>
</html>
```
