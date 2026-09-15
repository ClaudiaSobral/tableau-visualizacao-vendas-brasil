# tableau-visualizacao-vendas-brasil
Repositório auxiliar para demonstrar meu processo de aprendizado em Tableau


> Link do painel: [https://public.tableau.com/app/profile/claudia.sobral3111/viz/Vendasporregio_17894167074070/Painel1](https://public.tableau.com/app/profile/claudia.sobral3111/viz/Vendasporregio_17894167074070/Painel1)

## 📊 A ferramenta
O Tableau Public é uma ferramenta gratuita de visualização especializada em lidar com dados relacionais. Nela, é possível publicar sua visualização de forma gratuita e explorar o trabalho de outros usuários.
Há uma vasta gama de modelos disponíveis.

## 🌆 O cenário 
A partir da disponibilização de dois datasets, o dataset.csv, contendo dados de clientes e seus pedidos, e o dataset estados_brasileiros.csv (com informações geoespaciais), o desafio era plotar visualizações que mostrassem de forma bastante intuitiva o faturamento por diferentes níveis de granularidade geográfica (país, estados e cidades).

## 👣 O passo a passo
- Upload das tabelas .csv na aba "Fonte de Dados" do Tableau Public
- Mudança da tipagem das colunas "Sigla", "Estado" e "Região" para função geográfica
- Join das duas tabelas através da coluna Customer State (de dataset.csv) e Sigla (de estados_brasileiros.csv)
- Criação das planilhas "País", "Estado" e "Cidade"
- Criação dos parâmetros e campos calculados para filtrar a visualização do painel final por granularidade
- Criação do painel "Vendas por país, região e cidade", utilizando containers flexíveis para melhor adaptabilidade da visualização em diversos dispositivos.
- Edição e retoques finais no painel (ajuste de filtro e teste de funcionalidades).

## 🧠 Desafios encontrados
  - Inicialmente, a join foi feita de forma incorreta na coluna "Customer State" com "Estado", o que causou erro na união. Isso foi rapidamente resolvido substituindo "Estado" por "Sigla"
  - O maior desafio foi a criação de parâmetros e campos calculados funcionais no painel.
    - Isso foi solucionado pela criação do parâmetro mestre "Seletor de nível do mapa" ([Seletor de nível do mapa]) com uma lista de valores: "País", "Estado" e "Cidade".
    - Em seguida, criou-se o Campo Calculado "Filtro Visibilidade do Mapa", arrastando o parâmetro para dentro dele. Isso fez com que o campo "lesse" o parâmetro.
    - O Campo Calculado "Filtro Visibilidade do Mapa" foi aplicado ao filtro de cada uma das três planilhas. Ao abrir o filtro, foi inserido no campo personalizado o valor correspondente da planilha ("País", "Estado" e "Cidade")
    - Por fim, as planilhas foram plottadas no painel final, explicitando o seletor com a opção "Mostrar parâmetro"
   
## 📝 Aprendizados
O Tableau a princípio já era uma ferramenta que eu conhecia, mas essa foi uma oportunidade para aprender mais sobre as particularidades dela. Os principais aprendizados foram:
  - Criação de joins diretamente na ferramenta;
  - Criação de seletores personalizados.

## ✨ Conclusão
- A partir da visualização, é possível perceber uma concentração das compras no Sudeste, Sul e Nordeste (principalmente no litoral deste).
