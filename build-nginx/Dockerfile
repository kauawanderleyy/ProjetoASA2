# 1. Usa a imagem oficial do Nginx como base
FROM nginx:latest

# 2. Atualiza os repositórios e instala as ferramentas ping e curl
RUN apt-get update && \
    apt-get install -y iputils-ping curl && \
    rm -rf /var/lib/apt/lists/*

# 3. Substitui o arquivo de configuração padrão pelo nosso com Camada 4
COPY nginx.conf /etc/nginx/nginx.conf

# 4. Expõe a porta 8080 (que configuramos no stream)
EXPOSE 8080
