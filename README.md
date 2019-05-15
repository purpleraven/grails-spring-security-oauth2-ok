Spring Security OAuth2 Odnoklassniki Plugin
======================================
[ ![Download](https://api.bintray.com/packages/purpleraven/plugins/spring-security-oauth2-ok/images/download.svg) ](https://bintray.com/purpleraven/plugins/spring-security-oauth2-ok/_latestVersion)

Add a Odnoklassniki OAuth2 provider to the [Spring Security OAuth2 Plugin](https://github.com/MatrixCrawler/grails-spring-security-oauth2).

Installation
------------
Add the following dependencies in `build.gradle`
```
dependencies {
...
    compile 'org.grails.plugins:spring-security-oauth2:1.1+'
    compile 'org.grails.plugins:spring-security-oauth2-ok:1.0'
...
}
```

Usage
-----
Add this to your application.yml
```
grails:
    plugin:
        springsecurity:
            oauth2:
                providers:
                    odnoklassniki:
                        api_key: 'odnoklassniki-api-key'               #needed
                        api_secret: 'odnoklassniki-api-secret'         #needed
                        successUri: "/oauth2/odnoklassniki/success"    #optional
                        failureUri: "/oauth2/odnoklassniki/failure"    #optional
                        callback: "/oauth2/odnoklassniki/callback"     #optional
```
You can replace the URIs with your own controller implementation.

In your view you can use the taglib exposed from this plugin and from OAuth plugin to create links and to know if the user is authenticated with a given provider:
```xml
<oauth2:connect provider="odnoklassniki" id="odnoklassniki-connect-link">odnoklassniki</oauth2:connect>

Logged with odnoklassniki?
<oauth2:ifLoggedInWith provider="odnoklassniki">yes</oauth2:ifLoggedInWith>
<oauth2:ifNotLoggedInWith provider="odnoklassniki">no</oauth2:ifNotLoggedInWith>
```
License
-------
Apache 2