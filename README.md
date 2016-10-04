# Docker com Apache

Imagem docker criada para servir como base de estudos ao servidor web apache.

## Uso

Utilize:
<pre>
docker run -dit --name apache-app --publish=9081:80 -v "$PWD":/usr/local/apache2/htdocs/ chicocx/docker-apache
</pre>

## Demais comandos

Entrar na máquina/imagem
<pre>
docker exec -it redmine1 bash 
</pre>

sair sem encerrar a máquina: 
<pre>
ctrl p q
</pre>

Lista o status dos containers 
<pre>
docker ps -a
</pre>

Exclui os containers que estão parados

<pre>
docker rm $(docker ps -q -f status=exited)
</pre>

Lista as imagens baixadas
<pre>
docker images
</pre>

Exclui alguma imagem
<pre>
docker rmi f72216345d97
</pre>

