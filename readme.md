# FintechG Frontend

MVP de aplicativo web responsivo para controle financeiro pessoal/empresarial, construído com Ionic e Angular (usando Standalone Components para leveza e modularidade). O app permite autenticação segura, cadastro de entidades financeiras, registro de transações e visualização de dashboards com gráficos e métricas. Focado em usabilidade mobile-first, performance rápida (<2s load) e design minimalista (Material Design).

## Funcionalidades Exemplificadas
- **Autenticação**: Login/register com email/senha, integração social (Google/Facebook) e verificação OTP/SMS. Exemplo: Um usuário se registra em 2025, verifica via SMS e acessa o dashboard protegido por JWT.
- **Cadastros**: Registro de contas bancárias, clientes e fornecedores. Exemplo: Adicione um fornecedor "Empresa X" com detalhes, que aparece em filtros de transações.
- **Transações Financeiras**: Entradas/saídas com valores, datas e categorias. Exemplo: Registre uma saída de R$500 para "Aluguel" em novembro/2025, atualizando o balanço em tempo real.
- **Dashboard**: Visão geral com balanço total, gráfico de pizza (distribuição de despesas) e métricas mensais (ex.: total entradas R$10k, saídas R$5k em 2025). Filtros por ano/mês/dia.
- **Upload de Logo**: Crop e upload de imagem de perfil/logo, armazenada em S3-like.
- **UI/UX**: Responsivo para web/mobile, dark mode, acessibilidade (ARIA). Exemplo: No dashboard, um gráfico Chart.js mostra pizza de categorias financeiras de 2025.

O frontend se conecta ao backend via API (ex.: localhost:3000/auth/login) para dados persistentes.

## Requisitos
- Node.js 18+
- Ionic CLI: `npm install -g @ionic/cli`
- Angular 17+ (Standalone enabled)

## Setup e Execução
1. Clone o repo: `git clone https://github.com/Hitice/fintechg.git`
2. Instale dependências: `cd fintechg && npm install`
3. Rode localmente: `ionic serve` (acessa em http://localhost:8100)
4. Build para produção: `ionic build --prod`
5. Deploy exemplo: Use Vercel/Netlify (configure environment vars para API_URL do backend).

## Estrutura do Código
- `src/app/auth/`: Componentes para login/register (Standalone com FormsModule).
- `src/app/dashboard/`: DashboardComponent com gráficos (Chart.js).
- `src/app/financas/`: Componentes para cadastros e transações.
- `src/app/shared/`: Reutilizáveis como upload/crop (Cropper.js).
- Rotas lazy-loaded em `app-routing.module.ts`.

## Convenções
- Branches: `feature/nome-feature` (ex.: feature/auth-otp)
- Commits: Semânticos (feat:, fix:, chore:)
- Nomenclatura: kebab-case para arquivos, PascalCase para components.

## Integrações Pendentes
- Backend: Conecte a https://github.com/Hitice/fintechg-backend
- Testes: Jest/Cypress (adicionar em sprints futuros).

Para issues ou contribuições, abra um PR!