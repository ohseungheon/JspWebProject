```java

package servlet;

import java.io.IOException;
import java.io.PrintWriter;

import javax.servlet.ServletContext;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import com.oreilly.servlet.MultipartRequest;
import com.oreilly.servlet.multipart.DefaultFileRenamePolicy;

import dao.ProductDao;

/**
 * Servlet implementation class productWriteServlet
 */
@WebServlet("/productWrite.do")
public class productWriteServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
	ProductDao pdao = new ProductDao();
	
	protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		//String[] paramArr = request.getParameterValues("regInfo");
		request.setCharacterEncoding("utf-8");
		response.setContentType("text/html;charset=utf-8");
		
		PrintWriter out = response.getWriter();
		
		String savePath = "upload";
		int uploadFileSizeLimit=5*1024*1024;
		String encType="utf-8";
		
		ServletContext context =getServletContext();
		String uploadFilePath = context.getRealPath(savePath);
		System.out.println("서버상의 실제 디렉:");
		System.out.println(uploadFilePath);
		
		
		MultipartRequest multi = new MultipartRequest(
				request,
				uploadFilePath,
				uploadFileSizeLimit,
				encType,
				new DefaultFileRenamePolicy()
				);
		String fileName =multi.getFilesystemName("regInfo");
		System.out.println("------------filename: "+fileName);
		String[] paramArr= multi.getParameterValues("regInfo");
		System.out.println("--------------------start");
		
		
		for(int i=0;i<paramArr.length;i++) {
			System.out.println(paramArr[i]);
		}
		String[] paramArr2=new String[5]; 
		paramArr2[0]= paramArr[0];
		paramArr2[1]= paramArr[1];
		paramArr2[2]= paramArr[2];
		paramArr2[3]= fileName;
		paramArr2[4]= paramArr[3];
		int result = pdao.regProd(paramArr2);
		
		if(result ==1) {
			System.out.println("등록성공");
			response.sendRedirect("productList.do");
		}else {
			System.out.println("등록실패");
		}
	}

}



```
