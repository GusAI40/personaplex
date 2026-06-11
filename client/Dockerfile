FROM node:20 AS build

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm ci

COPY . /app

RUN npm run build

FROM node:20-slim

WORKDIR /app

# OpenSSL for generating the self-signed certificate at container start
RUN apt-get update && apt-get install -y --no-install-recommends openssl \
 && rm -rf /var/lib/apt/lists/*

COPY --from=build /app /app

EXPOSE 5173

# The certificate is generated at startup (not baked into the image) so every
# container gets its own private key. Vite serves HTTPS when certs exist.
CMD ["sh", "-c", "test -f key.pem || openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout key.pem -out cert.pem -subj '/C=US/ST=State/L=City/O=Organization/CN=localhost'; exec npm run preview -- --host 0.0.0.0 --port 5173"]
