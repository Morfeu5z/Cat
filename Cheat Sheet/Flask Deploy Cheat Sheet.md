# Flask: 
## Deploy Flask on Apache2 on Ubuntu Server
***
### Instalacja modułów

>sudo su

>apt-get install python3-pip 

>apt-get install virtualenv

>pip3 install flask

>apt-get install apache2

>apt-get install libapache2-mod-wsgi-py3

>apt-get install a2enmod

### Ustawienia apache2

>cd /etc/apache2/sites-available

>nano my_flask.conf

```js
<VirtualHost *:80>
    serverName my_site.com
    WSGIScriptAlias / /var/www/flask/flask.wsgi
    <Directory /var/www/flask>
        Order allow,deny
        Allow from all
    </Directory>
    
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/error.log combinated
</VirtualHost>
```

### Stworzenie projetu

>cd /var/www

>mkdir flask

>cd flask

>mkdir static templates

>virtualenv venv

>nano init.py

```python
from flask import Flask

app = Flask(__name__)
@app.route("/")
def index():
  return "Hello world"

if __name__ == "__main__":
  app.run()
```

### Konfiguracja wsgi

>nano flask.wsgi

```js
import sys
sys.path.insert(0, "/var/www/flask/")
from init import app as application
```

### Uruchomienie na apache2
>a2ensite my_flask.conf

>a2dissite 000-default.conf

>systemctl reload apache2
>
