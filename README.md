- 👋 Hi, I’m @HtutLin-Htet
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
HtutLin-Htet/HtutLin-Htet is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html>
<head>
<meta charset="ISO-8859-1">
<title>Insert title here</title>
</head>
<body>
  <h3>Order Form</h3>
    <form action="ShowItem" method="get">
      New Item to Order &nbsp;
      <input type="text" name="newItem"><br><br>
      <input type="submit" value="Order and Show All Purchases"><br>
    </form>
</body>
</html>

HttpSession session=request.getSession(true);
    ArrayList<String>previousItems=(ArrayList<String>)session.getAttribute("previousItems");
    if(previousItems==null) {
      previousItems=new ArrayList<String>();
      session.setAttribute("previousItems", previousItems);
    }
    String newItem=request.getParameter("newItem");
    if((newItem!=null)&&!newItem.trim().equals(" "))
      previousItems.add(newItem);
    response.setContentType("text/html");
    PrintWriter out=response.getWriter();
    String title="Item Purchased";
    out.println("<html><body bgcolor=\"#FDF5E6\">\n"+"<h1>"+title+"</h1>");
    if(previousItems.size()==0) {
      out.println("No Items");
    }else {
      out.println("<ul>");
      for(String item:previousItems) {
        out.println("<li>"+item+"</li>");
      }
      out.println("</ul>");
    }
    out.println("</body></html>");

    <display-name>SessionEg1</display-name>
  <servlet>
    <servlet-name>ShowItem</servlet-name>
    <servlet-class>sessionEg.ShowItem</servlet-class>
  </servlet>
  <servlet-mapping>
    <servlet-name>ShowItem</servlet-name>
    <url-pattern>/ShowItem</url-pattern>
  </servlet-mapping>
  <welcome-file-list>
    <welcome-file>OrderForm.html</welcome-file>
    <welcome-file>ShowItem.java</welcome-file>
  </welcome-file-list>


  Student Registration

  <!DOCTYPE html>
<html>
<head>
<meta charset="ISO-8859-1">
<title>Insert title here</title>
</head>
<body>
  <form action="StudentServlet" method="get">
    <h2><center>Student Registration</center></h2>
    <table>
      <tr>
      <td>Name:</td>
      <td><input type="text" name="txtName"></td>
      </tr>
      <tr>
      <td>Gender:</td>
      <td><input type="radio" name="rdoGender" value="Male">Male
      <input type="radio" name="rdoGender" value="Female">Female</td>
      </tr>
      <tr>
      <td>NRC:</td>
      <td><input type="text" name="txtNRC"></td>
      </tr>
      <tr>
      <td>Father Name:</td>
      <td><input type="text" name="txtFname"></td>
      </tr>
      <tr>
      <td>Address:</td>
      <td><textarea name="txtAdd"></textarea></td>
      </tr>
      <tr>
      <td>Phone:</td>
      <td><input type="text" name="txtPh"></td>
      </tr>
      <tr>
      <td colspan="2"><center><input type="submit" value="Submit"></center></td>
      </tr>
    </table>
  </form>
</body>
</html>

HttpSession session=request.getSession();
    String s=(String)session.getAttribute("id");
    int n=0;
    if(s==null || s.length()==0)
      n=1;
    else
      n=Integer.parseInt(s);
    session.setAttribute("id", String.valueOf(n+1));
    String name=request.getParameter("txtName");
    String gender=request.getParameter("rdoGender");
    String nrc=request.getParameter("txtNRC");
    String fname=request.getParameter("txtFname");
    String add=request.getParameter("txtAdd");
    String phone=request.getParameter("txtPh");
    PrintWriter pw=response.getWriter();
    pw.println("Student ID: UCS-"+n);
    pw.println("Name: "+name);
    pw.println("Gender: "+gender);
    pw.println("NRC:"+nrc);
    pw.println("Father: "+fname);
    pw.println("Address:"+add);
    pw.println("Phone:"+phone);

<display-name>SessionEg2</display-name>
  <servlet>
    <servlet-name>StudentServlet</servlet-name>
    <servlet-class>sessionEg.StudentServlet</servlet-class>
  </servlet>
  <servlet-mapping>
    <servlet-name>StudentServlet</servlet-name>
    <url-pattern>/StudentServlet</url-pattern>
  </servlet-mapping>
  <welcome-file-list>
    <welcome-file>Student.html</welcome-file>
    <welcome-file>StudentServlet.java</welcome-file>
  </welcome-file-list>
  
