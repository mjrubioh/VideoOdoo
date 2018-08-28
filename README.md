# VideoOdoo

### Paso a paso de Ejecución de Odoo 10 en sistema Linux.

También pueden aprender a ejecutra odoo 10 en la página de [Juventud Productiva Venezolana](https://juventudproductivabicentenaria.blogspot.com/2017/07/ejecutar-odoo-10-en-linux.html#comment-form), pueden encontrar el archivo comprimido de odoo 10.

**1-** Actualizar su sistema operativo.

sudo apt-get update && apt-get upgrade


**2-** Instalar todas las dependencias de python, posgresql, node entre otras.

sudo apt-get install bzr bzrtools python python-egenix-mxdatetime python-dateutil python-pybabel python-openid python-feedparser python-lxml python-libxml2 python-libxslt1 python-psycopg2 python-libxml2 python-libxslt1 python-imaging python-gdata python-ldap python-reportlab python-pyparsing python-simplejson python-pydot python-webdav graphviz python-werkzeug python-matplotlib python-vatnumber python-numpy python-pychart python-vobject python-zsi python-xlwt python-hippocanvas python-profiler python-dev python-setuptools postgresql postgresql-client-common python-yaml python-mako gcc mc python-babel python-feedparser python-reportlab-accel python-zsi python-openssl python-jinja2 python-unittest2 python-mock python-docutils lptools make python-psutil python-paramiko poppler-utils python-pdftools antiword python-jinja2 python-requests git-core sudo python-decorator python-pypdf python-passlib xsltproc xmlstarlet python-soappy python-qrencode python-pip node-less

**3-** Configuracmos Postgresql para que no nos pida contraseña.

Abrimos el archivo pg_hba.conf con el siguiente comando.


sudo nano /etc/postgresql/tu_version_instalada/main/pg_hba.conf

Cambiamos en las dos lineas que dice:

  local   all     postgres      peer

 local  all      all         md5

 por

  local   all     postgres      trust

 local  all      all           trust


**4-** Creamos el usuario con que Odoo se comunicará con Postgresql.

createuser -U postgres -eSRdw odoo_tu_proyecto_10


**5-** Descargamos y descomprimimos Odoo 10 en la carpeta personal.

[Descargar Odoo 10 ZIP](https://juventudproductivabicentenaria.blogspot.com/2017/07/ejecutar-odoo-10-en-linux.html#comment-form)

**6-** Nos ubicamos dentro de la capeta de odoo-10 (descomprimida)  para crear el archivo de ejecución (No hacer como Usuario Root).


./odoo-bin -r odoo_tu_proyecto_10 -c tu_proyecto.conf -s


**7-** Finalmente levantamos Odoo 10.

Si todo ha salido bien, abre el navegador y coloca en la url localhost:8069 y pulse enter.
