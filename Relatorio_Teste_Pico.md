Relatório do teste de pico

Configuração:

Threads: 600  

Ramp-up: 2s  

Duration: 60s  

Loop: Infinite


Resultado principal:

Throughput total: 163.4 req/s  

P90 total: 4999 ms  

Error %: 0.00%  


Conclusão:  

O teste de pico não atende ao critério de aceitação.

Evidencias:  

Verificar os prints na pasta /evidencias_teste

Critério esperado:  

250 req/s  

P90 < 2000 ms  

Resultado obtido:  

163.4 req/s -> FAIL  

P90 = 4999 ms -> FAIL  

Erros = 0% -> PASS  


Comparação:  

Teste de carga: 193.5 req/s | P90: 1270 ms  

Teste de pico: 163.4 req/s | P90: 4999 ms  


O sistema começa a degradar sob pico: o sistema continuou respondendo sem erros, mas com aumento da latência e não atingindo a vazão mínima.