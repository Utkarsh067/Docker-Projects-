Download Docker Desktop form link

Create a docker project folder on your PC

In that folder, first create a docker file

FROM ubuntu:latest

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y nginx

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]

after this open terminal and copy docker project folder's path in it using
'cd path'

now to create an image use code 'docker build -t <image-name> .
it will create your image in docker hub

To check if image has been created or not, you can run 'docker images'
it will print all of the images in docker hub.

now run "docker run -p 8090:80 --name <container-name> <image-name>"
and open browser and write "localhost:8080" and press enter, it will show this

because we have.nt uploaded any html file on it

in the same fodler create another folder named  'html', and write your html code in it

now, go back to dockerfile and update it

FROM ubuntu:latest

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y nginx

COPY <html-folder-name> /var/www/html

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]


Now again build the image "docker build -t <image-name> ."
and run it using 
"docker run -p 8090:80 --name <container-name> <image-name>"

and refresh your tab, you can see your website there
