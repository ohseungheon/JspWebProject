```java
package servlet;

import java.io.IOException;
import java.util.ArrayList;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;

import dao.ProductDao;
import dto.Product;

/**
 * Servlet implementation class productListServlet
 */
@WebServlet("/productList.do")
public class productListServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;

	ProductDao pdao = new ProductDao();

	protected void service(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {
		
		HttpSession session = request.getSession();
		
		int grade = (Integer)session.getAttribute("result");
		System.out.println("check grade-----------------------------"+grade);
		if (grade==1) {
			ArrayList<Product> list = pdao.showTable();
			request.setAttribute("list", list);
			request.getRequestDispatcher("./admin/productList.jsp").forward(request, response);
		}
		
		if (grade==2) {
			ArrayList<Product> list = pdao.showTable();
			request.setAttribute("list", list);
			request.getRequestDispatcher("./member/productList.jsp").forward(request, response);
		}
	}

}

```
