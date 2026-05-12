# Prompt Codex — Simple Cashbook

Este arquivo contém o prompt principal usado para orientar a implementação do projeto no Codex.

## Produto

Simple Cashbook é um SaaS para autônomos, freelancers e pequenos prestadores controlarem receitas, despesas, categorias, pagamentos, recebimentos e fluxo de caixa básico.

## Stack obrigatória

- Laravel 13
- Vue.js 3
- TypeScript
- MySQL
- Tailwind CSS
- Vite
- Inertia.js

## Regras principais

- Seguir SOLID e Clean Code.
- Usar Controllers finos.
- Usar Services para regras de negócio.
- Usar Form Requests para validação.
- Usar Policies para autorização.
- Usar Enums para tipos, status, recorrências e roles.
- Criar painel admin.
- Criar CRUD de planos.
- Criar pelo menos um Plano Gratuito.
- Criar SEO básico.
- Criar `public/robots.txt`.
- Criar `public/sitemap.xml`.
- Criar manual em Markdown.
- Preparar deploy para VPS Hostinger KVM 1 com CloudPanel, Nginx, PHP-FPM, MySQL e Cloudflare.

## Observação importante

O sistema deve ser apresentado como ferramenta de organização financeira simples. Ele não deve prometer consultoria financeira, contábil, fiscal, tributária ou de investimentos.

## Prompt completo

Você é um arquiteto de software sênior especialista em Laravel 13, Vue.js 3, TypeScript, MySQL, SaaS financeiro simples, SOLID, Clean Code e segurança.

Crie um SaaS chamado "Meu Caixa Simples", focado em autônomos, freelancers e pequenos prestadores que precisam controlar receitas, despesas e fluxo de caixa básico.

Stack:
- Laravel 13
- Vue.js 3
- TypeScript
- MySQL
- Tailwind CSS
- Vite
- Inertia.js com Vue 3
- Autenticação compatível com Laravel 13

Objetivo:
Permitir controle financeiro simples, sem substituir contabilidade, banco ou sistema fiscal.

Avisos obrigatórios:
- O sistema não deve prometer consultoria financeira, contábil ou fiscal.
- Incluir disclaimer em Termos de Uso dizendo que é ferramenta de organização financeira e não substitui contador ou consultor.

Personas:
1. Freelancer.
2. MEI/autônomo que quer organizar entradas e saídas.
3. Prestador de serviço local.
4. Pequeno negócio informal em fase inicial.

Funcionalidades do usuário:
- Cadastro/login.
- Dashboard:
  - saldo previsto;
  - receitas do mês;
  - despesas do mês;
  - contas vencidas;
  - próximas contas;
  - limite do plano.
- CRUD de categorias:
  - receita;
  - despesa.
- CRUD de contas/lançamentos:
  - descrição;
  - tipo: receita/despesa;
  - categoria;
  - valor;
  - data de vencimento;
  - data de pagamento;
  - status;
  - observação.
- Status:
  - previsto;
  - pago;
  - recebido;
  - atrasado;
  - cancelado.
- Recorrências simples:
  - mensal;
  - semanal;
  - anual.
- Relatórios:
  - receitas por período;
  - despesas por período;
  - resultado mensal;
  - categorias mais relevantes.
- Exportação CSV.
- Não integrar banco, Open Finance ou nota fiscal no MVP.
- Cores configuráveis por variáveis.

Painel admin:
- Role admin.
- CRUD de planos.
- CRUD de usuários.
- Alterar plano manualmente.
- Configurações globais:
  - nome;
  - domínio;
  - e-mail;
  - cores;
  - SEO;
  - limites.
- Admin pode configurar categorias modelo sugeridas para novos usuários.
- Relatórios:
  - usuários ativos;
  - usuários por plano;
  - lançamentos criados.

Planos:
- Gratuito:
  - até 50 lançamentos por mês;
  - categorias limitadas.
- Pro:
  - lançamentos ilimitados;
  - recorrências;
  - exportação CSV.
- Plus:
  - recursos Pro;
  - relatórios avançados;
  - personalização visual.

SEO:
- Home.
- Recursos.
- Preços.
- Termos.
- Privacidade.
- Implementar metatags, canonical, Open Graph, Twitter Card.
- Schema.org SoftwareApplication.
- Criar public/robots.txt.
- Criar public/sitemap.xml.
- Não indexar qualquer página financeira do usuário.

