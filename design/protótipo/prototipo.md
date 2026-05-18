# Protótipo Triiib-o E-commerce — Heurísticas de Nielsen

Documentação do protótipo interativo do e-commerce **Triiib-o**, com inventário de telas, referência ao design no Figma e mapeamento das **10 heurísticas de usabilidade de Jakob Nielsen** aplicadas à interface.

---

## Protótipo no Figma

| Recurso | Link |
|--------|------|
| **Protótipo interativo** | [Triiib-o — Design (Figma)](https://www.figma.com/proto/VyLzHtJWcumPCNogXmenlr/Triiibo---Design?node-id=91-1362&t=EwdgYsDnooITxNk3-1) |

Use o link acima para navegar entre fluxos, estados e interações que não estão representados estaticamente neste documento.

---

## Inventário de telas

| # | Tela | Arquivo | Descrição |
|---|------|---------|-----------|
| 1 | Dashboard | `E-COMMERCE_ Dashboard.jpg` | Área administrativa com menu lateral, resumo financeiro e navegação principal |
| 2 | Catálogo | `E-COMMERCE_ Catálogo.jpg` | Listagem de produtos com filtros laterais, ordenação e grid |
| 3 | Adicionar ao carrinho | `E-COMMERCE_ Add to Cart.png` | Modal de quick view / adicionar produto com seletor de quantidade |
| 4 | Visualizar pedido | `E-COMMERCE_ Visualizar Pedido.jpg` | Detalhes do pedido, barra de progresso e resumo dos itens |
| 5 | Página não encontrada | `E-COMMERCE_ Not Found.jpg` | Erro 404 com mensagem amigável e retorno ao início |

---

## Telas do protótipo

### 1. Dashboard

![Dashboard do e-commerce Triiibo](./E-COMMERCE_%20Dashboard.jpg)

Área administrativa do cliente com menu lateral, indicadores financeiros e identidade visual da marca (vermelho e tons terrosos).

---

### 2. Catálogo

![Catálogo de produtos](./E-COMMERCE_%20Catálogo.jpg)

Página principal de compra: busca, filtros na barra lateral, grid de produtos e cards com informações essenciais.

---

### 3. Adicionar produto ao carrinho (Quick View)

![Modal adicionar ao carrinho](./E-COMMERCE_%20Add%20to%20Cart.png)

Modal para visualização rápida do produto, ajuste de quantidade e inclusão na sacola sem sair do catálogo.

---

### 4. Visualizar pedido

![Detalhes e acompanhamento do pedido](./E-COMMERCE_%20Visualizar%20Pedido.jpg)

Tela de acompanhamento com barra de progresso linear, resumo visual dos itens e dados de entrega e pagamento.

---

### 5. Página não encontrada (404)

![Página 404](./E-COMMERCE_%20Not%20Found.jpg)

Estado de erro para URLs inexistentes ou links quebrados, com orientação clara e ação de recuperação.

---

## Mapeamento: heurísticas de Nielsen × interface

A tabela abaixo resume **onde** cada heurística aparece no protótipo. As seções seguintes detalham o comportamento e o raciocínio de design.

| Heurística | Telas / componentes principais |
|------------|--------------------------------|
| 1. Visibilidade do status | Visualizar Pedido, Header (badge), Dashboard / menu |
| 2. Compatibilidade com o mundo real | Header, Catálogo, Dashboard |
| 3. Controle e liberdade | Modal Add to Cart, Visualizar Pedido |
| 4. Consistência e padrões | Catálogo, todas as telas (identidade visual) |
| 5. Prevenção de erros | Catálogo (estoque, slider de preço) |
| 6. Reconhecimento vs. memorização | Visualizar Pedido, Catálogo (filtros) |
| 7. Flexibilidade e eficiência | Modal Quick View, Catálogo (ordenação/filtros) |
| 8. Design estético e minimalista | Visualizar Pedido, Catálogo (cards) |
| 9. Recuperação de erros | 404, feedback por cor (status do pedido) |
| 10. Ajuda e documentação | Header (FAQ), modal de produto (especificações) |

---

### 1. Visibilidade do status do sistema

O sistema mantém o usuário informado sobre **onde está** e **o que está acontecendo**, sem depender de memória ou de atualização manual da página.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Acompanhamento de pedido** | Visualizar Pedido | Barra de progresso linear indica a etapa atual (Pedido Recebido, Processando, etc.). |
| **Feedback de carrinho** | Header (todas as páginas) | Ícone da sacola com badge numérico vermelho mostra em tempo real quantos itens foram selecionados. |
| **Página ativa** | Dashboard (menu lateral) e Header | Item correspondente à tela atual recebe destaque visual, indicando a localização no sistema. |

**Telas relacionadas:** Visualizar Pedido, Dashboard, Catálogo (Header compartilhado).

---

### 2. Compatibilidade entre sistema e mundo real

A interface fala a linguagem do usuário, com conceitos, símbolos e formatos familiares do cotidiano e de outros e-commerces.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Metáforas universais** | Header | Ícones de lupa (busca), telefone (suporte) e sacola (compras) reutilizam convenções já internalizadas. |
| **Linguagem financeira** | Catálogo e Dashboard | Valores em padrão monetário local (R$), com termos claros: Subtotal, Frete, Desconto. |

**Telas relacionadas:** Catálogo, Dashboard.

---

### 3. Controle e liberdade do usuário

O usuário pode desfazer ações, sair de fluxos e corrigir escolhas sem se sentir “preso” ao processo.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Saída de emergência** | Modal Adicionar ao Carrinho | Botão “X” no canto superior direito e clique na área externa permitem cancelar sem concluir a compra. |
| **Ajuste de quantidade** | Mesmo modal | Seletores “+” e “−” permitem corrigir a quantidade antes de adicionar à sacola. |
| **Navegação de retorno** | Visualizar Pedido | Ícone de seta “<” ao lado de “Detalhes do Pedido” facilita voltar à tela anterior. |

**Telas relacionadas:** Add to Cart, Visualizar Pedido.

---

### 4. Consistência e padrões

Padrões visuais e estruturais repetidos reduzem a curva de aprendizado e reforçam a confiança na marca.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Layout de e-commerce** | Catálogo | Logo à esquerda, busca centralizada, filtros na lateral e grid de produtos à direita — padrão industrial de varejo online. |
| **Identidade visual** | Todas as telas | Paleta triiib-o (vermelho e tons terrosos) em botões de ação, seleções e elementos de destaque. |

**Telas relacionadas:** Catálogo, Dashboard, demais fluxos.

---

### 5. Prevenção de erros

O design antecipa falhas comuns e as evita antes que o usuário chegue ao checkout ou à frustração.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Estado de estoque** | Catálogo | Tag “Esgotado” sobre a imagem impede tentativa de compra de item indisponível. |
| **Filtros restritivos** | Catálogo | Slider de preço limita a busca ao intervalo real de produtos, evitando valores inválidos digitados manualmente. |

**Telas relacionadas:** Catálogo.

---

### 6. Reconhecimento em vez de memorização

Informações relevantes permanecem visíveis; o usuário não precisa guardar códigos, filtros ou nomes técnicos na memória.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Resumo visual do pedido** | Visualizar Pedido | Miniatura e nome do produto permitem identificar visualmente o que foi comprado. |
| **Filtros ativos** | Catálogo (barra lateral) | Categorias selecionadas permanecem marcadas, lembrando quais critérios geraram o resultado atual. |

**Telas relacionadas:** Visualizar Pedido, Catálogo.

---

### 7. Flexibilidade e eficiência de uso

Atalhos e controles avançados atendem usuários experientes sem prejudicar quem prefere um fluxo simples.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Aceleradores de compra** | Modal Quick View (Add to Cart) | Adição ao carrinho sem carregar a página completa do produto. |
| **Filtros avançados** | Catálogo | Ordenação (“Último”, “Preço”) e filtros de categoria aceleram a descoberta para quem já conhece o catálogo. |

**Telas relacionadas:** Add to Cart, Catálogo.

---

### 8. Design estético e minimalista

A interface prioriza o essencial, com hierarquia clara e ausência de ruído visual desnecessário.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Hierarquia de informação** | Visualizar Pedido | Endereço, pagamento e produtos separados por whitespace e divisórias sutis. |
| **Foco no produto** | Catálogo (cards) | Apenas foto, nome, preço e avaliação — informação suficiente para a decisão de compra. |

**Telas relacionadas:** Visualizar Pedido, Catálogo.

---

### 9. Recuperação de erros

Quando algo falha, o sistema explica o problema e oferece caminhos claros para continuar.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Página 404 personalizada** | Not Found | Mensagem amigável e botão “Voltar ao Início” para sair do estado de erro. |
| **Feedback visual** | Fluxo de pedido | Verde para sucesso no processamento; vermelho para alertas — leitura rápida do resultado da operação. |

**Telas relacionadas:** Not Found, Visualizar Pedido.

---

### 10. Ajuda e documentação

Suporte contextual e documentação acessível reduzem dependência de atendimento humano para dúvidas recorrentes.

| Evidência | Onde | Comportamento |
|-----------|------|----------------|
| **Central de ajuda** | Header | Link para FAQ sobre entregas, trocas e pagamentos, encontrável em qualquer página. |
| **Descrições de produto** | Modal (ex.: caneca) | Especificações técnicas (material cerâmico, resistência, capacidade 325 ml) como documentação de apoio à decisão de compra. |

**Telas relacionadas:** Header (todas), Add to Cart / modal de produto.

---

## Referências

- Nielsen, J. (1994). *10 Usability Heuristics for User Interface Design.* Nielsen Norman Group.
- Protótipo Figma: [Triiib-o — Design](https://www.figma.com/proto/VyLzHtJWcumPCNogXmenlr/Triiibo---Design?node-id=91-1362&t=EwdgYsDnooITxNk3-1)

