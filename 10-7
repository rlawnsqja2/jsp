<%@ page language="java" contentType="text/html; charset=EUC-KR"
    pageEncoding="EUC-KR"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Insert title here</title>
</head>
<body>
	<%@ page import="java.sql.*, javax.sql.*, javax.naming.*" %>
	<h2>데이터베이스 univdb의 테이블 student에 학생 삽입프로그램</h2>
	
	<hr><center>
	<h2>학생삽입</h2>
	
	<%
		Connection con = null;
		PreparedStatement pstmt = null;
		Statement stmt = null;
		StringBuffer SQL = new StringBuffer("insert into student");
		SQL.append("values  (?,?,?,?,?,?,?,?,?,?)");
		String name = "전미정";
		
		try{
			Context initCtx = new InitialContext();
			Context env  (Context) initCtx.lookup("java:comp/env/");
			DataSource ds = (DataSource) env.lookup("jdbc/mysql");
			con = ds.getConnection();
			
			pstmt = con.prepareStatement(SQL.toString());
			//삽입할 학생 레코드 데이터 입력
			pstmt.setString(1, "DBCP");
			pstmt.setString(2, "commons");
			pstmt.setString(3, "name");
			pstmt.setInt(4,2010);
			pstmt.setString(5, "1039653");
			pstmt.setString(6, "전산정보과");
			pstmt.setString(7, "011");
			pstmt.setString(8, "2398-9750");
			pstmt.setString(9, "인천시");
			pstmt.setString(10, "dbcp@gmail.com");
			int rowCount = pstmt.executeUpdata();
			if(rowCount==1) out.println("<hr>학생 ["+name+"] 레코드 하나가 성공적으로 삽입 되었습니다.<hr>");
			else out.println("학생 레코드 삽입에 문제가 있습니다.");
			
			//다시 학생 조회
			stmt = con.createStatement();
		}
	%>
 //미완
	</center>
</body>
</html>
