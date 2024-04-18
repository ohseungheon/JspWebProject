```java


package servlet;

import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import dao.ProductDao;

@WebServlet("/productDlete.do")
public class productDeleteServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;

	ProductDao pdao = new ProductDao();

	protected void service(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {
		int pcode = Integer.valueOf(request.getParameter("pcode"));
		int result = pdao.delete(pcode);

		if (result == 1) {
			response.sendRedirect("productList.do");
		}
	}

}


```
