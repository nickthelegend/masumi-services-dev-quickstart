FROM ghcr.io/masumi-network/masumi-payment-service:0.22.0

RUN apt-get update && apt-get install -y curl

ENV DATABASE_URL=postgresql://postgres:postgres@postgres-payment:5432/postgres?schema=public
ENV ENCRYPTION_KEY=changeme
ENV ADMIN_KEY=changeme
ENV BLOCKFROST_API_KEY_PREPROD=changeme
ENV SEED_ONLY_IF_EMPTY=TRUE

CMD sh -c "npm run prisma:migrate && npm run prisma:seed && npm start"

EXPOSE 3001
