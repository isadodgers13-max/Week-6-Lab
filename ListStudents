@WebServlet(urlPatterns = "/students", loadOnStartup = 1)
public class ListStudents extends HttpServlet {

    @Override
    public void init() throws ServletException {
        List<Student> students = new ArrayList<>();
        students.add(new Student("Josh", 1, 7, "Minnows", "10am", "9am"));
        students.add(new Student("Eva", 1, 6, "Minnows", "10am", "1pm"));
        students.add(new Student("Lucy", 1, 4, "Starfish", "1pm", "2pm"));
        students.add(new Student("Matt", 2, 8, "Dolphins", "9am", "2pm"));

        getServletContext().setAttribute("students", students);
    }

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp)
            throws ServletException, IOException {

        resp.setContentType("text/html");
        PrintWriter out = resp.getWriter();

        out.println("<h2>Students | <a href='register'>Register</a></h2>");

        List<Student> students = (List<Student>) getServletContext().getAttribute("students");

        out.println("<table border='1'>");
        out.println("<tr><th>Name</th><th>Session</th><th>Age</th><th>Level</th><th>Time (1st Choice)</th><th>Time (2nd Choice)</th></tr>");
        for (Student s : students) {
            out.println("<tr>");
            out.printf("<td>%s</td><td>%d</td><td>%d</td><td>%s</td><td>%s</td><td>%s</td>",
                    s.getName(), s.getSession(), s.getAge(), s.getLevel(), s.getTime1(), s.getTime2());
            out.println("</tr>");
        }
        out.println("</table>");
    }
}
