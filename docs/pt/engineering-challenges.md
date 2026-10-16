# Desafios de engenharia

[🇧🇷 Português](engineering-challenges.md) | [🇺🇸 English](../en/engineering-challenges.md)

O SeuLeilão vai além de um CRUD: precisa lidar com entradas não confiáveis, documentos, processos assíncronos, regras em evolução e decisões humanas.

## Fontes heterogêneas
Informações podem chegar em fontes e formatos diferentes. **Desafio:** normalizar sem perder a origem, usando adaptações específicas quando necessário.

## Informações que mudam
Dados relacionados a leilões podem mudar ao longo do tempo. **Desafio:** preservar histórico e permitir auditoria.

## Documentos e extração
Informações relevantes podem existir apenas em documentos, cuja obtenção ou processamento pode falhar. **Desafio:** processamento assíncrono, tratamento de falhas e rastreabilidade.

## Dados incompletos ou conflitantes
Fontes podem divergir ou deixar campos sem resposta. **Desafio:** estados explícitos de pendência e revisão, sem escolhas silenciosas.

## Processamento demorado
Coleta, extração e enriquecimento podem levar mais tempo do que uma requisição HTTP. **Desafio:** workers Celery, retentativas e idempotência.

## Revisão humana
Nem toda decisão pode ser automatizada com segurança. **Desafio:** filas de revisão, registro de decisões e trilhas de auditoria.

## Evolução do produto
A compreensão do domínio amadurece com a implementação. **Desafio:** modularidade, registros de decisão (ADRs), entregas verticais e validação iterativa.

## Testes
Testes automatizados protegem regras determinísticas e fluxos importantes. Além de evitar regressões, ajudam a tornar verificáveis as hipóteses de produto e engenharia.
