FROM node:18-alpine

WORKDIR /app

# Copiar arquivos de dependências
COPY package*.json ./
COPY prisma ./prisma/

# Instalar dependências
RUN npm ci --only=production

# Gerar cliente Prisma
RUN npx prisma generate

# Copiar código fonte
COPY . .

# Build da aplicação
RUN npm run build

# Expor porta
EXPOSE 3000

# Comando para iniciar
CMD ["npm", "start"]
