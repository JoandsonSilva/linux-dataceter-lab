# Incident 02 — Disk Full

## Objetivo

Simular um incidente de disco cheio em um servidor Linux, monitorar o uso do armazenamento, identificar arquivos responsáveis pelo consumo excessivo e restaurar a estabilidade do sistema.

---

# Cenário

Em ambientes de infraestrutura e Data Center, servidores podem apresentar indisponibilidade ou lentidão devido ao consumo excessivo de armazenamento.

Esse laboratório simula um incidente operacional de disco cheio.

---

# Verificação Inicial do Disco

```bash
df -h
```

## Objetivo

Verificar:

- espaço total
- espaço utilizado
- espaço disponível
- percentual de uso do disco

---

# Simulação do Problema

## Criação de Arquivo Grande

```bash
fallocate -l 1G arquivo_teste.img
```

## Objetivo

Simular consumo excessivo de armazenamento no servidor.

---

# Validação do Consumo

```bash
df -h
```

## Resultado Esperado

Aumento no percentual de uso do disco.

---

# Investigação do Problema

## Verificação de Diretórios

```bash
du -sh *
```

## Objetivo

Identificar diretórios e arquivos com maior consumo de espaço.

---

# Análise de Logs

```bash
sudo du -h /var/log | sort -h
```

## Objetivo

Analisar crescimento de logs do sistema.

---

# Correção do Problema

## Remoção do Arquivo

```bash
rm arquivo_teste.img
```

---

# Validação Pós-Correção

```bash
df -h
```

## Objetivo

Confirmar recuperação do espaço em disco e estabilidade operacional.

---

# Aprendizados

- Monitoramento de armazenamento
- Troubleshooting Linux
- Investigação de uso de disco
- Gerenciamento de arquivos
- Correção de incidentes operacionais

---

# Mentalidade de Data Center

O foco do laboratório foi:

1. Detectar o problema
2. Monitorar impacto
3. Investigar causa
4. Corrigir com segurança
5. Validar estabilidade
6. Documentar o incidente
