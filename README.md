# ZPL Label Cleaner

Script em Python desenvolvido para processar arquivos ZPL exportados em formato ZIP, removendo automaticamente os blocos referentes ao DANFE Simplificado e mantendo apenas as etiquetas de envio.

## Objetivo

Este projeto foi desenvolvido para automatizar o tratamento de arquivos ZPL durante uma instabilidade temporária na geração de arquivos de impressão de uma plataforma de e-commerce ocorrida em junho de 2026.

Na operação em que o script foi utilizado, a regra de negócio era utilizar impressoras Zebra exclusivamente para a impressão das etiquetas de envio dos pedidos. As notas fiscais (DANFE) eram impressas separadamente em papel sulfite, não sendo utilizadas em etiquetas adesivas.

Durante o período da instabilidade, os arquivos de impressão passaram a incluir, no mesmo arquivo ZPL:

- Etiquetas de envio;
- Etiquetas contendo o DANFE Simplificado.

As configurações da plataforma estavam corretas e o comportamento foi identificado como uma falha temporária do próprio sistema.

Como consequência, a impressão automática gerava etiquetas de DANFE que não eram utilizadas, ocasionando desperdício de etiquetas adesivas, aumento de custos e perda de produtividade devido à necessidade de remoção manual dessas páginas.

Para eliminar esse retrabalho, foi desenvolvido este script, que identifica e remove automaticamente os blocos referentes ao **DANFE SIMPLIFICADO**, preservando apenas as etiquetas de envio.

## Como funciona

1. Faz upload do arquivo ZIP.
2. Extrai o conteúdo.
3. Localiza o arquivo TXT.
4. Identifica todos os blocos ZPL (`^XA ... ^XZ`).
5. Remove os blocos contendo **DANFE SIMPLIFICADO**.
6. Gera um novo arquivo contendo apenas as etiquetas.
7. Faz o download automaticamente do novo arquivo.

## Tecnologias

- Python
- Google Colab

## Fluxo do processamento

```text
Arquivo ZIP (gerado na tela de vendas do Mercado Livre)
      │
      ▼
Extrai o arquivo TXT
      │
      ▼
Localiza todos os blocos ZPL
      │
      ▼
Remove os blocos com "DANFE SIMPLIFICADO"
      │
      ▼
Gera um novo arquivo TXT
      │
      ▼
Download automático
```

## Como executar

1. Abra o notebook no Google Colab.
2. Execute a célula.
3. Faça upload do arquivo ZIP contendo o arquivo TXT exportado.
4. Aguarde o processamento.
5. O script irá gerar automaticamente um novo arquivo TXT contendo apenas as etiquetas de envio.
6. O download do arquivo será iniciado automaticamente.

## Observação

Este projeto foi desenvolvido a partir de uma necessidade operacional real para automatizar o tratamento de arquivos ZPL durante uma instabilidade temporária em uma plataforma de e-commerce.

O repositório apresenta apenas a solução desenvolvida em Python. Nenhum arquivo utilizado na operação, dado de cliente ou informação interna faz parte deste projeto.
