# Documento de Casos de Testes - Sistema McBugs

**Sistema:** McBugs - Totem de Autoatendimento para Restaurantes  
**Versão:** 1.0  
**Data:** 2024  
**Autor:** Analista de Qualidade Sênior

---

## Índice

1. [Casos de Teste - Tela Inicial](#casos-de-teste---tela-inicial)
2. [Casos de Teste - Menu e Navegação](#casos-de-teste---menu-e-navegação)
3. [Casos de Teste - Detalhes do Produto](#casos-de-teste---detalhes-do-produto)
4. [Casos de Teste - Carrinho de Compras](#casos-de-teste---carrinho-de-compras)
5. [Casos de Teste - Finalização de Pedido](#casos-de-teste---finalização-de-pedido)
6. [Casos de Teste - Pagamento](#casos-de-teste---pagamento)
7. [Casos de Teste - Confirmação de Pedido](#casos-de-teste---confirmação-de-pedido)
8. [Casos de Teste - Cancelamento](#casos-de-teste---cancelamento)

---

## Casos de Teste - Tela Inicial

### **CT001 - Selecionar Tipo de Pedido "Para Comer Aqui"**

#### **Objetivo**

Validar que o sistema permite ao usuário selecionar a opção "Para comer aqui" e redireciona corretamente para a página do menu.

#### **Pré-Condições**

- O sistema McBugs deve estar online e acessível.
- O navegador deve estar configurado corretamente para acessar o sistema.
- A conexão com o banco de dados Supabase deve estar estabelecida.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Acessar a página inicial do sistema | A página inicial deve ser carregada, exibindo o logo "McBugs", mensagem de boas-vindas e duas opções: "Para comer aqui" e "Para levar". |
| 2      | Verificar a exibição das opções de pedido | As duas opções devem estar visíveis com seus respectivos ícones e textos descritivos. |
| 3      | Clicar no botão "Para comer aqui" | O sistema deve registrar o tipo de pedido como "dine-in" e redirecionar o usuário para a página do menu. |
| 4      | Verificar a navegação para o menu | A página do menu deve ser carregada corretamente, exibindo as categorias de produtos disponíveis. |

#### **Resultados Esperados**

- O tipo de pedido "dine-in" deve ser armazenado no contexto do carrinho.
- O usuário deve ser redirecionado para a página `/menu`.
- A navegação deve ocorrer sem erros ou mensagens de erro.

#### **Critérios de Aceitação**

- A seleção do tipo de pedido deve ser registrada corretamente.
- A navegação para o menu deve ocorrer imediatamente após o clique.
- Não deve ocorrer nenhum erro durante o processo.

---

### **CT002 - Selecionar Tipo de Pedido "Para Levar"**

#### **Objetivo**

Validar que o sistema permite ao usuário selecionar a opção "Para levar" e redireciona corretamente para a página do menu.

#### **Pré-Condições**

- O sistema McBugs deve estar online e acessível.
- O navegador deve estar configurado corretamente para acessar o sistema.
- A conexão com o banco de dados Supabase deve estar estabelecida.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Acessar a página inicial do sistema | A página inicial deve ser carregada, exibindo o logo "McBugs", mensagem de boas-vindas e duas opções: "Para comer aqui" e "Para levar". |
| 2      | Verificar a exibição das opções de pedido | As duas opções devem estar visíveis com seus respectivos ícones e textos descritivos. |
| 3      | Clicar no botão "Para levar" | O sistema deve registrar o tipo de pedido como "takeaway" e redirecionar o usuário para a página do menu. |
| 4      | Verificar a navegação para o menu | A página do menu deve ser carregada corretamente, exibindo as categorias de produtos disponíveis. |

#### **Resultados Esperados**

- O tipo de pedido "takeaway" deve ser armazenado no contexto do carrinho.
- O usuário deve ser redirecionado para a página `/menu`.
- A navegação deve ocorrer sem erros ou mensagens de erro.

#### **Critérios de Aceitação**

- A seleção do tipo de pedido deve ser registrada corretamente.
- A navegação para o menu deve ocorrer imediatamente após o clique.
- Não deve ocorrer nenhum erro durante o processo.

---

## Casos de Teste - Menu e Navegação

### **CT003 - Visualizar Menu com Categorias**

#### **Objetivo**

Validar que o sistema exibe corretamente o menu com todas as categorias de produtos (Lanches, Fritas, Bebidas, Sobremesas) e permite a navegação entre elas.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O usuário deve ter selecionado um tipo de pedido (dine-in ou takeaway) na tela inicial.
- O usuário deve estar na página do menu (`/menu`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Acessar a página do menu | A página do menu deve ser carregada, exibindo a imagem hero, informações do restaurante e as abas de categorias. |
| 2      | Verificar a exibição das categorias | As categorias "Lanches", "Fritas", "Bebidas" e "Sobremesas" devem estar visíveis nas abas. |
| 3      | Verificar a categoria ativa por padrão | A categoria "Lanches" deve estar selecionada por padrão. |
| 4      | Verificar a exibição dos produtos | Os produtos da categoria "Lanches" devem ser exibidos em formato de grid. |
| 5      | Clicar na aba "Fritas" | A categoria "Fritas" deve ser selecionada e os produtos dessa categoria devem ser exibidos. |
| 6      | Clicar na aba "Bebidas" | A categoria "Bebidas" deve ser selecionada e os produtos dessa categoria devem ser exibidos. |
| 7      | Clicar na aba "Sobremesas" | A categoria "Sobremesas" deve ser selecionada e os produtos dessa categoria devem ser exibidos. |

#### **Resultados Esperados**

- Todas as categorias devem estar visíveis e funcionais.
- A troca entre categorias deve ocorrer instantaneamente.
- Apenas os produtos da categoria selecionada devem ser exibidos.
- Cada produto deve exibir nome, imagem e preço.

#### **Critérios de Aceitação**

- Todas as quatro categorias devem estar acessíveis.
- A filtragem de produtos por categoria deve funcionar corretamente.
- Não deve ocorrer nenhum erro durante a navegação entre categorias.

---

### **CT004 - Navegar de Volta para a Tela Inicial**

#### **Objetivo**

Validar que o sistema permite ao usuário retornar à tela inicial a partir do menu.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O usuário deve estar na página do menu (`/menu`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar o botão de voltar na página do menu | O botão com ícone de seta para a esquerda deve estar visível no canto superior esquerdo da imagem hero. |
| 2      | Clicar no botão de voltar | O sistema deve redirecionar o usuário para a página inicial (`/`). |
| 3      | Verificar a página inicial | A página inicial deve ser exibida com as opções "Para comer aqui" e "Para levar". |

#### **Resultados Esperados**

- O botão de voltar deve estar visível e funcional.
- A navegação para a página inicial deve ocorrer corretamente.
- O tipo de pedido selecionado anteriormente pode ser mantido ou resetado (comportamento a ser validado).

#### **Critérios de Aceitação**

- A navegação de volta deve funcionar corretamente.
- Não deve ocorrer nenhum erro durante o processo.

---

## Casos de Teste - Detalhes do Produto

### **CT005 - Visualizar Detalhes de um Produto**

#### **Objetivo**

Validar que o sistema exibe corretamente todas as informações detalhadas de um produto quando o usuário clica nele.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O usuário deve estar na página do menu (`/menu`).
- Deve haver produtos disponíveis na categoria selecionada.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Selecionar um produto no menu | O produto deve ser clicável e destacado ao passar o mouse. |
| 2      | Clicar em um produto | O sistema deve redirecionar para a página de detalhes do produto (`/product/{id}`). |
| 3      | Verificar a imagem do produto | A imagem do produto deve ser exibida em tamanho grande no topo da página. |
| 4      | Verificar o nome do produto | O nome do produto deve ser exibido de forma destacada. |
| 5      | Verificar o preço do produto | O preço do produto deve ser exibido em formato monetário (R$). |
| 6      | Verificar a descrição do produto | A descrição do produto deve ser exibida na seção "Sobre". |
| 7      | Verificar os ingredientes | Se o produto tiver ingredientes, eles devem ser listados na seção "Ingredientes". |
| 8      | Verificar o controle de quantidade | O controle de quantidade deve estar visível, permitindo aumentar ou diminuir a quantidade (mínimo 1). |

#### **Resultados Esperados**

- Todas as informações do produto devem ser exibidas corretamente.
- A imagem do produto deve carregar sem erros.
- O controle de quantidade deve estar funcional.
- O botão "Quero" deve exibir o valor total (preço × quantidade).

#### **Critérios de Aceitação**

- Todas as informações do produto devem estar corretas e legíveis.
- A página de detalhes deve carregar sem erros.
- O controle de quantidade deve funcionar corretamente.

---

### **CT006 - Adicionar Produto ao Carrinho a partir dos Detalhes**

#### **Objetivo**

Validar que o sistema permite adicionar um produto ao carrinho com a quantidade especificada a partir da página de detalhes.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O usuário deve estar na página de detalhes de um produto (`/product/{id}`).
- O carrinho pode estar vazio ou conter outros itens.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Verificar a quantidade inicial | A quantidade deve estar definida como 1 por padrão. |
| 2      | Aumentar a quantidade para 2 | O controle de quantidade deve permitir aumentar a quantidade e o botão "Quero" deve atualizar o valor total. |
| 3      | Clicar no botão "Quero" | O produto deve ser adicionado ao carrinho com a quantidade especificada. |
| 4      | Verificar o redirecionamento | O sistema deve redirecionar automaticamente para a página do menu (`/menu`). |
| 5      | Verificar o carrinho | O contador de itens no carrinho (CartBar) deve ser atualizado, refletindo a quantidade adicionada. |

#### **Resultados Esperados**

- O produto deve ser adicionado ao carrinho com a quantidade correta.
- O valor total no botão "Quero" deve refletir o preço × quantidade.
- O redirecionamento para o menu deve ocorrer após adicionar o produto.
- O carrinho deve ser atualizado visualmente.

#### **Critérios de Aceitação**

- O produto deve ser adicionado corretamente ao carrinho.
- A quantidade especificada deve ser respeitada.
- O redirecionamento deve ocorrer sem erros.

---

### **CT007 - Adicionar Produto Duplicado ao Carrinho**

#### **Objetivo**

Validar que o sistema incrementa a quantidade quando um produto já existente no carrinho é adicionado novamente.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- O usuário deve estar na página de detalhes de um produto que já está no carrinho.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Verificar o carrinho atual | O carrinho deve conter pelo menos um item com quantidade conhecida. |
| 2      | Navegar para os detalhes de um produto que já está no carrinho | A página de detalhes do produto deve ser carregada. |
| 3      | Definir a quantidade como 2 | O controle de quantidade deve permitir definir a quantidade. |
| 4      | Clicar no botão "Quero" | O sistema deve adicionar mais 2 unidades do produto ao carrinho. |
| 5      | Verificar o carrinho | A quantidade total do produto no carrinho deve ser a quantidade anterior + 2. |

#### **Resultados Esperados**

- O produto não deve ser duplicado como item separado no carrinho.
- A quantidade do produto existente deve ser incrementada.
- O total do carrinho deve ser atualizado corretamente.

#### **Critérios de Aceitação**

- A quantidade do produto deve ser incrementada corretamente.
- Não deve haver itens duplicados no carrinho.
- O cálculo do total deve estar correto.

---

## Casos de Teste - Carrinho de Compras

### **CT008 - Visualizar Carrinho Vazio**

#### **Objetivo**

Validar que o sistema exibe uma mensagem apropriada quando o carrinho está vazio.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve estar vazio (sem itens adicionados).
- O usuário deve acessar a página do carrinho (`/cart`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Acessar a página do carrinho sem itens | A página do carrinho deve ser carregada. |
| 2      | Verificar a mensagem de carrinho vazio | Deve ser exibida uma mensagem indicando que o carrinho está vazio, com ícone e texto "Nada Encontrado Aqui". |
| 3      | Verificar o botão "Ver cardápio" | Deve haver um botão que permite retornar ao menu. |
| 4      | Clicar no botão "Ver cardápio" | O sistema deve redirecionar para a página do menu. |

#### **Resultados Esperados**

- A mensagem de carrinho vazio deve ser clara e informativa.
- O botão para retornar ao menu deve estar visível e funcional.
- Não deve haver opções de finalizar pedido quando o carrinho está vazio.

#### **Critérios de Aceitação**

- A interface deve ser intuitiva e informar claramente que o carrinho está vazio.
- A navegação de volta ao menu deve funcionar corretamente.

---

### **CT009 - Visualizar Itens no Carrinho**

#### **Objetivo**

Validar que o sistema exibe corretamente todos os itens adicionados ao carrinho com suas informações.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- O usuário deve acessar a página do carrinho (`/cart`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Acessar a página do carrinho com itens | A página do carrinho deve ser carregada. |
| 2      | Verificar a exibição dos itens | Cada item do carrinho deve ser exibido com imagem, nome, preço unitário e quantidade. |
| 3      | Verificar o cálculo do subtotal por item | O subtotal de cada item (preço × quantidade) deve ser exibido corretamente. |
| 4      | Verificar o total do pedido | O total geral do pedido deve ser exibido em destaque no card "Total do pedido". |
| 5      | Verificar os botões de ação | Os botões "Finalizar pedido" e "Continuar comprando" devem estar visíveis na parte inferior da tela. |

#### **Resultados Esperados**

- Todos os itens do carrinho devem ser exibidos corretamente.
- Os valores devem ser calculados e exibidos corretamente.
- O total do pedido deve refletir a soma de todos os itens.

#### **Critérios de Aceitação**

- As informações dos itens devem estar corretas e legíveis.
- O cálculo do total deve estar matematicamente correto.
- A interface deve ser clara e organizada.

---

### **CT010 - Atualizar Quantidade de Item no Carrinho**

#### **Objetivo**

Validar que o sistema permite aumentar ou diminuir a quantidade de um item no carrinho.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- O usuário deve estar na página do carrinho (`/cart`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar o controle de quantidade de um item | O controle de quantidade deve estar visível para cada item no carrinho. |
| 2      | Clicar no botão de aumentar quantidade | A quantidade do item deve ser incrementada em 1. |
| 3      | Verificar a atualização do subtotal | O subtotal do item deve ser atualizado (preço × nova quantidade). |
| 4      | Verificar a atualização do total | O total do pedido deve ser atualizado para refletir a nova quantidade. |
| 5      | Clicar no botão de diminuir quantidade | A quantidade do item deve ser decrementada em 1. |
| 6      | Verificar a atualização novamente | O subtotal e o total devem ser atualizados corretamente. |

#### **Resultados Esperados**

- A quantidade deve ser atualizada imediatamente ao clicar nos botões.
- Os valores (subtotal e total) devem ser recalculados automaticamente.
- As alterações devem ser persistidas no carrinho.

#### **Critérios de Aceitação**

- A atualização de quantidade deve funcionar corretamente.
- Os cálculos devem estar matematicamente corretos.
- As alterações devem ser salvas no localStorage.

---

### **CT011 - Remover Item do Carrinho**

#### **Objetivo**

Validar que o sistema permite remover um item do carrinho.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- O usuário deve estar na página do carrinho (`/cart`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar o botão de remover item | O botão de remover deve estar visível para cada item no carrinho. |
| 2      | Verificar o total antes da remoção | Anotar o total do pedido antes de remover o item. |
| 3      | Clicar no botão de remover | O item deve ser removido do carrinho imediatamente. |
| 4      | Verificar a atualização do total | O total do pedido deve ser atualizado, subtraindo o valor do item removido. |
| 5      | Verificar a atualização da lista | O item removido não deve mais aparecer na lista de itens do carrinho. |

#### **Resultados Esperados**

- O item deve ser removido imediatamente do carrinho.
- O total do pedido deve ser atualizado corretamente.
- Se o carrinho ficar vazio após a remoção, a mensagem de carrinho vazio deve ser exibida.

#### **Critérios de Aceitação**

- A remoção do item deve funcionar corretamente.
- O total deve ser recalculado corretamente após a remoção.
- A interface deve ser atualizada imediatamente.

---

### **CT012 - Remover Item ao Definir Quantidade como Zero**

#### **Objetivo**

Validar que o sistema remove automaticamente um item do carrinho quando a quantidade é definida como zero.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- O usuário deve estar na página do carrinho (`/cart`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar o controle de quantidade de um item | O controle de quantidade deve estar visível. |
| 2      | Diminuir a quantidade até chegar a 1 | A quantidade deve ser decrementada normalmente. |
| 3      | Diminuir a quantidade de 1 para 0 | O sistema deve remover automaticamente o item do carrinho quando a quantidade chegar a 0. |
| 4      | Verificar a remoção do item | O item não deve mais aparecer no carrinho. |
| 5      | Verificar a atualização do total | O total do pedido deve ser atualizado, removendo o valor do item. |

#### **Resultados Esperados**

- O item deve ser removido automaticamente quando a quantidade chega a zero.
- O total do pedido deve ser atualizado corretamente.
- Não deve ocorrer nenhum erro durante o processo.

#### **Critérios de Aceitação**

- A remoção automática deve funcionar corretamente.
- O total deve ser recalculado corretamente.
- Não deve haver itens com quantidade zero no carrinho.

---

## Casos de Teste - Finalização de Pedido

### **CT013 - Finalizar Pedido com Nome Válido**

#### **Objetivo**

Validar que o sistema permite finalizar um pedido quando o nome do cliente é informado corretamente.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- O usuário deve estar na página do carrinho (`/cart`).
- A conexão com o banco de dados Supabase deve estar estabelecida.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Clicar no botão "Finalizar pedido" | O drawer de checkout deve ser aberto, exibindo um formulário para inserir o nome do cliente. |
| 2      | Verificar o campo de nome | O campo de nome deve estar visível e editável. |
| 3      | Inserir um nome válido (ex: "João Silva") | O nome deve ser inserido no campo sem erros. |
| 4      | Clicar no botão "Finalizar" | O sistema deve processar o pedido, exibindo uma mensagem de carregamento "enviando a cozinha....". |
| 5      | Aguardar o processamento | O pedido deve ser criado no banco de dados com status "pending". |
| 6      | Verificar o redirecionamento | Após o processamento, o sistema deve redirecionar para a página de pagamento (`/payment`). |

#### **Resultados Esperados**

- O pedido deve ser criado no banco de dados com sucesso.
- O pedido deve receber um ID único.
- O carrinho deve ser limpo após a criação do pedido.
- O usuário deve ser redirecionado para a página de pagamento.

#### **Critérios de Aceitação**

- O pedido deve ser criado corretamente no banco de dados.
- Todas as informações do pedido (itens, total, tipo, nome do cliente) devem ser salvas corretamente.
- A navegação para a página de pagamento deve ocorrer sem erros.

---

### **CT014 - Tentar Finalizar Pedido sem Nome**

#### **Objetivo**

Validar que o sistema impede a finalização do pedido quando o nome do cliente não é informado.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- O usuário deve estar na página do carrinho (`/cart`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Clicar no botão "Finalizar pedido" | O drawer de checkout deve ser aberto. |
| 2      | Deixar o campo de nome vazio | O campo de nome deve estar vazio ou contendo apenas espaços em branco. |
| 3      | Tentar clicar no botão "Finalizar" | O botão deve estar desabilitado ou o formulário deve impedir o envio (validação HTML5). |
| 4      | Verificar a mensagem de validação | Se houver validação, uma mensagem deve indicar que o nome é obrigatório. |

#### **Resultados Esperados**

- O sistema deve impedir a finalização do pedido sem nome.
- Uma validação deve ser exibida indicando que o campo é obrigatório.
- O drawer deve permanecer aberto até que um nome válido seja inserido.

#### **Critérios de Aceitação**

- A validação do campo nome deve funcionar corretamente.
- O pedido não deve ser criado sem um nome válido.
- A interface deve informar claramente o erro ao usuário.

---

### **CT015 - Cancelar Finalização de Pedido**

#### **Objetivo**

Validar que o sistema permite cancelar o processo de finalização de pedido e retornar ao carrinho.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- O usuário deve estar na página do carrinho (`/cart`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Clicar no botão "Finalizar pedido" | O drawer de checkout deve ser aberto. |
| 2      | Verificar o botão "Cancelar" | O botão "Cancelar" deve estar visível no drawer. |
| 3      | Clicar no botão "Cancelar" | O drawer deve ser fechado e o usuário deve retornar à visualização do carrinho. |
| 4      | Verificar o estado do carrinho | O carrinho deve permanecer inalterado, com todos os itens ainda presentes. |

#### **Resultados Esperados**

- O drawer deve ser fechado ao clicar em "Cancelar".
- O carrinho deve permanecer inalterado.
- Nenhum pedido deve ser criado no banco de dados.

#### **Critérios de Aceitação**

- O cancelamento deve funcionar corretamente.
- O estado do carrinho não deve ser alterado.
- Não deve ocorrer nenhum erro durante o processo.

---

## Casos de Teste - Pagamento

### **CT016 - Visualizar Opções de Pagamento**

#### **Objetivo**

Validar que o sistema exibe corretamente todas as opções de pagamento disponíveis.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Um pedido deve ter sido criado com sucesso.
- O usuário deve estar na página de pagamento (`/payment`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Acessar a página de pagamento | A página de pagamento deve ser carregada, exibindo um resumo do pedido. |
| 2      | Verificar o resumo do pedido | O resumo deve exibir o número do pedido e o total a pagar. |
| 3      | Verificar as opções de pagamento | Devem ser exibidas três opções: "PIX", "Cartão de Débito" e "Cartão de Crédito". |
| 4      | Verificar as informações de cada opção | Cada opção deve exibir ícone, nome e descrição "Pagamento no balcão na hora da retirada". |
| 5      | Verificar o botão de cancelar | Deve haver um botão "Cancelar Pedido" visível na parte inferior da página. |

#### **Resultados Esperados**

- Todas as três opções de pagamento devem estar visíveis e clicáveis.
- O resumo do pedido deve exibir informações corretas.
- A interface deve ser clara e intuitiva.

#### **Critérios de Aceitação**

- Todas as opções de pagamento devem estar acessíveis.
- As informações do pedido devem estar corretas.
- A interface deve ser responsiva e funcional.

---

### **CT017 - Selecionar Pagamento via PIX**

#### **Objetivo**

Validar que o sistema permite selecionar o pagamento via PIX e redireciona para a página de confirmação.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Um pedido deve ter sido criado com sucesso.
- O usuário deve estar na página de pagamento (`/payment`).
- A conexão com o banco de dados Supabase deve estar estabelecida.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar a opção "PIX" | A opção de pagamento PIX deve estar visível na lista de métodos de pagamento. |
| 2      | Clicar na opção "PIX" | O sistema deve atualizar o método de pagamento do pedido no banco de dados para "pix". |
| 3      | Verificar o redirecionamento | O sistema deve redirecionar para a página de confirmação (`/payment/pix/confirm`). |
| 4      | Verificar a atualização no banco | O método de pagamento do pedido deve ser atualizado para "pix" no banco de dados. |

#### **Resultados Esperados**

- O método de pagamento deve ser atualizado no banco de dados.
- O redirecionamento deve ocorrer corretamente.
- A página de confirmação deve exibir as informações corretas do pagamento PIX.

#### **Critérios de Aceitação**

- A seleção do método de pagamento deve funcionar corretamente.
- A atualização no banco de dados deve ser bem-sucedida.
- A navegação deve ocorrer sem erros.

---

### **CT018 - Selecionar Pagamento via Cartão de Débito**

#### **Objetivo**

Validar que o sistema permite selecionar o pagamento via cartão de débito e redireciona para a página de confirmação.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Um pedido deve ter sido criado com sucesso.
- O usuário deve estar na página de pagamento (`/payment`).
- A conexão com o banco de dados Supabase deve estar estabelecida.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar a opção "Cartão de Débito" | A opção de pagamento Cartão de Débito deve estar visível na lista de métodos de pagamento. |
| 2      | Clicar na opção "Cartão de Débito" | O sistema deve atualizar o método de pagamento do pedido no banco de dados para "debit". |
| 3      | Verificar o redirecionamento | O sistema deve redirecionar para a página de confirmação (`/payment/debit/confirm`). |
| 4      | Verificar a atualização no banco | O método de pagamento do pedido deve ser atualizado para "debit" no banco de dados. |

#### **Resultados Esperados**

- O método de pagamento deve ser atualizado no banco de dados.
- O redirecionamento deve ocorrer corretamente.
- A página de confirmação deve exibir as informações corretas do pagamento via cartão de débito.

#### **Critérios de Aceitação**

- A seleção do método de pagamento deve funcionar corretamente.
- A atualização no banco de dados deve ser bem-sucedida.
- A navegação deve ocorrer sem erros.

---

### **CT019 - Selecionar Pagamento via Cartão de Crédito**

#### **Objetivo**

Validar que o sistema permite selecionar o pagamento via cartão de crédito e redireciona para a página de confirmação.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Um pedido deve ter sido criado com sucesso.
- O usuário deve estar na página de pagamento (`/payment`).
- A conexão com o banco de dados Supabase deve estar estabelecida.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar a opção "Cartão de Crédito" | A opção de pagamento Cartão de Crédito deve estar visível na lista de métodos de pagamento. |
| 2      | Clicar na opção "Cartão de Crédito" | O sistema deve atualizar o método de pagamento do pedido no banco de dados para "credit". |
| 3      | Verificar o redirecionamento | O sistema deve redirecionar para a página de confirmação (`/payment/credit/confirm`). |
| 4      | Verificar a atualização no banco | O método de pagamento do pedido deve ser atualizado para "credit" no banco de dados. |

#### **Resultados Esperados**

- O método de pagamento deve ser atualizado no banco de dados.
- O redirecionamento deve ocorrer corretamente.
- A página de confirmação deve exibir as informações corretas do pagamento via cartão de crédito.

#### **Critérios de Aceitação**

- A seleção do método de pagamento deve funcionar corretamente.
- A atualização no banco de dados deve ser bem-sucedida.
- A navegação deve ocorrer sem erros.

---

### **CT020 - Acessar Página de Pagamento sem Pedido**

#### **Objetivo**

Validar que o sistema redireciona o usuário quando tenta acessar a página de pagamento sem um pedido ativo.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Não deve haver um pedido ativo no contexto do carrinho.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Tentar acessar diretamente a página de pagamento (`/payment`) | O sistema deve detectar que não há pedido ativo. |
| 2      | Verificar o redirecionamento | O sistema deve redirecionar automaticamente para a página inicial (`/`). |

#### **Resultados Esperados**

- O sistema deve detectar a ausência de um pedido ativo.
- O redirecionamento para a página inicial deve ocorrer automaticamente.
- Não deve ocorrer nenhum erro durante o processo.

#### **Critérios de Aceitação**

- A validação de pedido ativo deve funcionar corretamente.
- O redirecionamento deve ocorrer sem erros.
- A experiência do usuário deve ser preservada.

---

## Casos de Teste - Confirmação de Pedido

### **CT021 - Visualizar Confirmação de Pedido com PIX**

#### **Objetivo**

Validar que o sistema exibe corretamente todas as informações de confirmação do pedido quando o pagamento é via PIX.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Um pedido deve ter sido criado e o método de pagamento PIX deve ter sido selecionado.
- O usuário deve estar na página de confirmação (`/payment/pix/confirm`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Acessar a página de confirmação | A página de confirmação deve ser carregada. |
| 2      | Verificar o cabeçalho | Deve ser exibido o ícone e nome "PIX" no cabeçalho. |
| 3      | Verificar o resumo do pedido | O resumo deve exibir o número do pedido e o total a pagar. |
| 4      | Verificar as instruções de pagamento | Deve ser exibida uma seção com instruções "Pagamento no Balcão" informando que o pagamento será feito com PIX. |
| 5      | Verificar os detalhes do pedido | Os detalhes devem incluir: nome do cliente, tipo de pedido, forma de pagamento e data. |
| 6      | Verificar a lista de itens | Todos os itens do pedido devem ser listados com quantidade e preço. |
| 7      | Verificar a mensagem para dine-in | Se o tipo de pedido for "dine-in", deve ser exibida uma mensagem informando para aguardar ser chamado pelo número do pedido. |
| 8      | Verificar o botão "Fazer Novo Pedido" | O botão deve estar visível na parte inferior da página. |

#### **Resultados Esperados**

- Todas as informações do pedido devem ser exibidas corretamente.
- As instruções de pagamento devem ser claras e específicas para PIX.
- A interface deve ser organizada e fácil de entender.

#### **Critérios de Aceitação**

- Todas as informações devem estar corretas e legíveis.
- A página deve carregar sem erros.
- A experiência do usuário deve ser positiva.

---

### **CT022 - Visualizar Confirmação de Pedido com Cartão**

#### **Objetivo**

Validar que o sistema exibe corretamente todas as informações de confirmação do pedido quando o pagamento é via cartão (débito ou crédito).

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Um pedido deve ter sido criado e o método de pagamento cartão (débito ou crédito) deve ter sido selecionado.
- O usuário deve estar na página de confirmação (`/payment/debit/confirm` ou `/payment/credit/confirm`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Acessar a página de confirmação | A página de confirmação deve ser carregada. |
| 2      | Verificar o cabeçalho | Deve ser exibido o ícone de cartão e o nome correto ("Cartão de Débito" ou "Cartão de Crédito") no cabeçalho. |
| 3      | Verificar o resumo do pedido | O resumo deve exibir o número do pedido e o total a pagar. |
| 4      | Verificar as instruções de pagamento | Deve ser exibida uma seção com instruções "Pagamento no Balcão" informando que o pagamento será feito com cartão. |
| 5      | Verificar os detalhes do pedido | Os detalhes devem incluir: nome do cliente, tipo de pedido, forma de pagamento e data. |
| 6      | Verificar a lista de itens | Todos os itens do pedido devem ser listados com quantidade e preço. |
| 7      | Verificar a mensagem para dine-in | Se o tipo de pedido for "dine-in", deve ser exibida uma mensagem informando para aguardar ser chamado pelo número do pedido. |
| 8      | Verificar o botão "Fazer Novo Pedido" | O botão deve estar visível na parte inferior da página. |

#### **Resultados Esperados**

- Todas as informações do pedido devem ser exibidas corretamente.
- As instruções de pagamento devem ser claras e específicas para cartão.
- O tipo de cartão (débito ou crédito) deve ser exibido corretamente.

#### **Critérios de Aceitação**

- Todas as informações devem estar corretas e legíveis.
- A página deve carregar sem erros.
- O método de pagamento deve ser exibido corretamente.

---

### **CT023 - Fazer Novo Pedido após Confirmação**

#### **Objetivo**

Validar que o sistema permite iniciar um novo pedido após a confirmação do pedido anterior.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O usuário deve estar na página de confirmação de pedido (`/payment/{method}/confirm`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar o botão "Fazer Novo Pedido" | O botão deve estar visível na parte inferior da página de confirmação. |
| 2      | Clicar no botão "Fazer Novo Pedido" | O sistema deve limpar o estado do pedido atual (resetOrder). |
| 3      | Verificar o redirecionamento | O sistema deve redirecionar para a página inicial (`/`). |
| 4      | Verificar o estado limpo | O carrinho deve estar vazio e não deve haver pedido ativo. |
| 5      | Verificar a página inicial | A página inicial deve ser exibida com as opções "Para comer aqui" e "Para levar". |

#### **Resultados Esperados**

- O estado do pedido anterior deve ser limpo completamente.
- O carrinho deve estar vazio.
- O usuário deve ser redirecionado para a página inicial.
- Um novo pedido pode ser iniciado normalmente.

#### **Critérios de Aceitação**

- A limpeza do estado deve funcionar corretamente.
- O redirecionamento deve ocorrer sem erros.
- O sistema deve estar pronto para um novo pedido.

---

### **CT024 - Voltar da Página de Confirmação para Pagamento**

#### **Objetivo**

Validar que o sistema permite retornar à página de pagamento a partir da página de confirmação.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O usuário deve estar na página de confirmação de pedido (`/payment/{method}/confirm`).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar o botão de voltar | O botão com ícone de seta para a esquerda deve estar visível no cabeçalho da página. |
| 2      | Clicar no botão de voltar | O sistema deve redirecionar para a página de pagamento (`/payment`). |
| 3      | Verificar a página de pagamento | A página de pagamento deve ser exibida com todas as opções de pagamento disponíveis. |
| 4      | Verificar o estado do pedido | O pedido deve permanecer ativo e as informações devem ser mantidas. |

#### **Resultados Esperados**

- O botão de voltar deve estar funcional.
- A navegação de volta deve ocorrer corretamente.
- O estado do pedido deve ser preservado.

#### **Critérios de Aceitação**

- A navegação de volta deve funcionar corretamente.
- O estado do pedido não deve ser perdido.
- Não deve ocorrer nenhum erro durante o processo.

---

## Casos de Teste - Cancelamento

### **CT025 - Cancelar Pedido na Página de Pagamento**

#### **Objetivo**

Validar que o sistema permite cancelar um pedido na página de pagamento e retornar à tela inicial.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Um pedido deve ter sido criado com sucesso.
- O usuário deve estar na página de pagamento (`/payment`).
- A conexão com o banco de dados Supabase deve estar estabelecida.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Localizar o botão "Cancelar Pedido" | O botão "Cancelar Pedido" deve estar visível na parte inferior da página de pagamento. |
| 2      | Clicar no botão "Cancelar Pedido" | O sistema deve atualizar o status do pedido no banco de dados para "cancelled". |
| 3      | Verificar a limpeza do estado | O carrinho deve ser limpo e o pedido atual deve ser removido do contexto. |
| 4      | Verificar o redirecionamento | O sistema deve redirecionar para a página inicial (`/`). |
| 5      | Verificar o estado no banco | O pedido no banco de dados deve ter o status "cancelled". |

#### **Resultados Esperados**

- O pedido deve ser marcado como "cancelled" no banco de dados.
- O estado do carrinho e do pedido deve ser limpo.
- O usuário deve ser redirecionado para a página inicial.
- Um novo pedido pode ser iniciado normalmente.

#### **Critérios de Aceitação**

- O cancelamento do pedido deve funcionar corretamente.
- A atualização no banco de dados deve ser bem-sucedida.
- O estado do sistema deve ser limpo completamente.

---

### **CT026 - Acessar Página de Confirmação sem Pedido**

#### **Objetivo**

Validar que o sistema redireciona o usuário quando tenta acessar a página de confirmação sem um pedido ativo.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- Não deve haver um pedido ativo no contexto do carrinho.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Tentar acessar diretamente a página de confirmação (`/payment/pix/confirm`) | O sistema deve detectar que não há pedido ativo. |
| 2      | Verificar o redirecionamento | O sistema deve redirecionar automaticamente para a página de pagamento (`/payment`). |

#### **Resultados Esperados**

- O sistema deve detectar a ausência de um pedido ativo.
- O redirecionamento para a página de pagamento deve ocorrer automaticamente.
- Não deve ocorrer nenhum erro durante o processo.

#### **Critérios de Aceitação**

- A validação de pedido ativo deve funcionar corretamente.
- O redirecionamento deve ocorrer sem erros.
- A experiência do usuário deve ser preservada.

---

## Casos de Teste - Persistência e Recuperação

### **CT027 - Persistência do Carrinho no LocalStorage**

#### **Objetivo**

Validar que o sistema persiste os itens do carrinho no localStorage e os recupera ao recarregar a página.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O navegador deve suportar localStorage.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Adicionar itens ao carrinho | Adicionar pelo menos dois produtos diferentes ao carrinho com quantidades variadas. |
| 2      | Verificar o localStorage | Os itens do carrinho devem ser salvos no localStorage com a chave "mcbugs-cart-items". |
| 3      | Recarregar a página | Recarregar a página do menu ou carrinho (F5 ou Ctrl+R). |
| 4      | Verificar a recuperação dos itens | Os itens do carrinho devem ser recuperados e exibidos corretamente após o recarregamento. |
| 5      | Verificar as quantidades | As quantidades dos itens devem estar corretas. |
| 6      | Verificar o total | O total do pedido deve ser calculado corretamente com base nos itens recuperados. |

#### **Resultados Esperados**

- Os itens do carrinho devem ser persistidos no localStorage.
- Os itens devem ser recuperados corretamente após o recarregamento.
- As quantidades e o total devem estar corretos.

#### **Critérios de Aceitação**

- A persistência no localStorage deve funcionar corretamente.
- A recuperação dos dados deve ser bem-sucedida.
- Não deve haver perda de dados durante o recarregamento.

---

### **CT028 - Persistência do Tipo de Pedido no LocalStorage**

#### **Objetivo**

Validar que o sistema persiste o tipo de pedido (dine-in ou takeaway) no localStorage e o recupera ao recarregar a página.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O navegador deve suportar localStorage.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Selecionar o tipo de pedido "Para comer aqui" | O tipo de pedido "dine-in" deve ser salvo no localStorage. |
| 2      | Verificar o localStorage | O tipo de pedido deve ser salvo no localStorage com a chave "mcbugs-order-type". |
| 3      | Recarregar a página | Recarregar a página do menu (F5 ou Ctrl+R). |
| 4      | Verificar a recuperação | O tipo de pedido deve ser recuperado e mantido no contexto. |
| 5      | Repetir o processo com "Para levar" | O tipo de pedido "takeaway" deve ser salvo e recuperado corretamente. |

#### **Resultados Esperados**

- O tipo de pedido deve ser persistido no localStorage.
- O tipo de pedido deve ser recuperado corretamente após o recarregamento.
- O tipo de pedido deve ser mantido durante toda a sessão.

#### **Critérios de Aceitação**

- A persistência do tipo de pedido deve funcionar corretamente.
- A recuperação deve ser bem-sucedida.
- O tipo de pedido deve ser usado corretamente na criação do pedido.

---

## Casos de Teste - Validações e Tratamento de Erros

### **CT029 - Tratamento de Erro ao Criar Pedido sem Conexão**

#### **Objetivo**

Validar que o sistema trata adequadamente erros ao tentar criar um pedido quando não há conexão com o banco de dados.

#### **Pré-Condições**

- O sistema deve estar online e acessível.
- O carrinho deve conter pelo menos um item.
- A conexão com o banco de dados Supabase deve ser interrompida (simular desconexão).

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Interromper a conexão com o banco de dados | Simular uma falha de conexão (desconectar internet ou desabilitar Supabase). |
| 2      | Tentar finalizar o pedido | Preencher o nome do cliente e clicar em "Finalizar". |
| 3      | Verificar o tratamento de erro | O sistema deve detectar o erro e exibir uma mensagem apropriada ao usuário. |
| 4      | Verificar o estado do carrinho | O carrinho deve permanecer inalterado (itens não devem ser perdidos). |
| 5      | Verificar o drawer | O drawer de checkout deve permanecer aberto ou ser reaberto para permitir nova tentativa. |

#### **Resultados Esperados**

- O sistema deve detectar o erro de conexão.
- Uma mensagem de erro deve ser exibida ao usuário.
- O estado do carrinho deve ser preservado.
- O usuário deve poder tentar novamente após restaurar a conexão.

#### **Critérios de Aceitação**

- O tratamento de erro deve funcionar corretamente.
- A experiência do usuário deve ser preservada (sem perda de dados).
- A mensagem de erro deve ser clara e informativa.

---

### **CT030 - Acessar Produto Inexistente**

#### **Objetivo**

Validar que o sistema trata adequadamente tentativas de acessar um produto que não existe.

#### **Pré-Condições**

- O sistema deve estar online e acessível.

#### **Passos**

| **Id** | **Ação**                          | **Resultado Esperado**                            |
|--------|------------------------------------|---------------------------------------------------|
| 1      | Tentar acessar uma URL de produto inexistente | Acessar diretamente uma URL como `/product/produto-inexistente`. |
| 2      | Verificar o tratamento | O sistema deve detectar que o produto não existe. |
| 3      | Verificar a mensagem | Deve ser exibida uma mensagem apropriada, como "Produto não encontrado". |
| 4      | Verificar a interface | A página deve exibir uma interface adequada para o erro, sem quebrar o layout. |

#### **Resultados Esperados**

- O sistema deve detectar que o produto não existe.
- Uma mensagem apropriada deve ser exibida.
- A interface não deve quebrar ou exibir erros técnicos.

#### **Critérios de Aceitação**

- O tratamento de produto inexistente deve funcionar corretamente.
- A mensagem deve ser clara e informativa.
- A experiência do usuário deve ser preservada.

---

## Resumo dos Casos de Teste

### **Estatísticas**

- **Total de Casos de Teste:** 30
- **Casos de Teste Positivos:** 24
- **Casos de Teste Negativos:** 6

### **Cobertura por Módulo**

- **Tela Inicial:** 2 casos
- **Menu e Navegação:** 2 casos
- **Detalhes do Produto:** 3 casos
- **Carrinho de Compras:** 5 casos
- **Finalização de Pedido:** 3 casos
- **Pagamento:** 5 casos
- **Confirmação de Pedido:** 4 casos
- **Cancelamento:** 2 casos
- **Persistência e Recuperação:** 2 casos
- **Validações e Tratamento de Erros:** 2 casos

---

## Observações Finais

Este documento de casos de teste foi elaborado com foco em testes manuais funcionais do sistema McBugs. Os casos de teste cobrem os principais fluxos de trabalho do sistema, incluindo cenários positivos e negativos.

**Recomendações:**

1. Execute os casos de teste na ordem sugerida para garantir uma cobertura completa.
2. Documente os resultados de cada teste, incluindo evidências (screenshots) quando necessário.
3. Reporte qualquer desvio encontrado durante a execução dos testes.
4. Mantenha este documento atualizado conforme novas funcionalidades forem adicionadas ao sistema.

---

**Fim do Documento**

