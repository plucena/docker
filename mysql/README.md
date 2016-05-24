MYSQL Docker - https://hub.docker.com/r/plucena/mysqld
---------------

user: root

password: unasp


How to install it on IBM BlueMix
-----------------

* Install BlueMix Containers CLI - https://console.ng.bluemix.net/docs/containers/container_cli_cfic.html

* Login with Bluemix credentials - API endpoint: https://api.ng.bluemix.net

        cf login


* Get your namespace

        cf ic namespace get

        If a namespace is displayed from the cf ic namespace get command, take note of that name and skip to the next step. If a namespace is not specified for your organization yet, set one using the following command:

        cf ic namespace set <new_name>

