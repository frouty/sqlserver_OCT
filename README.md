# sqlserver_OCT
debogage OCT

pour trouver le port sur lequel le serveur tourne : `netstat -a -b`

# dans ce lien
https://support.microsoft.com/en-us/help/4009936/solving-connectivity-errors-to-sql-server  
On trouve des info pour troubleshooter en interactif.

# dans ce lien
https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/troubleshoot-connecting-to-the-sql-server-database-engine  
on y trouve des infos pour troubleshooter le msg d'erreur:  

"A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections."



## Comment récuperer des infos sur l'instance du SQL server.

- Start SQL server configuration manager 
  - comment démarrer *SQL server configuration manager*: je ne sais pas
  - dans le panneau de gauche / SQL server services
  - dans la panneau de droite confirmer que l'instance de Database engine est presente et tourne. une instance nommée SQL Server (MSSQLSERVER) est une instance par défaut. SQL Server Express utilise le nom SQL server (SQLEXPRESS) comme nom d'instance. A moins que ce nom ait été changé lors de l'installation.
  - noter le nom de cette instance.
  - et aussi confirmez que l'instance est running: fleche verte.
  - Si l'instance à un carre rouge click-droit sur l'instance then click start. 
  - il faut aussi s'assurer que le SQL server browser service is running.
  
  -
