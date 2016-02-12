FROM plone/plone:latest
MAINTAINER "Alin Voinea" <alin.voinea@eaudeweb.ro>

COPY src/install-dependencies.sh /bin/install-dependencies
COPY src/update-dependencies.sh  /bin/update-dependencies
COPY src/chaperone.conf          /etc/chaperone.d/chaperone.conf

COPY src/docker-setup.sh         /docker-setup.sh
COPY src/configure.py            /configure.py
COPY src/requires.py             /requires.py

COPY src/install.sh              /plone/install.sh

USER root
RUN ./install.sh
USER 500

ENTRYPOINT ["/usr/bin/chaperone"]
CMD ["--user", "zope-www"]
