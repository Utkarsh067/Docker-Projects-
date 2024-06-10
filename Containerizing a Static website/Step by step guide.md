# Steps
1. Download Docker Desktop form link

2. Create a docker project folder on your PC

      In that folder, first create a docker file and write this code
   
```json
FROM ubuntu:latest

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y nginx

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]
```

3. After this open terminal and copy docker project folder's path in it using "cd path"

4. Now to create an image use code 'docker build -t <image-name> .
      It will create your image in docker hub

5. To check if image has been created or not, you can run 'docker images'
      It will print all of the images in docker hub.

6. now run "docker run -p 8080:80 --name <container-name> <image-name>" and open browser and write "localhost:8080" and press enter 
![image](https://github.com/Utkarsh067/Docker-Projects-/assets/161854515/cc574cbd-0f7a-4a27-9f3c-42d25722a16b)

      It will show this because we haven't uploaded any html file on it

7. In the same fodler create another folder named  'html', and write your html code in it

8. Now, go back to dockerfile and update it
```json
FROM ubuntu:latest

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y nginx

COPY <html-folder-name> /var/www/html

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]
```

9. Now again build the image "docker build -t <image-name> ." and run it using 
      "docker run -p 8090:80 --name <container-name> <image-name>"

 10. Refresh your tab, you can see your website there


**Hoorayyyy!!!, you have successfully Containerized your HTML Web Application🎉🎉🎉**
