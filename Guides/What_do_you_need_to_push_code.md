# What do you need

To keep consistency and provide the most amount of information to the user about the architecture, usage and installation of the code, the repository should adhere to the following structure:

# The README.md file:

THe information related to the README.md file and what requirements it needs can be found here: [How to publish content](https://github.com/Anthology-Community/Contributions/blob/main/Guides/How%20to%20publish%20content.md)

> [!CAUTION]
> Please review the document mentioned above, if the README doesn't contain the information there, the submission will not be approved until it does.

# The Code:

Regarding the code, the structure itself will differ significantly from language to language (even the type of application being published), however, the code itself should try to adhere the following structure at its core:

## _For Code applications or samples_

<details>
<summary>Expand for definition and structure</summary>

```
  Product-RepositoryName
    |- config
      |- <local config>
    |- database
      |- <local db files>
    |- src
      |- <App code>
    |- public
      |- <static files (if any)>
    |- tests
    |- docs
    |- .gitignore
    |- CHANGELOG.md
    |- lint-files
    |- Docker file or docker-compose file (if needed)
    |- README.md
```

This is the folder structure that should be within your project. The following will provide an explanation of each of the folders and what is expected to be present:

### Product-RepositoryName:

This references the topmost (root) location of your repository (sometimes references as the home of the repository). This name should comply with the naming conventions outlined in the guide [How to publish content](How_to_publish_content.md)

### config:

This folder should contain a file or files where the configuration of the application should be stored such as domains, ports, URLs, routes, etc., or any piece of information that will be needed within the application to work properly and is expected for the user to fill.

> [!TIP]
> Although is not required, it is recommended that you add a README.md file on this folder where you explain each of the config values and what it does or what type of information is expected (type of value, format, length, etc)

The folder should contain an initial configuration file with examples of configuration values (denoted with .example) and have another initial file with empty values for the user to fill.

> [!CAUTION]
> Please don't use .env files throughout the application since it could be confusing to the user or could have exposed data or PII, in addition to this, usual GitHub configurations will skip this file from being uploaded (specially with the presence of a .gitignore file)

### database:

This folder should contain the set of files that will work as local database in case your application needs one and doesn't have access to a proper database (PostgreSQL, MySQL, etc.).

This folder should contain only the files and not any handler or additional functions that can be used by the code, these functions will go within the application itself.

> [!CAUTION]
> If you're including a lite database such as SQLite, make sure that the database doesn't have any information stored in it or if there's information, is dummy data and not related to any client

### src:

This is the folder where your application code will be located. Given that structures of code changes depending on the language used to develop the application, there's no one-fit-all structure, however, it should have coherence and should be easily readable by the user.

> [!TIP]
> It is not required but we recommend that you add a README file having an overall explanation of how the code works and explaining any potential functions that might be cumbersome to read.

> [!CAUTION]
> It is required that you create a README file in case your application has an additional service within your src code explaining how it works, what configuration is needed and the installation/launch process.

### public:

If your application has any public files such as HTML, CSS or JS files that are used within your application, you can store them here and reference them in your application

### tests:

This folder will contain any unit tests or other type of test you deem necessary for the correct functioning of your application. If there's no test, the folder can be omitted.

### docs:

This folder will contain additional information about the application such as endpoint definitions, installation guides, in-depth code walkthroughs, etc.

### .gitignore

Your application must have a .gitignore file where you add files and folders that can be omitted when uploading the code (such as node_modules or .env files). If needed [Toptal has your back](https://www.toptal.com/developers/gitignore)

### CHANGELOG.md

This file should keep track of the version of the sample code/application and have a list of changes or fixes implemented that were implemented in newer releases. To have consistency in this file, the contents must adhere to the following conventions in this order (any one can be skipped if there are no changes related to that section). The section that have information should display them as a list of items:

```
# Release vX.X.X

### Added
### Changed
### Deprecated
### Fixed
### Removed
### Security
```

The only release that can skip this format is the initial release since all information will be new. For a description of each section and what should contain, please refer to [https://changelog.md](https://changelog.md)

### lint-files

If your application needs a specific set of rules when it comes to code, you can add a lint file(s) for it. If there's no need, this can be omitted.

### Docker or docker-compose file

If your application can be containerized, you can add one or both files to the root of the repository. dockerfile to create the image and docker-compose.yml to create the container stack (if any)

</details>

## _For API collections_

<details>
<summary>Expand for definition and structure</summary>

```
  Product-RepositoryName
    |- config
      |- <local config>
    |- api
      |- <API files>
    |- docs
    |- CHANGELOG.md
    |- .gitignore
    |- README.md
```

### Product-RepositoryName:

This references the topmost (root) location of your repository (sometimes references as the home of the repository). This name should comply with the naming conventions outlined in the guide [How to publish content](How_to_publish_content.md)

### config:

This folder should contain the configuration needed in the program to allow the user the usage of the APi collection without any issue. This could contain an .MD file that outlines the steps in detail.

E.g: Steps to configure Postman to work gather the authentication tokens from a REST API call and apply it to all subsequent requests.

### api:

This folder contains the source or export files created by the API client used to create the API collection. If there's more than one version of the collection or support for multiple software is included, the exports of each should be separated by folder with clear names.

E.g: For multiple software

```
Learn-Attendance_APIs
    |- config
      |- How_to_configure_Postman.md
      |- How_to_configure_HTTPie.md
      |- How_to_configure_Insomnia.md
    |- api
      |- Postman
          |- API_EXPORT.JSON
      |- HTTPie
          |- API_EXPORT.JSON
      |- Insomnia
          |- API_EXPORT.JSON
    |- docs
        |- swagger_export
    |- CHANGELOG.md
    |- .gitignore
    |- README.md
```

E.g: For multiple versions

```
Learn-Attendance_APIs
    |- config
      |- Migrate from V1 to V2.md
    |- api
      |- v1
          |- COLLECTION_EXPORT.JSON
      |- v2
          |- UPDATED_COLLECTION_EXPORT.JSON
    |- docs
        |- swagger_v1
        |- swagger_v2
    |- CHANGELOG.md
    |- .gitignore
    |- README.md
```

### docs

This folder should contain the documentation related to the API collection (if any). This can also be used to store any Swagger exports that can be made public

### CHANGELOG.md

This file should keep track of the version of the sample code/application and have a list of changes or fixes implemented that were implemented in newer releases. To have consistency in this file, the contents must adhere to the following conventions in this order (any one can be skipped if there are no changes related to that section). The section that have information should display them as a list of items:

```
# Release vX.X.X

### Added
### Changed
### Deprecated
### Fixed
### Removed
### Security
```

The only release that can skip this format is the initial release since all information will be new. For a description of each section and what should contain, please refer to [https://changelog.md](https://changelog.md)

### .gitignore

Your application must have a .gitignore file where you add files and folders that can be omitted when uploading the code (such as node_modules or .env files). If needed [Toptal has your back](https://www.toptal.com/developers/gitignore)

</details>

# To publish your contribution

To publish your contribution, please submit a new issue in the Contributions repository ([Here](https://github.com/anthology-inc/community-contribution/issues/new/choose)) using the template to **Publish Code Repository** including the necessary information requested in the template.
