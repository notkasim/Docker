- [Compose]
    - [] Creates an nginx image
    - [] Port 443:80 exposed
    - [] Creates a volumes that
    - [] Edit the html file and see changes

Dockerfile
-[] Creates an ubuntu container running nginx
    - [] creates test "testfile" in the /root
    - [] delete the default index file and replaces it
    - [] creates a virtualhost named "virtualhost1" in the /etc/nginx/conf.d
    - [] sendes the container to the background
    - [] The webserver can be reaches on port 10.0.0.200:8080