# template-base

Template base para projetos com Vite, JavaScript, Prettier, ESLint, Stylelint e Husky.

## Quick start

Clone o template, configure a identificação do projeto e inicialize o ambiente:

1. Abra o `package.json` e atualize os campos iniciais:
   ```json
   "name": "nome-do-seu-projeto",
   "description": "Breve descrição do projeto"
   ```
2. Instale as dependências travadas no lockfile e configure o ambiente:
   ```bash
   npm ci
   npm run dev
   ```
   Se precisar de variáveis locais, copie `.env.example` para `.env` usando o recurso de cópia do seu sistema e ajuste os valores. No PowerShell, por exemplo: `Copy-Item .env.example .env`.

## Comandos e fluxo

| Etapa               | Comando                      | Quando usar                                                    | O que faz                                                                        |
| :------------------ | :--------------------------- | :------------------------------------------------------------- | :------------------------------------------------------------------------------- |
| **Sincronização**   | `npm ci`                     | Pós-clonagem (após mudar o package.json) ou pós-`git pull`     | Instalação limpa, rápida e 100% fiel baseada no `package-lock.json`              |
| **Manutenção**      | `npm install`                | Se necessário (instalar novo pacote ou atualizar dependências) | Instala ou atualiza pacotes alterando o `package-lock.json`                      |
| **Desenvolvimento** | `npm run dev`                | Durante todo o desenvolvimento (diária)                        | Inicia o servidor local com atualização automática (HMR)                         |
| **Verificação JS**  | `npm run lint`               | Ao terminar uma funcionalidade (fim da task)                   | Observa, analisa e avisa sobre inconformidades e erros de lógica no JavaScript   |
| **Verificação CSS** | `npm run lint:css`           | Ao terminar uma funcionalidade ou estilização                  | Examina os arquivos CSS buscando regras inválidas e maus padrões                 |
| **Limpeza JS**      | `npx eslint [caminho] --fix` | Fim da task (após o lint básico)                               | Corrige erros de estilo de forma cirúrgica e localizada no arquivo/pasta da task |
| **Auto-fix CSS**    | `npm run lint:css:fix`       | Fim da task ou ajuste em lote no CSS                           | Corrige automaticamente formatação, hexadecimais e regras estáticas no CSS       |
| **Commit**          | `git commit`                 | Ao finalizar as mudanças (fim da task)                         | O Husky valida as regras de qualidade automaticamente antes de salvar            |
| **Build**           | `npm run build`              | Antes de entregar ou publicar                                  | Compila, minifica e otimiza a aplicação na pasta `dist` para produção            |
| **Preview**         | `npm run preview`            | Após a build, antes de enviar para o ar                        | Abre um servidor local rodando os arquivos da `dist` para validação final        |

## Padronização de Código e Linters

- **ESLint:** Analisa o código JavaScript em busca de erros de sintaxe, lógica e boas práticas.
- **Stylelint:** Valida e padroniza a estrutura das folhas de estilo CSS (`.stylelintrc.json`). O projeto conta com `.stylelintignore` para evitar checagens em arquivos de build (`dist/`).
- **Prettier:** Mantém a formatação visual do código consistente sem conflitar com os linters.

## ⚠️ Boas Práticas e Cuidados Importantes

### Sincronização Segura

Evite usar o `npm install` no dia a dia se você não está adicionando novos pacotes. Use sempre o `npm ci` para garantir que sua pasta `node_modules` esteja idêntica ao histórico do projeto sem corromper o arquivo `package-lock.json`. Se o linter ou terminal apontar vulnerabilidades após um `npm install`, utilize o `npm audit fix`.

### Linting Cirúrgico

Em projetos grandes, rodar o `npm run lint:fix` de forma generalizada pode alterar arquivos de outros colegas e causar conflitos de código. A boa prática profissional é:

1. Rodar `npm run lint` e `npm run lint:css` para mapear os problemas reais.
2. Corrigir erros de lógica ou avisos críticos manualmente no VS Code.
3. Usar o linter com o modificador `--fix` apontando estritamente para o arquivo ou componente que você editou:
   ```bash
   npx eslint src/components/MeuBotao/ --fix
   ```

---

Desenvolvido por [Victor Martins](https://github.com/VictorMartinsD)
Front-End Developer focado em aplicações web modernas e performance.