Arquitetura:
- Services:
  - TransactionService;
  - RecurrenceService;
  - FinancialSummaryService;
  - PlanLimitService.
- Controllers finos.
- Form Requests.
- Policies.
- Enums:
  - TransactionType;
  - TransactionStatus;
  - RecurrenceType;
  - UserRole.
- Seeders:
  - admin;
  - planos;
  - configurações;
  - categorias modelo.
- Factories.
- Testes:
  - criação de lançamento;
  - limite do plano gratuito;
  - cálculo de resumo mensal;
  - usuário não acessa dados de outro usuário;
  - admin altera plano.

Entidades:
- User
- Plan
- UserPlan
- Category
- Transaction
- Recurrence
- AppSetting
- DefaultCategoryTemplate

Manual:
- Criar docs/MANUAL.md.
- Explicar:
  - cadastro de receitas/despesas;
  - categorias;
  - recorrências;
  - relatórios;
  - limitações;
  - planos;
  - painel admin.
- Criar README.md.
- Criar docs/DEPLOY.md para VPS Hostinger KVM 1.

Priorizar segurança, isolamento dos dados por usuário, validações fortes e simplicidade.

### Regras globais do projeto:

1. Stack obrigatória:
   - Laravel 13
   - Vue.js 3
   - TypeScript
   - MySQL
   - Tailwind CSS
   - Vite

2. Arquitetura:
   - Seguir SOLID, Clean Code e separação de responsabilidades.
   - Controllers devem ser finos.
   - Usar Form Requests para validação.
   - Usar Policies para autorização.
   - Usar Services/Actions para regras de negócio.
   - Usar Enums para status, roles e tipos fixos.
   - Usar migrations com foreign keys, índices e constraints.
   - Usar seeders para dados iniciais.
   - Usar factories e testes mínimos.

3. SaaS:
   - Todo projeto deve ter planos.
   - Deve existir no mínimo Plano Gratuito.
   - Planos devem ser configuráveis pelo painel admin.
   - Admin deve poder alterar plano do usuário manualmente.
   - Não implementar pagamento online no MVP.
   - Preparar estrutura para futura integração com cobrança.

4. Admin:
   - Criar role admin.
   - Criar painel admin protegido.
   - Admin deve gerenciar usuários, planos e configurações globais.
   - Admin deve visualizar relatórios básicos.

5. SEO:
   - Criar páginas públicas:
     - Home
     - Recursos
     - Preços
     - Termos de Uso
     - Política de Privacidade
   - Implementar title, meta description, canonical, Open Graph e Twitter Card.
   - Criar Schema.org SoftwareApplication quando aplicável.
   - Criar public/robots.txt.
   - Criar public/sitemap.xml.
   - Não indexar rotas autenticadas, admin, dashboard ou dados privados.

6. Front-end:
   - Usar Vue 3 com TypeScript.
   - Componentizar telas e elementos reutilizáveis.
   - Usar Tailwind CSS.
   - Cores principais devem ser configuráveis via variáveis CSS.
   - Evitar cores hardcoded espalhadas no projeto.
   - Criar layout público, layout autenticado e layout admin.

7. Deploy:
   - Preparar para VPS KVM 1 da Hostinger com Nginx, PHP-FPM, MySQL e Node.
   - Criar docs/DEPLOY.md.
   - Documentar:
     - composer install
     - npm install
     - npm run build
     - php artisan migrate --seed
     - php artisan storage:link
     - permissões
     - configuração .env
     - cache de config, routes e views

8. Documentação:
   - Criar / Atualizart README.md técnico.
   - Criar / Atualizart docs/MANUAL.md para uso do sistema.
   - Criar / Atualizart docs/ROADMAP.md com melhorias futuras.
   - Criar / Atualizart docs/DEPLOY.md.

9. Segurança:
   - Isolar dados por usuário.
   - Nunca permitir que um usuário acesse dados de outro.
   - Validar permissões via Policies.
   - Proteger rotas admin.
   - Não expor dados privados no sitemap.
   - Não indexar páginas privadas.

10. Qualidade:
   - Criar testes mínimos para regras principais.
   - Evitar overengineering.
   - Priorizar MVP funcional, limpo, simples e evolutivo.