# Docker com Apache

Imagem docker criada para servir como base de estudos ao servidor web apache.

## Uso

Utilize:

<pre>
docker run -dit --name apache-app --publish=9081:80 chicocx/docker-apache
</pre>

Para configurar externamente à imagem docker o local onde o apache salvará o site, utilize:

<pre>
docker run -dit --name apache-app --publish=9081:80 -v "$PWD":/usr/local/apache2/htdocs/ chicocx/docker-apache
</pre>

O parâmetro
<pre>
-v "$PWD":/usr/local/apache2/htdocs/
</pre>
configura o diretório de onde o comando docker é executado como sendo o ponto de montagem do diretório /usr/local/apache2/htdocs/ da imagem criada. No caso, "$PWD" retorna o diretório atual.

É possível modificar esse diretório da seguinte forma:

<pre>
-v /diretorio/do/host:/usr/local/apache2/htdocs/
</pre>

Dessa forma, /diretorio/do/host passa a ser o diretório do host que conterá os arquivos lidos pela imagem em /usr/local/apache2/htdocs/

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

