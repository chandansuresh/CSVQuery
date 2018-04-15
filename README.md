# CSVQuery
java program to upload a sql content into CSV file


package com.cointheta.internshala ;
import java.io.FileReader ;
import java.sql.connection;
import java.sql.PreparedStatement ;
import java.sql.Statement;

Import com.opencsv.CSVReader ;

public class Importcsv
{
public static void main(String [] args )
{
readCsv();
}
}
 
 private static void readCsv ()
 {
    try (CSVReader reader = new CSVReader(new FileReader("upload.csv"), ','); 

    Connection connection = DBConnection.getConnection();
   {
      String insertQuery = "Insert into tbl (name ,id, addr,cont_no) values (null,?,?,?)";  
	   PreparedStatement pstmt = connection.prepareStatement(insertQuery);
	   
	    while((rowData = reader.readNext()) != null)
	{
		System.out.println("Data Successfully Uploaded");
	}

   }
 catch (Exception e)
        {
                e.printStackTrace();
        }
 }
