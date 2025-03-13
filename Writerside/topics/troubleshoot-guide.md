# Troubleshoot Guide

>FAQs for installing Cafe Variome

## Installation Errors

>Running composer CVInstall command returns an error
> {style="warning"}

**Problem Description**: The `composer CVInstall` command is the final step in the installation process for Cafe Variome. It should set up Cafe Variome successfully on your local environment if all the requirements listed at System Requirements are met and you've followed the installation process outlined in Installing Cafe Variome page. If you encounter an error while running this command, follow these steps to troubleshoot the issue:

* **Install required PHP Extensions**: Ensure that you have installed all the necessary PHP extensions as mentioned in the provided link, along with other required software such as Composer, Neo4j, and Elasticsearch. Here is a list of the required PHP modules:

  * bcmath 
  * 
  * curl
  * 
  * fileinfo
  * 
  * gd
  * 
  * intl
  * 
  * json
  * 
  * mbstring
  * 
  * mysql
  * 
  * sockets
  * 
  * sodium
  * 
  * xml
  * 
  * zlib 

  You can verify if these modules are enabled by running the following command: 

      php -m

Alternatively, you can create a `phpinfo.php` file to check the enabled modules.

* **Move Project Folder to Apache Server Root:** Ensure that you have moved the Cafe Variome project folder to the Apache server's root location, which is typically under `/var/www/html`, as specified in the `apache2.conf `file.

* **Configure MySQL Database:** Make sure you have created and provided an empty database in the .env file. It is also recommended to create a separate MySQL user and password for this database with the necessary permissions. You can achieve this using MySQL commands like:

    CREATE USER 'yourUserName'@'localhost' IDENTIFIED BY 'yourPassword';
    GRANT ALL PRIVILEGES on yourDatabaseName.* to 'yourUserName'@'localhost';
    FLUSH PRIVILEGES;

* **Modify .env File:** Update the content in the template .env file with your application's BaseURL and database details, and then save the file as .env.

* **Run Composer Commands:** Open a terminal and navigate to the root directory of your Cafe Variome project. Run the following commands:
    
    composer install
    composer CVInstall

* **Provide Installation Details:** During the installation process, you will be prompted to provide an installation key, network URL, and your admin password as specified in the Cafe Variome installation documentation.

By following these steps, you should be able to troubleshoot any errors encountered while running the `composer CVInstall` command and complete the Cafe Variome installation successfully.

>PHP error encountered while running composer CVInstall
>{style="warning"}

**Problem Description:** When running the composer CVInstall command, you may encounter the following error message: **"PHP Fatal error: Uncaught TypeError: array_merge(): Argument #1 must be of type array, bool given in /usr/share/php/Composer/Config.php:191"**. To resolve this error, follow these steps:

**Install Composer from Official Source:** To avoid this error, download and install Composer from the official source by following the instructions provided at the following link: https://getcomposer.org/download/.

If you have previously installed Composer using `sudo apt install composer`, you can resolve this issue by making changes to the composer.json file provided within Cafe Variome. Follow these steps:

1. Locate your composer.json file in your Cafe Variome project directory.
2. Open the composer.json file in a text editor.
3. Look for the line that reads "allow-plugins": false in the JSON file.
4. Modify it to read "allow-plugins": { "test/plugin": true }

Here's what it should look like after modification:

    "config": {
    ...
    "allow-plugins": { "test/plugin": true },
    ...
    }

Save the `composer.json` file after making this change.

By following these steps, you should be able to resolve the error you encountered while running the `"composer CVInstall"` command.

>Blank white screen after successful installation or 404 Not Found Error`
>{style="warning"}

**Problem Description:** After successfully installing Cafe Variome, if you see a blank page in your web browser or encounter a "404 Not Found" error when visiting the URL you set in the .env file, follow these steps to troubleshoot the issue:

**Ensure Folder Access:** Make sure your Cafe Variome folder is accessible by your user. If not, you can use the following command to grant access (if you're using Linux-based machine):

    sudo chown -R $USER /var/www/html/YourCafeVariomeFolder

**Check Apache Configuration:** If the above command doesn't resolve the issue, you may need to verify your Apache web server configuration. Follow these steps:

1. Open your Apache configuration file, often located at `/etc/apache2/apache2.conf.`
2. Look for the configuration directives related to your root folder, which is typically `/var/www/html.`
3. Ensure that the `AllowOverride` directive is set to **AllowOverride All** instead of **AllowOverride None**.
4. Ensure that the configuration within the `<Directory /var/www> `block looks like this


    ```
    ...
    <Directory /var/www>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
    ...
    ```


`Make sure to save your changes and restart Apache for them to take effect.`

By following these steps and ensuring that your Apache configuration matches the provided example, you should be able to address the blank white screen or 404 Not Found error and get Cafe Variome up and running correctly.

>Error After Clicking Login on the Landing Page
>{style="warning"}

**Problem Description:** If you can access the landing page (http://localhost/YourCafeVariomeBaseURL/) but encounter a 404 error when clicking on the login link, it may be due to the mod_rewrite module being disabled in Apache. Follow these steps to resolve the issue:

1. **Verify Mod_Rewrite is Disabled:** To check if mod_rewrite is disabled, go to http://localhost/YourCafeVariomeBaseURL/index.php/auth/login/ in your web browser. If you can see the login page at this URL, the issue is likely because mod_rewrite is disabled.

   3. **Enable Mod_Rewrite:** To enable the mod_rewrite module in Apache, follow these steps:

       1. Open a terminal window.
       2. To enable the mod_rewrite module, use the a2enmod command, which is a tool provided by Apache to enable various modules. Run the following command:
      

               sudo a2enmod rewrite

You will likely be prompted to enter your system password to authorise the change.

4. **Restart Apache**: After enabling mod_rewrite, you should restart the Apache web server to apply the changes. Use the following command:

        sudo systemctl restart apache2

5.**Access Cafe Variome:** Once Apache has been restarted, try accessing Cafe Variome again by visiting the landing page and clicking on the login link (http://localhost/YourCafeVariomeBaseURL/). You should no longer encounter the 404 error, and the login page should display correctly.

By following these steps, you can resolve the issue of encountering a 404 error when clicking the login link on the Cafe Variome landing page due to the mod_rewrite module being disabled in Apache.

# Dashboard Errors

>Communication Problem with Network Software in Administrator Dashboard`
>{style="warning"}

