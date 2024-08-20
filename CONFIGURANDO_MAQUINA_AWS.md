# Gerar chaves ssh para github
```
ssh-keygen -t rsa -b 4096 -C "youremail.com" \
eval "$(ssh-agent -s)" \
ssh-add github \
sudo chmod 400 github github.pub
```
# Adicionando alias e personlizando o terminal ~/.bashrc
```
echo 'alias api="cd /var/www/prod/api"' >> ~/.bashrc \
echo 'alias client="cd /var/www/prod/client"' >> ~/.bashrc \
echo 'alias create-command="nano ~/.bashrc"' >> ~/.bashrc \
echo 'export PS1='\''\[\e[32m\]\u@\h\[\e[m\]:\[\e[34m\]\w\[\e[m\]\[\e[33m\]$(git branch 2>/dev/null | grep \* | sed "s/* //")\[\e[m\]\$ '\'' ' >> ~/.bashrc
```

# Criar as pastas do projeto
```
cd /var \
sudo mkdir www \
chmod 777 -R www \
cd www \
mkdir prod \
cd prod \
mkdir api \
mkdir client
```
# Instalar o docker
```
sudo yum update -y \
sudo yum install docker -y \
sudo service docker start
```
# Configurar git nas pastas do projeto
```
cd /var/www/prod/api \
git init \
git remote add origin git@github.com:user/repo.git \
cd ../client \
git init \
git remote add origin git@github.com:user/repo.git
```