# Installing Cafe Variome

>The installation guide for Linux-based systems.

## Overview

Cafe Variome can be easily installed through Composer. To get started for installing Cafe Variome after meeting the installation requirements, get a copy of the software, by either downloading the compressed version suitable to your environment from our list of releases or using docker or clone our repository as follows:

    git clone https://github.com/Cafe-Variome/CafeVariome.git
    mv CafeVariome/ YourProjectName/
    cd YourProjectName

    
## Preparing for installation

To prepare the server for installing Café Variome, create a MySQL (or MariaDB) database with a user account which has access to the created database.

Make note of the URL or IP address of the server that you want to point to the Café Variome installation.

## Installation Key

To function properly as an instance, Café Variome needs to have a valid installation key. The installation key is a unique string of characters and numbers, that will be provided by our team.

## Installation Checklist

* Valid Installation Key (provided by our team)
* 
* URL or IP Address of the base server
* 
* MySQL/MariaDB Database
* 
* Database credentials (username and password)
* 
* Database hostname (usually it is localhost; if the address is on a separate server - the address of the server)
* 
* Path to PHP binary on the server

## Configuring env template

The above checklist can be used to make sure you have everything ready for installing Cafe Variome. All these values will need to be placed in a .env file that will automatically be read by Cafe Variome on initialisation.

The following env template file comes with the packaged Cafe Variome. To make it accessible to the CodeIgniter framework, modify the contents of this template with your values and rename it to .env. This declares default environment variables to be used by Cafe Variome.
        
        #.env
        #--------------------------------------------------------------------
        # Example Environment Configuration file
        #
        # This file can be used as a starting point for your own
        # custom .env files, and contains most of the possible settings
        # available in a default install.
        #
        # By default, all of the settings are commented out. If you want
        # to override the setting, you must uncomment it by removing the '#'
        # at the beginning of the line.
        #--------------------------------------------------------------------
        
        #--------------------------------------------------------------------
        # ENVIRONMENT
        #--------------------------------------------------------------------
        
        CI_ENVIRONMENT = development
        
        #--------------------------------------------------------------------
        # APP
        #--------------------------------------------------------------------
        
        app.baseURL = 'http://localhost/dummy_cv/'
        #app.forceGlobalSecureRequests = true
        
        #app.sessionDriver = 'CodeIgniter\Session\Handlers\FileHandler'
        #app.sessionCookieName = 'ci_session'
        #app.sessionSavePath = NULL
        #app.sessionMatchIP = false
        #app.sessionTimeToUpdate = 300
        #app.sessionRegenerateDestroy = false
        
        #app.cookiePrefix = ''
        #app.cookieDomain = ''
        #app.cookiePath = '/'
        #app.cookieSecure = false
        #app.cookieHTTPOnly = false
        
        #app.CSRFProtection  = false
        #app.CSRFTokenName   = 'csrf_test_name'
        #app.CSRFCookieName  = 'csrf_cookie_name'
        #app.CSRFExpire      = 7200
        #app.CSRFRegenerate  = true
        #app.CSRFExcludeURIs = []
        
        #app.CSPEnabled = false
        
        #--------------------------------------------------------------------
        # DATABASE
        #--------------------------------------------------------------------
        
        database.default.hostname = localhost
        database.default.database = dummy_cv #change this to your database name
        database.default.username = yourdb_username #change to your db credentials
        database.default.password = yourdb_password #change to your db credentials
        database.default.DBDriver = MySQLi
        
        # database.tests.hostname = localhost
        # database.tests.database = ci4
        # database.tests.username = root
        # database.tests.password = root
        # database.tests.DBDriver = MySQLi
        
        #--------------------------------------------------------------------
        # CONTENT SECURITY POLICY
        #--------------------------------------------------------------------
        
        # contentsecuritypolicy.reportOnly = false
        # contentsecuritypolicy.defaultSrc = 'none'
        # contentsecuritypolicy.scriptSrc = 'self'
        # contentsecuritypolicy.styleSrc = 'self'
        # contentsecuritypolicy.imageSrc = 'self'
        # contentsecuritypolicy.base_uri = null
        # contentsecuritypolicy.childSrc = null
        # contentsecuritypolicy.connectSrc = 'self'
        # contentsecuritypolicy.fontSrc = null
        # contentsecuritypolicy.formAction = null
        # contentsecuritypolicy.frameAncestors = null
        # contentsecuritypolicy.mediaSrc = null
        # contentsecuritypolicy.objectSrc = null
        # contentsecuritypolicy.pluginTypes = null
        # contentsecuritypolicy.reportURI = null
        # contentsecuritypolicy.sandbox = false
        # contentsecuritypolicy.upgradeInsecureRequests = false
        
        #--------------------------------------------------------------------
        # HONEYPOT
        #--------------------------------------------------------------------
        
        #  honeypot.hidden = 'true'
        #  honeypot.label = 'Fill This Field'
        #  honeypot.name = 'honeypot'
        #  honeypot.template = '<label>{label}</label><input type="text" name="{name}" value=""/>'
        
        #--------------------------------------------------------------------
        # Cafe Variome Constants
        #--------------------------------------------------------------------
        
        PHP_BIN_PATH = /usr/bin/php
        EAV_BATCH_SIZE = 30000
        NEO4J_BATCH_SIZE = 30000
        SPREADSHEET_BATCH_SIZE = 1000
        ELASTICSERACH_AGGREGATE_SIZE = 100000
        ELASTICSERACH_EXTRACT_AGGREGATE_SIZE = 10000
        
        #--------------------------------------------------------------------
        # Authentication and Session Names
        #--------------------------------------------------------------------
        ALLOW_LOCAL_AUTHENTICATION = false # To determine if local authentication can happen or not.
        AUTHENTICATOR_SESSION_NAME = '_CV_AUTHENTICATOR_ID'
        SSO_RANDOM_STATE_SESSION_NAME = '_CV_OAUTH2_STATE'
        SSO_TOKEN_SESSION_NAME = '_CV_OAUTH2_TOKEN'
        SSO_REFRESH_TOKEN_SESSION_NAME = '_CV_OAUTH2_REFRESH_TOKEN'
        POST_AUTHENTICATION_REDIRECT_URL_SESSION_NAME = '_CV_REDIRECT_URL'


## Installation
In a terminal pointing to the root directory of Café Variome, run the following commands:

    composer install
    
    composer CVInstal

The first command fetches the dependencies from the composer.json file and sets up the bootstrap script.

The second command calls the interactive command line install tool. Follow the on-screen instructions (as shown below) to successfully install Cafe Variome.

<img height="1000" src="installation.png" width="1000"/>


## Contact and Support
For any queries related to Cafe Variome, refer to the FAQs or kindly contact Patrick.
