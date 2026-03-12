program:

package com.klef.fsad.exam;

import javax.persistence.*;
import java.util.Date;

@Entity                 // Marks this class as a Hibernate entity (mapped to a table)
@Table(name="course")  // Specifies the table name in the database
public class Course 
{
    @Id   // Declares this field as the primary key of the table
    @GeneratedValue(strategy = GenerationType.IDENTITY)  
    // Automatically generates ID values using database auto-increment
    private int id;

    @Column(name="name")  // Maps this variable to the 'name' column in the table
    private String name;

    @Column(name="description") // Maps this variable to 'description' column
    private String description;

    @Temporal(TemporalType.DATE) 
    // Tells Hibernate to store only the DATE part (not time)
    private Date date;

    @Column(name="status") // Maps to 'status' column
    private String status;

    // Default constructor (required by Hibernate)
    public Course() {}

    // Parameterized constructor
    public Course(String name,String description,Date date,String status)
    {
        this.name=name;
        this.description=description;
        this.date=date;
        this.status=status;
    }

    // Getter and Setter methods
    public int getId() 
    {
        return id;
    }

    public String getName() 
    {
        return name;
    }

    public void setName(String name) 
    {
        this.name = name;
    }

    public String getDescription() 
    {
        return description;
    }

    public void setDescription(String description) 
    {
        this.description = description;
    }

    public Date getDate() 
    {
        return date;
    }

    public void setDate(Date date) 
    {
        this.date = date;
    }

    public String getStatus() 
    {
        return status;
    }

    public void setStatus(String status) 
    {
        this.status = status;
    }
}