**Problem Description:** In the Administrator Dashboard, a red banner with the message **"There was a problem in communicating with network software. Please fix it as the system is unable to function correctly"** appears. To troubleshoot this issue, follow these steps:

**Check Authorization Server URL:** Click on "Settings" in the side navigation to open the 'System Settings' page. This page allows you to edit the Main System Settings. Double-check that the 'Authorization Server URL' field is set to https://network.discoverynexus.org/. If it's not, change it to the correct URL and save the settings. Then, go to the Dashboard to verify if the error is resolved.

**Validate Installation Key:** If the error persists after updating the 'Authorization Server URL,' make sure you have a valid Installation Key provided by the Cafe Variome team. Additionally, ensure that this installation key has been generated from the correct Authorization Server URL (https://network.discoverynexus.org/). Input the correct Installation Key and save the settings.

`Do not change the 'Authorization Server URL' and Installation Key unless you are facing the communication error described above.`

By following these steps, you should be able to troubleshoot and resolve the issue related to communication problems with the network software in the Administrator Dashboard.

>Elasticsearch Not Running Error in Administrator Dashboard
>{style="warning"}

**Problem Description:** After successfully installing and logging into Cafe Variome, you may encounter an error in the Administrator Dashboard that states, "Elasticsearch is not running. The query interface is not accessible. Please ask the server administrator to start it." This error indicates that Elasticsearch might not be running or the installation was unsuccessful. Follow these steps to resolve the issue:

* **Download Elasticsearch Zip or Tar.gz File**: Instead of installing the .deb file, download the Elasticsearch zip or tar.gz file from the official Elasticsearch website (https://www.elastic.co/downloads/elasticsearch) and save it to a directory of your choice, such as /opt.

* **Set Java Path in .bashrc:** To properly set the Java path, follow these instructions:

    * Open a terminal window.

    * Edit the .bashrc file using a text editor. You can use the nano text editor as an example: 

    `  nano ~/.bashrc`

    * Add the following line to set the Java path. Make sure to replace /path/to/your/java with the actual path to your Java installation: 
 
    `export JAVA_HOME=/path/to/your/java`

    * Save the changes and exit the text editor.

    * To apply the changes to your current terminal session, either close and reopen the terminal or run the following command:

  ` source ~/.bashrc`

  * **Start Elasticsearch**: Now that you have set the Java path, navigate to the directory where you copied the Elasticsearch zip or tar.gz file (e.g., /opt/yourelasticsearchfolder). Run Elasticsearch using the following command:

          ES_JAVA_OPTS="-Xms1g -Xmx1g" ./bin/elasticsearch

This command starts Elasticsearch with a minimum heap size of 1GB and a maximum heap size of 1GB. Adjust these values according to your system's resources if necessary.

By following these steps, you should be able to download and run Elasticsearch successfully, resolving the error in the Administrator Dashboard related to Elasticsearch not running.

>Neo4j Not Running Error in Administrator Dashboard
>{style="warning"}

Problem Description: After successfully installing and logging into Cafe Variome, as well as completing the installation of Neo4j, you encounter an error in the Administrator Dashboard that states, "Neo4J is not running. Some capabilities of the system are disabled because of this. Please ask the server administrator to start it." This error indicates that Neo4j might not be running or that the password needs to be updated. Here's how to resolve it:

* **Verify Neo4j Status**: Start by confirming whether Neo4j is running. Open a web browser and navigate to **[http://localhost:7474/](http://localhost:7474/)**. If this is your first visit, you will be prompted to log in with the following credentials:

  * Username: neo4j
  
  * Password: neo4j

Once logged in, you will be asked to set a new password for your Neo4j instance.

* **Set Neo4j Password**: After setting a new password for Neo4J, go to the Neo4J Settings section within the Settings menu in the side navigation of your Administrator Dashboard. Edit the "Neo4J Password" field with the password you've just set in the Neo4j interface.
* **Save Settings**: Make sure to save the changes to the Neo4J Password field.

This should resolve the Neo4j error in your Cafe Variome Administrator Dashboard. The error was likely caused by either Neo4j not running or an outdated password, and these steps will ensure that the password is updated and the Neo4j service is properly configured.