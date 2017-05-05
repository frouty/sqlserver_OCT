# sqlserver_OCT
debogage OCT

pour trouver le port sur lequel le serveur tourne : `netstat -a -b`

# dans ce lien
http://www.exforsys.com/tutorials/sql-server-2005/sql-server-configuration-manager.html

On trouve des infos sur l'utilisation de *SQL server configuration manager*
# dans ce lien
https://support.microsoft.com/en-us/help/4009936/solving-connectivity-errors-to-sql-server  
On trouve des info pour troubleshooter en interactif.

# dans ce lien
https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/troubleshoot-connecting-to-the-sql-server-database-engine  
on y trouve des infos pour troubleshooter le msg d'erreur:  

"A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections."

# SQL server Configuration manager
On peut Start Stop Pause or Resume SQL server services comme: 
- SQL Server Database Engine Services, 
- SQL Server Agent Service, 
- SQL Server Browser Services
- etc. 

- Pour ouvrir le SQL server configuration manager pour le SQL server 2005:
  - SQLSERVERMANAGER.msc
  - ou All Programs / Microsoft SQL server / configuration tools / SQL server configuration manager.
# SQL server Management Studio
On peut soit:
- 1 All Programs / Microsoft SQL Server / SQL Server Management Studio
- 2 Run / SSMS.exe / OK

# Pour démarrer l'instance par défault de SQL server
- 1 Ouvrir le SQL server configuration manager pour le SQL server 2005:
  - SQLSERVERMANAGER.msc
  - ou All Programs / Microsoft SQL server / configuration tools / SQL server configuration manager.
- 2 In SQL server configuration manager / expand *services* / click *SQL Server*
- 3 dans le panneau de droite : right-click SQL Server (MSSQLServer) / clik *Start*
- 4 une fleche verte indique que le service tourne correctement.

## Comment récuperer des infos sur l'instance du SQL server.

- Start SQL server configuration manager 
  - comment démarrer *SQL server configuration manager*: je ne sais pas
  - dans le panneau de gauche / SQL server services
  - dans la panneau de droite confirmer que l'instance de Database engine est presente et tourne. une instance nommée SQL Server (MSSQLSERVER) est une instance par défaut. SQL Server Express utilise le nom SQL server (SQLEXPRESS) comme nom d'instance. A moins que ce nom ait été changé lors de l'installation.
  - noter le nom de cette instance.
  - et aussi confirmez que l'instance est running: fleche verte.
  - Si l'instance à un carre rouge click-droit sur l'instance then click start. 
  - il faut aussi s'assurer que le SQL server browser service is running. (lancer le SQL Server configuration manager
  
- En utilisant le *SQL server management studio*. Se connecter à l'instance du SQL server:
  - dans *Object Explorer* / expand *Management* / expand *SQL server logs* / double click le log courant.
  - dans le log viewer click filter button sur la barre d'outil
  - *Message contains text* box: taper *server is listening to* / Apply / OK
 - Tester une connection en local
  - il faut SQL Server Management Studio (ssMS). On peut aussi utiliser les commandes de `sqlcmd.exe`
  - All programs / Microsoft SQL server / SQL server MAnagement Studio
  - In the *connect to server* dialog box /  in *Server* type box / select *Database engine*
  - In the authentification box / select *Windows authentification*
  - In the *server name* box / taper:
    - 1 *le nom du computer* pour une instance par default
    - 2 ou *le computer name/instance name*
  - Si on a un msg d'erreur il va falloir debogger:
    - pour voir les informations completes sur les erreurs voir le SQL Server Error log. que l'on peut parfois trouver à :
    `C:\Program Files\Microsoft SQL Server\MSSQL13.MSSQLSERVER\MSSQL\Log\ERRORLOG`

# Utilisation de SQL Server Management Studio
