# Controle de Presença

Site completo para pesquisa de pessoas e controle de presença.

## Estrutura

- `index.html` — página e funcionamento do sistema.
- `dados.json` — dados importados do Excel.
- `README.md` — este manual.

A planilha original utilizada foi a aba **event_participations**, com **108 registros**.

## Como atualizar a lista

Abra o `dados.json` e substitua o conteúdo pelos novos dados no mesmo formato JSON.

Outra opção é me enviar uma nova planilha e eu gero um novo `dados.json` para você.

## Publicar no GitHub Pages

1. Acesse o GitHub.
2. Clique em **New repository**.
3. Crie um repositório chamado, por exemplo, `controle-presenca`.
4. Abra o repositório.
5. Clique em **Add file → Upload files**.
6. Envie **index.html**, **dados.json** e **README.md**.
7. Clique em **Commit changes**.
8. Vá para **Settings → Pages**.
9. Em **Build and deployment**, selecione **Deploy from a branch**.
10. Selecione a branch **main** e a pasta **/(root)**.
11. Clique em **Save**.
12. Aguarde a publicação.

O endereço será semelhante a:
`https://SEU-USUARIO.github.io/controle-presenca/`

## Funcionamento da presença

O botão "Presente" usa `localStorage` do navegador. Assim, ao atualizar a página, os checks continuam no mesmo navegador/dispositivo.

O botão "Exportar presença" cria um CSV contendo todos os dados e uma coluna adicional chamada `Presente`.

## Atenção à privacidade

O `dados.json` contém os dados da lista. Se o repositório for público, esses dados poderão ser acessados por qualquer pessoa. Para informações pessoais, avalie usar um repositório privado ou outra forma de hospedagem com controle de acesso.
