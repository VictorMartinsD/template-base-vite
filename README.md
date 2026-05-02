# template-base

Template base para projetos com Vite, JavaScript, Prettier, ESLint e Husky.

## Quick start

Clone o template, instale as dependências e inicie o desenvolvimento:

```bash
npm install
cp .env.example .env  # copie e ajuste as variáveis de ambiente se precisar
npm run dev
```

## Comandos e fluxo

| Etapa               | Comando            | Quando usar                                             | O que faz                                                |
| ------------------- | ------------------ | ------------------------------------------------------- | -------------------------------------------------------- |
| **Preparação**      | `npm install`      | Após clonar, após `git pull`, ao alterar `package.json` | Instala/atualiza as dependências                         |
| **Desenvolvimento** | `npm run dev`      | Durante todo o desenvolvimento                          | Inicia o servidor local com atualização automática       |
| **Verificação**     | `npm run lint:fix` | Ao terminar uma funcionalidade                          | Corrige automaticamente problemas de estilo e importação |
| **Validação**       | `npm run lint`     | Após `lint:fix` ou antes de commitar                    | Mostra erros que exigem ajuste manual                    |
| **Build**           | `npm run build`    | Antes de entregar ou publicar                           | Gera a versão otimizada para produção                    |
| **Preview**         | `npm run preview`  | Após `build`, antes de enviar para o ar                 | Valida a build localmente                                |
| **Commit**          | `git commit`       | Ao finalizar as mudanças                                | Husky + lint-staged validam os arquivos automaticamente  |

**Nota:** O Prettier reformata o código automaticamente durante o pre-commit. Se precisar ajustar o README para outro projeto, mantenha esse fluxo e personalize as instruções finais.

---

Desenvolvido por [Victor Martins](https://github.com/VictorMartinsD)
Front-End Developer focado em aplicações web modernas e performance.
