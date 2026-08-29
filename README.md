# Controle de Presença — versão compartilhada

Esta versão mantém a lista e os checks de presença em um banco Supabase, para que o mesmo estado apareça em celular, outro navegador e outro computador.

## Arquivos

- `index.html` — site.
- `dados.json` — cópia inicial dos 109 registros da planilha, incluindo **Angelica Guadalupe**.
- `config.js` — onde entram a URL e a Publishable Key do Supabase.
- `supabase.sql` — criação da tabela e políticas.
- `README.md` — instruções.

## Por que precisamos do Supabase?

O GitHub Pages hospeda arquivos, mas não é um banco de dados. O `localStorage` anterior só funciona em cada navegador/dispositivo. Para compartilhar a presença entre aparelhos, o site precisa gravar em um banco online.

## Configuração

1. Crie uma conta/projeto no Supabase.
2. Abra o SQL Editor e execute `supabase.sql`.
3. Crie a tabela `pessoas` com as colunas:
   - id
   - nome
   - dados
   - presente
   - atualizado_em
4. Importe os registros do `dados.json` para a tabela. Para cada pessoa:
   - `nome` = valor de `Nome`
   - `dados` = objeto JSON com os dados da pessoa
   - `presente` = false
5. No Supabase, copie a **Project URL** e a **Publishable key**.
6. Abra `config.js` e substitua:
   `COLE_AQUI_A_PROJECT_URL`
   e
   `COLE_AQUI_A_PUBLISHABLE_KEY`
7. Envie `index.html`, `config.js`, `dados.json`, `supabase.sql` e `README.md` para o GitHub.
8. Mantenha o GitHub Pages apontando para `main` e `/root`.

A documentação oficial do Supabase mostra a inicialização do cliente com Project URL + Publishable key e recomenda nunca expor a `service_role` key no navegador.

## Busca inteligente

A busca:
- ignora acentos;
- ignora maiúsculas/minúsculas;
- encontra parte do nome;
- permite pesquisar as palavras do nome mesmo fora da ordem.

Exemplo: `angelica guadalupe`, `ANGELICA GUADALUPE` e `angélica guadalupe` encontram a mesma pessoa.

## Segurança

A configuração do SQL é adequada para um protótipo de controle compartilhado, mas permite leitura e atualização anônimas. Para um sistema real com dados pessoais, o ideal é adicionar autenticação e políticas RLS mais restritivas.

## Exportação

A exportação de presença gera CSV em UTF-8 com BOM, separador `;` e quebras de linha compatíveis com o Excel em português.
