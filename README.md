# template-base

Template base para projetos com Vite, JavaScript, Prettier, ESLint e Husky.

## Como usar ao clonar

1. Instale as dependências:

```bash
npm install
```

2. Inicie o projeto em modo desenvolvimento:

```bash
npm run dev
```

3. Quando finalizar uma tarefa, valide e corrija o código:

```bash
npm run lint:fix
npm run lint
```

4. Antes de considerar o projeto pronto, gere a build final:

```bash
npm run build
```

## Fluxo de uso

### 1. Quando alterar dependências

Use `npm install` sempre que precisar sincronizar as dependências do projeto.

- O que faz: instala ou atualiza as dependências do projeto.
- Quando usar: após clonar o repositório, depois de um `git pull` que trouxe mudanças no `package.json`, e sempre que adicionar, remover ou atualizar pacotes.
- Status: obrigatório.
- Consequência: mantém o ambiente do projeto e as ferramentas de lint sincronizados.

### 1.1 Ciclo de desenvolvimento diário

Use `npm run dev` para trabalhar no projeto em tempo real.

- O que faz: inicia o ambiente local de desenvolvimento.
- Quando usar: no começo de cada sessão de trabalho e enquanto estiver editando o código.
- Status: obrigatório durante o desenvolvimento.
- Consequência: você vê as mudanças na hora e consegue identificar erros rapidamente.

### 2. Quando terminar uma funcionalidade

Use este fluxo ao final de uma feature ou tarefa.

1. `npm run lint:fix`
   - O que faz: corrige automaticamente o que o ESLint consegue resolver.
   - O que costuma corrigir: imports desorganizados, variáveis não usadas, pequenas inconsistências de estilo.
   - O que não corrige: erros de lógica ou decisões arquiteturais.
   - Status: opcional, mas recomendado.

2. `npm run lint`
   - O que faz: apenas verifica e mostra o que ainda ficou pendente.
   - Quando usar: depois do `lint:fix`, ou antes de commitar se você quiser conferir manualmente.
   - Status: opcional, mas recomendado.
   - Consequência: mostra warnings e erros que exigem ajuste manual.

3. Ajuste manual no editor
   - Quando usar: se o `lint` ainda apontar problemas.
   - Consequência: você corrige o que a automação não consegue resolver.

### 3. No momento do commit

O Husky + lint-staged rodam automaticamente no `git commit`.

- O que faz: valida os arquivos staged antes do commit ser concluído.
- Status: obrigatório no projeto.
- Resultado: se estiver tudo certo, o commit segue; se houver erro, o commit é bloqueado.

## Comandos principais

Use estes comandos conforme a etapa do projeto:

```bash
npm run dev
```

- Quando usar: no início da sessão de desenvolvimento e durante todo o tempo em que estiver alterando o código.
- Resultado: mantém a aplicação rodando com atualização rápida para você testar mudanças em tempo real.

```bash
npm run build
```

- Quando usar: quando a feature ou o projeto estiver pronto para validação final, entrega ou publicação.
- Resultado: gera a versão de produção do projeto.

```bash
npm install
npm run lint
npm run lint:fix
```

## Regra prática

- `npm run lint:fix` corrige automaticamente o que puder.
- `npm run lint` confirma o que ainda precisa de atenção.
- O pre-commit valida tudo de novo antes do commit.
- `npm install` entra sempre que o projeto precisar sincronizar dependências locais com o `package.json`.

Se quiser usar esse template em outro projeto, mantenha esse fluxo e adapte o README final do projeto novo ao final do desenvolvimento.

---

Desenvolvido por [Victor Martins](https://github.com/VictorMartinsD)
Front-End Developer focado em aplicações web modernas e performance.
