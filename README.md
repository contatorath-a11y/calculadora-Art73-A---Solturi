# Calculadora Art. 73-A · REN ANEEL nº 1.000/2021

Calcula a potência de microgeração solar fotovoltaica compatível com o consumo da unidade consumidora, conforme o **art. 73-A, inciso II e § 1º, da Resolução Normativa ANEEL nº 1.000/2021** (incluído pela REN ANEEL nº 1.098/2024). Até essa potência, a análise de inversão de fluxo de potência fica afastada, desde que a unidade atenda aos critérios de gratuidade.

A calculadora também gera um **memorial de cálculo em PDF** para apresentar a qualquer distribuidora, com o embasamento normativo e cada passo do cálculo.

**Acesse:** https://contatorath-a11y.github.io/calculadora-Art73-A---Solturi/

## Como usar

1. Informe o consumo da unidade de uma das três formas:
   - **Média mensal** dos 12 últimos ciclos;
   - **Total** dos 12 últimos ciclos (a calculadora divide por 12);
   - **Mês a mês**, digitando o consumo de cada fatura. Esse histórico entra no relatório.
2. Escolha a classe da unidade: residencial, comercial, industrial, rural ou serviço público.
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

## Conteúdo do relatório em PDF

1. Identificação da unidade consumidora e do projeto
2. Objetivo
3. Embasamento normativo: transcrição do art. 73-A, itens aplicáveis do Manual de Instruções e tabela de fatores de ajuste
4. Dados de entrada, com a origem de cada parâmetro e o histórico mensal, quando informado
5. Memória de cálculo em cinco passos
6. Verificação das condições de enquadramento
7. Conclusão, que muda conforme o projeto caiba ou não no limite
8. Referências e bloco de assinatura do responsável técnico

O PDF é gerado no próprio navegador. Nenhum dado digitado é enviado a servidores. Os dados do responsável técnico ficam salvos apenas no navegador de quem usa.

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
index.html        a calculadora completa (HTML, CSS e JavaScript em um só arquivo)
assets/logo.jpg   cópia do logotipo (a página já traz o logo embutido)
```

A página usa o [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 (via cdnjs) para montar o PDF e as fontes Barlow Semi Condensed e IBM Plex do Google Fonts.

## Usar sem internet ou em outro servidor

Basta abrir o `index.html` no navegador. Para gerar o PDF é preciso conexão na primeira carga, por causa do jsPDF e das fontes.

## Aviso

Ferramenta de apoio ao projeto. O valor que vale para a conexão é o informado pela distribuidora no orçamento de conexão, que deve liberar o maior valor entre esta regra e a máxima potência injetável apurada no estudo de inversão de fluxo (item 8.14 do Manual).
