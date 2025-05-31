# Sistema de Administração de Doações

Este projeto consiste em um sistema de administração de doações e beneficiários:

- Frontend em Vue.js
- Backend em NestJS

## Pré-requisitos

- Docker e Docker Compose instalados
- Node.js 20 ou superior
- yarn (gerenciador de pacotes)
- tailwind para estilização do frontent

## Estrutura do Projeto

```
.
├── donation-manager/           # Backend (NestJS)
├── donation-admin/ # Frontend (Vue.js)
├── docker-compose.yml   # Configuração do Docker Compose
└── README.md            # Este arquivo
```

## Configuração do Ambiente

1. Clone os repositórios

- donation-manager (git clone https://github.com/BrunoSilva-Correia/donation-manager.git)
- donation-admin (https://github.com/BrunoSilva-Correia/donation-admin.git)

2. Certifique-se de que todas as portas necessárias estão disponíveis:
   - 3000 (Frontend)
   - 3002 (Backend)
   - 5432 (PostgreSQL)

## Executando o Projeto

Para iniciar todos os serviços, execute:

```bash
docker-compose up --build
```

Este comando irá:

1. Construir as imagens Docker para todos os serviços
2. Iniciar o banco de dados PostgreSQL
3. Iniciar o backend
4. Iniciar o frontend

## Acessando os Serviços

- Frontend: http://localhost:3000/login
- Backend: http://localhost:3002
- Banco de Dados PostgreSQL: localhost:5432

## Variáveis de Ambiente

Cada serviço possui seu próprio arquivo `.env`. Certifique-se de configurar as seguintes variáveis:

### Frontend (donation-admin)

```
rota -> /login
email -> admin@admin.com
senha   -> admin
```

### Backend (donation-manager)

```
PORT=3002
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/donation_manager"
JWT_SECRET_TOKEN='830a3988a5c7a94a6c196c99ff9649424a1e3a412725235cc7af835b0062bfbb27eaa916494833afe0f210300b51da29a5e0f9b628999a710edb1be1a3e8011f60f7d4150f61feb2b69c34e1f8cb42fb66770d829f034315e198e29d14c528d566a3dc0ce8f14a5cf7cde74b7f568e5d89810e400ee6822484b0cde0aa1b333724304a8775e6910a62c2b0101510915cfedb7971f392d118d364207e9b144cece1c900a17e356d1662c65c5043aa81e700f53793a234e0658723e1df8d94d7d2ace2e2a06edf00f320c7a1c1d5bd6fe43031c102f204265d8b5da5e41ad541f2568d3740b396634ed2e91a78afce29cb0efc0034525081fed32f6918412764b6'
```

## Desenvolvimento

Para desenvolvimento local, você pode executar cada serviço individualmente:

1. Frontend:

```bash
cd donation-admin
yarn install
yarn serve
```

2. Backend:

```bash
cd donation-admin
yarn install
yarn start:dev
```

## Parando os Serviços

Para parar todos os serviços:

```bash
docker-compose down
```

Para parar os serviços e remover os volumes:

```bash
docker-compose down -v
```

## Solução de Problemas

1. Se os serviços não iniciarem corretamente, verifique os logs:

```bash
docker-compose logs
```

2. Para reiniciar um serviço específico:

```bash
docker-compose restart [nome-do-serviço]
```

3. Se houver problemas com o banco de dados, você pode remover o volume e recriar:

```bash
docker-compose down -v
docker-compose up --build
```

## Equipe

- Albino Lucciani Leite Pinheiro – 2318056
- Bruno Silva Correia de Freitas - 2415477
- Francisco Rozinaldo Patrício Carneiro - 2316875
- Gedasio Alves de Brito Filho – 2213907
- Maria Leciene de Moura Silva - 2317815
- Nayla Honorato da Silva - 2319732
