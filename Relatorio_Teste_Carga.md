Relatório do teste de carga

Configuração:

Threads: 300  

Ramp-up: 10s  

Duration: 120s  

Loop: Infinite

Resultado principal:

Throughput total: 193.5 req/s  

P90 total: 1270 ms  

Error %: 0.04%

Evidencias:  

Verificar os prints na pasta /evidencias_teste

Conclusão:  

O teste de carga não atende completamente ao critério de aceitação.

Critério esperado:  

250 req/s  

P90 < 2000 ms  


Resultado obtido:  

193.5 req/s -> FAIL  

P90 = 1270 ms -> PASS  

Erros = 0.04% -> PASS  


Comparação com o requisito:  

Throughput abaixo do esperado (77% da meta)  

Tempo de resposta dentro do limite  

Erros desprezíveis  


O sistema consegue manter estabilidade e latência sob carga, mas não sustenta a vazão mínima exigida de 250 req/s.