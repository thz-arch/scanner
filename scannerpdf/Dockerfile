FROM python:3.9-slim

# Instalar dependências do sistema
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx \
    libglib2.0-0 \
    && rm -rf /var/lib/apt/lists/*

# Definir diretório de trabalho
WORKDIR /app

# Copiar arquivos
COPY . .

# Instalar dependências Python
RUN pip install --no-cache-dir -r requirements.txt

# Definir porta
EXPOSE 8080

# Comando para iniciar o servidor
CMD ["gunicorn", "-b", "0.0.0.0:8080", "app:app"]
