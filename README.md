# Plataforma Alavanca

Versão base da plataforma de cursos e aplicativos por assinatura, no estilo Hotmart. O nome "Alavanca" é provisório.

> Aqui não te ensinamos apenas como fazer, te damos as ferramentas para você ganhar dinheiro com o conhecimento adquirido.

## O que já existe

Tudo está em um único arquivo, `index.html` (HTML, CSS e JavaScript puros, sem build).

| Tela | Endereço | O que faz |
|---|---|---|
| Página inicial | `#inicio` | Marketing de vendas, exemplo de trilha, planos e perguntas frequentes |
| Catálogo | `#catalogo` | Cursos e aplicativos com busca e filtros |
| Detalhe | `#item-<id>` | Página de cada curso ou aplicativo |
| Aplicativos | `#apps` | Downloads (Google Play, App Store, web, computador), liberados para assinantes |
| Entrar | `#entrar` | Login com e-mail e senha, Google e Apple; criar conta; recuperar senha |
| Minha área | `#painel` | Assinatura, cursos em andamento, aplicativos e conta |
| Aula (LMS) | `#aula-<id>` | Trilha de módulos e aulas, vídeo, texto, questionário com correção e atividade prática |
| Planos | `#planos` | Planos mensal e anual |
| Admin | `#admin` | Cadastro de cursos (módulos, aulas, atividades) e de aplicativos (links de download) |

O catálogo inicial vem das 13 ideias do brainstorming de 14/11/2026: 6 cursos e 8 aplicativos.

## Como rodar

Abra o `index.html` no navegador. Para servir localmente:

```bash
python3 -m http.server 8080
# acesse http://localhost:8080
```

## O que ainda é simulação

- **Login:** as contas ficam no `localStorage` do navegador. Os botões Google e Apple simulam o retorno do login.
- **Assinatura:** confirmar o plano libera o acesso sem cobrança.
- **Progresso dos alunos:** salvo no navegador de cada aluno.
- **Catálogo:** quando aberto como artefato no Claude, o cadastro da área Admin é compartilhado entre a equipe. Fora dele, as edições ficam salvas só no navegador.
- **Valores dos planos:** são exemplos (R$ 59,90 por mês ou R$ 39,90 por mês no plano anual).

## Próximos passos para produção

1. **Autenticação:** Firebase Authentication, Supabase Auth ou Auth0, com e-mail e senha, Google e Apple. O login com Apple exige conta no Apple Developer Program.
2. **Pagamentos:** cobrança recorrente com Pix e cartão (Stripe, Mercado Pago ou Pagar.me), com webhook para ativar e cancelar o acesso.
3. **Vídeos:** hospedagem com controle de acesso (Panda Video, Vimeo ou Bunny Stream). O campo "Link do vídeo" de cada aula já aceita o endereço.
4. **Back-end e banco de dados:** catálogo, alunos, progresso e atividades no servidor.
5. **Lojas de aplicativos:** contas de desenvolvedor na Google Play e na App Store.
6. **Jurídico:** domínio, termos de uso, política de privacidade (LGPD) e política de reembolso.
