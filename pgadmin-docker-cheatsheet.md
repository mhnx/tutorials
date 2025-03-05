# Instalando o Docker

A fazer:
https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository

# Configurando o PostgreSQL e instalando no Docker
```bash
docker run -d \
  --name postgres_container \
  -e POSTGRES_USER=rainbow_mika \
  -e POSTGRES_PASSWORD=admin123 \
  -e POSTGRES_DB=happy_playground \
  -p 5432:5432 \
  postgres:latest
```
# Inicializar o contêiner
```bash
docker ps
docker start postgres_container
```
# Instalando o pgAdmin
```bash
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
```
```bash
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```
```bash
sudo apt install pgadmin4-desktop
```
# Acessando o PostgreSQL via pgAdmin
1. Abra o pgAdmin
2. Clique em "Add New Server"
3. Configure a conexão:
    - Name: ```PostgreSQL Docker```
    - Host: ```localhost```
    - Port: ```5432```
    - Username: ```rainbow_mika```
    - Password: ```admin123```
4. Clique em "Save" e pronto! 🎉

