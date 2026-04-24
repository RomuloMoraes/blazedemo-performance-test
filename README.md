# BlazeDemo Performance Test

## Instruções para execução

### Pré-requisitos

- Java JDK 8 ou superior
- Apache JMeter instalado

Download do JMeter:
https://jmeter.apache.org/download_jmeter.cgi

### Configuração do ambiente

1. Baixar e extrair o Apache JMeter
2. Garantir que o Java esteja instalado:

bash> java -version

### Execução do Teste
1. Abrir pasta onde esta o Jmeter
2. Se windows, executar jmeter.bat ou Caso Linux/Mac ./jmeter.sh  (Linux/Mac)
3. No menu do Jmeter navege por File > Open > jmeter_file_exmaple.jmx

OBS: No Test Plan há 2 Thread Groups, antes de executar os testes, atente-se para desabilitar o que não será alvo do teste
No menu do jmeter navege > 
1. Botão direito em cima do Thread Group que não será executado
2. Escolha a opção "Disable"

Para ativar novamente, repita os passos e escolha a opção Enable

## Objetivo

Avaliar o desempenho do sistema no cenário de compra de passagem aérea.

## Cenário

Fluxo completo:

1. Home
2. Search Flights
3. Choose Flight
4. Purchase Flight

# Teste de carga
## Configuração:
Threads: 300
Ramp-up: 10s
Duration: 120s
Loop: Infinite
## Resultado principal:
Throughput total: 193.5 req/s
P90 total: 1270 ms
Error %: 0.04%
O teste de carga não atende completamente ao critério de aceitação.
## Resultado esperado:
250 req/s
P90 < 2000 ms
## Resultado obtido:
193.5 req/s -> FAIL
P90 = 1270 ms -> PASS
Erros = 0.04% -> PASS

O sistema apresentou comportamento estável sob carga moderada, com tempo de resposta dentro do limite e taxa de erro praticamente nula.

# Teste de pico
## Configuração:
Threads: 600
Ramp-up: 2s
Duration: 60s
Loop: Infinite
## Resultado principal:
Throughput total: 163.4 req/s
P90 total: 4999 ms
Error %: 0.00%
O teste de pico não atende ao critério de aceitação.
## Resultado esperado:
250 req/s
P90 < 2000 ms
## Resultado obtido:
163.4 req/s -> FAIL
P90 = 4999 ms -> FAIL
Erros = 0% -> PASS

Mesmo com aumento brusco para 600 usuários em 2 segundos, o sistema não conseguiu aumentar a vazão. Pelo contrário, o throughput ficou menor que no teste de carga anterior.
