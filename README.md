## Objetivo

Este projeto foi desenvolvido para automatizar o tratamento de arquivos ZPL durante uma instabilidade temporária na geração de arquivos de impressão de uma plataforma de e-commerce ocorrida em junho de 2026.

Na operação em que o script foi utilizado, a regra de negócio era utilizar impressoras Zebra exclusivamente para a impressão das etiquetas de envio dos pedidos. As notas fiscais (DANFE) eram impressas separadamente em papel sulfite, não sendo utilizadas em etiquetas adesivas.

Durante o período da instabilidade, os arquivos de impressão passaram a incluir, no mesmo arquivo ZPL:

- Etiquetas de envio;
- Etiquetas contendo o DANFE Simplificado.

As configurações da plataforma estavam corretas e o comportamento foi identificado como uma falha temporária do próprio sistema.

Como consequência, a impressão automática gerava etiquetas de DANFE que não eram utilizadas, ocasionando desperdício de etiquetas adesivas, aumento de custos e perda de produtividade devido à necessidade de remoção manual dessas páginas.

Para eliminar esse retrabalho, foi desenvolvido este script, que identifica e remove automaticamente os blocos referentes ao **DANFE SIMPLIFICADO**, preservando apenas as etiquetas de envio.
