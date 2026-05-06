
# Comandos Utilizados — Incidente de Alto Consumo de CPU

## Atualização dos Repositórios

```bash
sudo apt update
```

### Objetivo

Atualizar a lista de pacotes disponíveis no sistema Linux.

---

## Instalação das Ferramentas

```bash
sudo apt install stress htop sysstat -y
```

### Objetivo

Instalar ferramentas para:

- Simulação de carga na CPU
- Monitoramento de processos
- Análise de desempenho do sistema

---

# Ferramentas Instaladas

## stress

### Função

Gerar carga artificial na CPU para simular um incidente operacional.

---

## htop

### Função

Monitoramento visual de processos e uso de recursos do sistema.

---

## sysstat

### Função

Coleta de métricas e estatísticas de desempenho da CPU.

---

# Simulação do Incidente

## Geração de Alto Consumo de CPU

```bash
stress --cpu 2 --timeout 300
```

### Explicação

| Parâmetro | Função |
|---|---|
| `--cpu 2` | Cria 2 processos consumindo CPU |
| `--timeout 300` | Mantém a carga por 300 segundos |

---

# Monitoramento do Sistema

## Monitoramento em Tempo Real

```bash
top
```

### Objetivo

Visualizar:

- Uso de CPU
- Uso de memória
- Processos ativos
- Load average

---

## Monitoramento Visual Avançado

```bash
htop
```

### Objetivo

Monitorar processos de forma visual e organizada.

---

## Estatísticas da CPU

```bash
mpstat 1 5
```

### Explicação

| Parâmetro | Função |
|---|---|
| `1` | Intervalo de coleta em segundos |
| `5` | Quantidade de leituras |

---

# Identificação do Processo com Alto Consumo

```bash
ps aux --sort=-%cpu | head
```

### Objetivo

Listar os processos com maior consumo de CPU.

---

# Encerramento do Processo Problemático

```bash
sudo kill -9 PID
```

### Exemplo

```bash
sudo kill -9 1234
```

### Explicação

| Comando | Função |
|---|---|
| `kill` | Encerra um processo |
| `-9` | Força encerramento imediato |
| `PID` | Identificador do processo |

---

# Validação Pós-Correção

## Verificação Final

```bash
top
```

ou

```bash
htop
```

### Objetivo

Confirmar:

- Redução do uso de CPU
- Normalização do sistema
- Estabilidade operacional

---

# Resumo Operacional

## Fluxo Executado

1. Atualização dos repositórios
2. Instalação das ferramentas
3. Simulação de carga na CPU
4. Monitoramento do sistema
5. Identificação do processo problemático
6. Encerramento do processo
7. Validação da estabilidade

---

# Tecnologias Utilizadas

- Linux Ubuntu
- UTM
- stress
- htop
- sysstat
- top
- Bash
