# SQL

# Select Another Server Database Table

    exec sp_helpserver --Display all server
    
    exec sp_addlinkedserver @server = '192.168.160.2' --Add a server to local
    
    EXEC sp_addlinkedsrvlogin 
      @rmtsrvname = '192.168.160.2', 
      @locallogin = 'sa', 
      @rmtpassword = 'passw0rd'
      
    select * from itemhelpinfo ihi
    left join [192.168.160.2].[dataplanet].dbo.image i on i.isbn = ihi.isbn13
    where i.isbn is null
