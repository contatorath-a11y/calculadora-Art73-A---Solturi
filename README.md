# Calculadora Art. 73-A · REN ANEEL nº 1.000/2021

Calcula a potência de microgeração solar fotovoltaica compatível com o consumo da unidade consumidora, conforme o **art. 73-A, inciso II e § 1º, da Resolução Normativa ANEEL nº 1.000/2021** (incluído pela REN ANEEL nº 1.098/2024). Até essa potência, a análise de inversão de fluxo de potência fica afastada, desde que a unidade atenda aos critérios de gratuidade.

Na versão 3.0, basta **enviar a fatura de energia** (PDF ou foto): a calculadora lê os 12 meses de consumo, tira a média e identifica a classe da unidade. Depois gera um **memorial de cálculo em PDF** para apresentar a qualquer distribuidora, com o embasamento normativo e cada passo do cálculo.

**Acesse:** https://contatorath-a11y.github.io/calculadora-Art73-A---Solturi/

## Como usar

1. Arraste a fatura de energia para o campo **Ler fatura de energia** (ou clique nele e escolha o arquivo). A calculadora preenche o mês a mês, a classe e os dados da unidade que encontrar. Confira os valores com a fatura.

   Se preferir, informe o consumo à mão, de uma das três formas:
   - **Média mensal** dos 12 últimos ciclos;
   - **Total** dos 12 últimos ciclos (a calculadora divide por 12);
   - **Mês a mês**, digitando o consumo de cada fatura. Esse histórico entra no relatório.
2. Confira a classe da unidade: residencial, comercial, industrial, rural ou serviço público.
3. Opcional: informe a potência do projeto para comparar com o limite calculado.
4. Preencha os dados do relatório (titular, nº da UC, distribuidora, responsável técnico) e clique em **Gerar relatório PDF**.

## Fórmula

```
Pg = C ÷ (FC × 24 h × 30 dias) × FA
```

| Símbolo | Significado | Valor |
|---|---|---|
| Pg | Potência a ser instalada da microgeração | resultado, em kW |
| C | Consumo médio mensal dos 12 últimos ciclos de faturamento | kWh/mês (item 8.15 do Manual) |
| FC | Fator de capacidade da fonte solar | 16% (item 8.12; art. 655-B) |
| FA | Fator de ajuste regulatório da classe | Anexo II do Manual |

O resultado é **arredondado para cima** até o número inteiro seguinte (item 8.13).

### Fatores de ajuste regulatórios (Anexo II do Manual)

| Classe | FA |
|---|---|
| Residencial | 46% |
| Comércio, serviços e outras atividades | 63% |
| Industrial | 69% |
| Rural | 53% |
| Serviço público | 57% |

A classe poder público usa o fator de comércio, serviços e outras atividades (item 8.18).

### Exemplos do próprio Manual da ANEEL

| Classe | Consumo médio | Cálculo | Pg |
|---|---|---|---|
| Residencial | 706 kWh | 706 ÷ 115,2 × 0,46 = 2,82 kW | 3 kW |
| Comercial | 4.360 kWh | 4.360 ÷ 115,2 × 0,63 = 23,84 kW | 24 kW |

## Leitura da fatura

| Arquivo | Como é lido | Resultado esperado |
|---|---|---|
| PDF baixado do site da distribuidora | Texto do próprio PDF, no navegador | Rápido e preciso |
| PDF escaneado ou foto (JPG, PNG) | Reconhecimento de texto (OCR) no navegador | Bom com imagem nítida, de frente e bem iluminada; meses não lidos ficam marcados para preencher |

O que é procurado na fatura:

- **Histórico de consumo:** tabelas em linhas (ex.: Cemig), gráficos com o valor sobre a barra (ex.: Celesc, Enel), colunas separadas (ex.: Copel) e linhas de valores com os meses embaixo (ex.: Equatorial). Quando o histórico não traz o mês da própria fatura, o consumo faturado no mês é acrescentado.
- **Classe:** pelo campo "Classe" ou "Classificação", ou pelo subgrupo (B1 residencial, B2 rural, B3 + atividade).
- **Distribuidora e nº da unidade consumidora**, quando aparecem na fatura.

