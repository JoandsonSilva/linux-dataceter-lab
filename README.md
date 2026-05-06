# Linux Data Center Lab — Incidente de Alto Consumo de CPU

## Objetivo

Simular um cenário real de alto consumo de CPU em um servidor Linux, monitorar o comportamento do sistema, identificar o processo responsável pelo problema e aplicar a correção.

Esse laboratório foi desenvolvido com foco em práticas de infraestrutura, troubleshooting e mentalidade operacional de Data Center.

---

# Ambiente Utilizado

| Item | Descrição |
|---|---|
| Host | macOS |
| Virtualização | UTM |
| VM Servidor | Linux Ubuntu |
| VM Cliente | Linux Ubuntu |
| Objetivo | Simulação de incidente operacional |

---

# Conceito do Incidente

Em ambientes de Data Center, um servidor pode apresentar lentidão devido ao alto uso de CPU.

Isso pode acontecer por diversos motivos:

- Processos travados
- Scripts em loop
- Aplicações consumindo recursos excessivos
- Falhas de sistema
- Sobrecarga operacional

Neste laboratório, o incidente foi simulado artificialmente para fins de aprendizado e prática de troubleshooting.

---

# Preparação do Ambiente

## Atualização dos repositórios

```bash
sudo apt update
```

### Explicação

- `sudo` → executa o comando com privilégios administrativos
- `apt` → gerenciador de pacotes do Ubuntu/Debian
- `update` → atualiza a lista de pacotes disponíveis nos repositórios

Esse passo garante que o sistema tenha acesso às versões mais recentes dos programas.

---

# Instalação das Ferramentas

```bash
sudo apt install stress htop sysstat -y
```

## Explicação das Ferramentas

### stress

Ferramenta utilizada para gerar carga artificial no sistema.

Foi utilizada para simular alto consumo de CPU.

---

### htop

Ferramenta visual de monitoramento de processos.

Permite visualizar:

- Uso de CPU
- Uso de memória
- Processos ativos
- Consumo por núcleo

---

### sysstat

Pacote de ferramentas de análise de desempenho.

Neste projeto foi utilizado o comando:

```bash
mpstat
```

Para monitoramento detalhado da CPU.

---

### -y

Confirma automaticamente a instalação dos pacotes.

---

# Simulação do Problema

## Geração de carga na CPU

```bash
stress --cpu 2 --timeout 300
```

## Explicação

### --cpu 2

Cria 2 processos consumindo CPU.

---

### --timeout 300

Mantém a carga ativa por 300 segundos (5 minutos).

---

## Resultado esperado

A CPU do servidor apresenta alto consumo, simulando um cenário de lentidão operacional.

---

# Monitoramento do Sistema

## Monitoramento em tempo real

```bash
top
```

Ferramenta padrão do Linux para visualização de:

- Processos
- CPU
- Memória
- Load Average

---

## Monitoramento visual avançado

```bash
htop
```

Versão mais amigável e visual do `top`.

---

## Estatísticas da CPU

```bash
mpstat 1 5
```

## Explicação

- `1` → coleta dados a cada 1 segundo
- `5` → executa 5 leituras

Objetivo:

Analisar o comportamento da CPU durante o incidente.

---

# Identificação do Processo Problemático

```bash
ps aux --sort=-%cpu | head
```

## Explicação

### ps aux

Lista todos os processos ativos do sistema.

---

### --sort=-%cpu

Ordena os processos do maior para o menor consumo de CPU.

---

### head

Mostra apenas os primeiros resultados.

---

## Objetivo

Identificar rapidamente qual processo está causando o alto consumo de CPU.

---

# Correção do Problema

## Encerramento do processo

```bash
sudo kill -9 PID
```

Exemplo:

```bash
sudo kill -9 1234
```

## Explicação

### kill

Comando utilizado para encerrar processos.

---

### -9

Força o encerramento imediato do processo.

---

### PID

Identificador único do processo.

---

# Validação Pós-Correção

Após encerrar o processo:

```bash
top
```

ou

```bash
htop
```

Foi possível validar:

- Redução do uso de CPU
- Normalização do sistema
- Recuperação da estabilidade operacional

---

# Aprendizados

Durante esse laboratório foi possível aprender:

- Simulação de incidentes Linux
- Monitoramento de CPU
- Diagnóstico de processos
- Uso de ferramentas de troubleshooting
- Identificação de causa raiz
- Correção de incidentes
- Validação de estabilidade do sistema

---

# Mentalidade de Data Center

O foco do projeto não foi apenas executar comandos, mas seguir uma lógica operacional:

1. Identificar o sintoma
2. Monitorar métricas
3. Investigar a causa
4. Corrigir com segurança
5. Validar estabilidade
6. Documentar o incidente

Essa abordagem é essencial em ambientes de infraestrutura, suporte e Data Center.

---

# Tecnologias e Ferramentas

- Linux Ubuntu
- UTM
- stress
- htop
- sysstat
- top
- SSH

---

# Próximos Passos

- Simulação de disco cheio
- Monitoramento de rede
- Logs do sistema
- Automação com Bash
- Integração com Jira
- Monitoramento com Grafana/Zabbix

---

# Autor

Joandson Oliveira

Projeto desenvolvido com foco em aprendizado prático de Linux, troubleshooting e operações de Data Center.
