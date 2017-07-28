package DBM;

public class ProjectListQuery
{
    
    public String getProjectListQuery()
    {
        String query = "SELECT p.id, p.projectcommonname, p.nspprojectname, concat(u.givenname, \" \", u.surname) AS name\n" +
        "FROM pworeg_project p\n" +
        "JOIN fos_user u\n" +
        "ON p.manager=u.id;";
        return query;
    }
    
    public String getProjectList_IDQuery(String ID)
    {
        String query = "SELECT p.id, p.projectcommonname, p.nspprojectname, concat(u.givenname, \" \", u.surname) AS name\n" +
        "FROM pworeg_project p\n" +
        "JOIN fos_user u\n" +
        "ON p.manager=u.id\n" +
        "WHERE p.id=" + ID + ";";
        return query;
    }
    
    public String getProjectList_CommonNameQuery(String CommonName)
    {
        String query = "SELECT p.id, p.projectcommonname, p.nspprojectname, concat(u.givenname, \" \", u.surname) AS name\n" +
        "FROM pworeg_project p\n" +
        "JOIN fos_user u\n" +
        "ON p.manager=u.id\n" +
        "WHERE p.projectcommonname LIKE '%" + CommonName + "%';";
        return query;
    }
    
    public String getProjectList_ProjectNameQuery(String ProjectName)
    {
        String query = "SELECT p.id, p.projectcommonname, p.nspprojectname, concat(u.givenname, \" \", u.surname) AS name\n" +
        "FROM pworeg_project p\n" +
        "JOIN fos_user u\n" +
        "ON p.manager=u.id\n" +
        "WHERE p.nspprojectname LIKE '%" + ProjectName + "%';";
        return query;
    }
    
    public String getProjectList_ManagerQuery(String Manager)
    {
        String query = "SELECT p.id, p.projectcommonname, p.nspprojectname, concat(u.givenname, \" \", u.surname) AS name\n" +
        "FROM pworeg_project p\n" +
        "JOIN fos_user u\n" +
        "ON p.manager=u.id\n" +
        "WHERE concat(u.givenname, \" \", u.surname) LIKE '%" + Manager + "%';";
        return query;
    }
    
}
