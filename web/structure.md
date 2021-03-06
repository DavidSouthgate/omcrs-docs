# Project Structure
An overview of the project directory structure is shown below

    /
    ├── Docker Configuration Files
    ├── /ci
    |   └── Continious Integration Config Files
    ├── /db
    |   └── init.sql: Database Setup Script
    └── /web
        ├── /docker
        |   ├── /apache: Apache config files
        |   ├── /log: Application log files
        |   └── /php: PHP config files
        ├── /public: Directory made public by apache
        |   ├── /api
        |   |   ├── index.php: All API requests. URLs etc processed here.
        |   |   └── .htaccess: Apache config file. Fowards all requests to index.php
        |   ├── /css: Static CSS files
        |   ├── /img: Static image files
        |   ├── /js: Statis javascript files
        |   ├── .htaccess: Apache config file. Fowards all requests to index.php
        |   ├── autoload.php: Calls needed classes and files
        |   └── index.php: All page requests. URLs etc processed here.
        ├── src
        |   ├── /analysis: Analysis python scripts
        |   ├── /classes: All application classes
        |   |   ├── /Api: Classes related to API
        |   |   ├── /ApiLegacy: Classes related to legacy API
        |   |   ├── /Breadcrumb: Classes related to Breadcrumbs
        |   |   ├── /Database: Classes related with database connection
        |   |   ├── /Login: Classes related to logging in
        |   |   ├── /Page: Classes for each page. Every page is represented by a static function in one of these classes.
        |   |   ├── /Question: Classes for question types
        |   |   └── /Scoring: Classes related to scoring
        |   ├── /templates: Template files
        |   ├── /vendor: Generated by composer. Includes required 3rd part libraries.
        |   ├── autoload.php: Calls needed classes and files
        |   ├── config.php: Config file. Example availiable in sample.config.php
        |   ├── functions.php: Generic functions required throughout project
        |   ├── sample.config.php: Example config file
        |   └── waitForDatabase.php: Script used by CI to ensure database is loaded before running scrtips
        ├── /tests: Unit tests etc
        └── /uploads: User upload files
        
## Example Page Execution Flow
 1. User navigates to / (i.e. home)
 2. Starts `/web/public/index.php`
 3. Uses url to lookup page class and function.
 4. Page function looked up as `PageHome::Home()`
 5. Runs static function PageHome::home() in `/web/src/classes/Page/PageHome.php`
 6. Executes page and passes variables to template `home` found in `/web/src/templates/home.php`
 7. Output page from template