A leitura avisa quando falta algum mês, quando um valor parece fora do padrão, quando a fatura tem postos horários (ponta e fora de ponta) ou quando a unidade já tem geração própria.

Quando os dados vêm da fatura, o relatório registra isso: a classe aparece com o texto da fatura como origem, e a tabela do histórico informa que os valores foram transcritos da fatura e conferidos pelo responsável técnico.

## Conteúdo do relatório em PDF

1. Identificação da unidade consumidora e do projeto
2. Objetivo
3. Embasamento normativo: transcrição do art. 73-A, itens aplicáveis do Manual de Instruções e tabela de fatores de ajuste
4. Dados de entrada, com a origem de cada parâmetro e o histórico mensal, quando informado
5. Memória de cálculo em cinco passos
6. Verificação das condições de enquadramento
7. Conclusão, que muda conforme o projeto caiba ou não no limite
8. Referências e bloco de assinatura do responsável técnico

O PDF é gerado no próprio navegador. A fatura e os dados digitados não são enviados a servidores. Os dados do responsável técnico ficam salvos apenas no navegador de quem usa.

## Quando o cálculo se aplica

- Microgeração distribuída de fonte solar fotovoltaica, com até 75 kW;
- Enquadramento nos critérios de gratuidade (§ 3º do art. 104, § 2º do art. 105 e parágrafo único do art. 106). Na prática, a potência da geração não pode superar a potência disponibilizada da unidade, ou a obra da carga deve ser suficiente para a geração (item 3.3 do Manual);
- Unidade com pelo menos 12 ciclos de faturamento (item 8.17);
- Não vale para as classes iluminação pública e consumo próprio.

## Base normativa

- [Resolução Normativa ANEEL nº 1.000/2021](https://www2.aneel.gov.br/cedoc/ren20211000.html), art. 73-A
- [Resolução Normativa ANEEL nº 1.098/2024](https://www2.aneel.gov.br/cedoc/ren20241098.html), que incluiu o art. 73-A
- [Manual de Instruções do art. 73, § 1º](https://www2.aneel.gov.br/cedoc/adsp20242216_2.pdf), aprovado pelo Despacho ANEEL nº 2.216/2024

## Estrutura do repositório

```
index.html        a calculadora 3.0 completa (HTML, CSS e JavaScript em um só arquivo)
v2/index.html     a versão 2.0, sem leitura de fatura
assets/logo.jpg   cópia do logotipo (a página já traz o logo embutido)
```

Bibliotecas usadas, carregadas de CDN só quando necessárias:

- [jsPDF](https://github.com/parallax/jsPDF) 2.5.1, para montar o relatório;
- [PDF.js](https://mozilla.github.io/pdf.js/) 3.11.174, para ler o texto e as páginas da fatura em PDF;
- [Tesseract.js](https://tesseract.projectnaptha.com/) 5.1.1, para o reconhecimento de texto em fotos (baixa cerca de 4 MB na primeira leitura de imagem).

As fontes Barlow Semi Condensed e IBM Plex vêm do Google Fonts.

## Versão anterior

A versão 2.0 continua disponível em https://contatorath-a11y.github.io/calculadora-Art73-A---Solturi/v2/

## Usar em outro servidor

Basta publicar ou abrir o `index.html`. É preciso conexão com a internet para baixar as bibliotecas na primeira vez.

## Aviso

Ferramenta de apoio ao projeto. O valor que vale para a conexão é o informado pela distribuidora no orçamento de conexão, que deve liberar o maior valor entre esta regra e a máxima potência injetável apurada no estudo de inversão de fluxo (item 8.14 do Manual).
