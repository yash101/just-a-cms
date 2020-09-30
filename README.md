# just-a-cms
It's just a CMS! Holds and manages information and resources separate from your frontend code.

## Introduction
Just-A-CMS is supposed to manage the data and resources that your website or web app uses.

## Design

### Scopes

- Data is stored in **scopes** which are akin to directories. There is a root scope (`/`).
- Scopes can hold variables and other scopes.
- Scopes have ownership. If a user has access to a parent scope, all child scopes have access.
- Users are categorized by roles
- Roles have parent roles, except the `admin` role which is the topmost root role
    - `admin` roles can read / write to any scope
- Another default role also exists: `anonymous` which represents "open to the public"
    - Users cannot take the `anonymous` role
    - The `anonymous` role can only be assigned the read priviledge to scopes and variables'
- Variables and data are stored in scopes
    - Main supported types:
        - Array::Type - arrays are nested and must have a type
        - RawText
        - HtmlText
        - File

### Features

- Main features:
    - Public API providing access to the information stored in the CMS
    - Database
    - Content management - variables, files, etc.
    - Authentication
- Other features:
    - Dashboard and interface for easy management
    - Triggers
        - HTTP/HTTPS endpoints which execute scripts
            - Could be used to create re-deploy hooks for Git  (🤔)
    - Static server
        - Serves static content per provided rules
        - Supports CORS rewriting of the API
        - Multi-site: multiple static content directories may be served simultaneously. The serving rules will be used to route the content.
    - Wizards
        - Automatically set up Just-A-CMS to provide a default experience for most common applications
    - Plugins
        - Modify the functionality of Just-A-CMS
        - I have no clue how I would go by implementing this

## More

Since Just-A-CMS is designed to be multi-user and multi-role, and has nested roles and priviledges, it can easily be used to serve multiple sites and applications simultaneously. 
