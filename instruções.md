docker compose up -d
Quando o terminal liberar, abra o seu navegador de preferência e acesse:
http://localhost:8080

docker compose ps
docker compose logs app 
No docker compose ps,o serviço monica_app aparece como Up ou como Exited?
docker compose logs -f app
Application is now live. ou AH00094: Command line: 'httpd -D FOREGROUND'
significa que ele terminou!
Volte no navegador e atualize a página: http://localhost:8080

docker compose down 
Isso vai parar e remover os contêineres temporários.
docker compose up -d
Acesse o navegador novamente (http://localhost:8080):