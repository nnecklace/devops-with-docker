REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
memcached           latest              33546802fc24        7 months ago        62.2MB
dev-proxy           latest              ea962732232c        12 months ago       15.1MB
kura-postgres       latest              f1538b222681        12 months ago       229MB
postgres            10                  6eb6c50a02e7        13 months ago       229MB
alpine              3.7                 34ea7509dcad        15 months ago       4.21MB

CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS                      NAMES
c6afa31b2115        postgres:10         "docker-entrypoint.s…"   8 minutes ago       Exited (1) 8 minutes ago                               clever_allen
d60421c09eaf        memcached           "docker-entrypoint.s…"   5 months ago        Exited (255) 4 months ago   0.0.0.0:11211->11211/tcp   gracious_williamson
afea617acb95        dev-proxy           "/opt/docker-entrypo…"   7 months ago        Exited (255) 4 months ago   0.0.0.0:443->4443/tcp      brave_perlman
