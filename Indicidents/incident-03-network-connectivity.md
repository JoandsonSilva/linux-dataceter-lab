# Incident 03 — Network Connectivity Failure

## Objetivo

Simular e validar comunicação entre duas máquinas virtuais Linux utilizando rede local, ping e SSH.

---

# Cenário

Em ambientes de Data Center, falhas de conectividade podem causar indisponibilidade de serviços e impedir acesso remoto a servidores.

Esse laboratório simula testes básicos de conectividade entre cliente e servidor Linux.

---

# Identificação do IP do Servidor

```bash
ip a
```

## Objetivo

Identificar o endereço IP da VM servidor.

---

# Teste de Conectividade

## Ping do Cliente para o Servidor

```bash
ping IP_DO_SERVIDOR
```

## Objetivo

Validar comunicação entre as máquinas.

---

# Instalação do SSH

## No Servidor

```bash
sudo apt install openssh-server -y
```

---

# Verificação do Serviço SSH

```bash
sudo systemctl status ssh
```

## Objetivo

Garantir que o serviço SSH esteja ativo.

---

# Acesso Remoto

## Cliente acessando Servidor

```bash
ssh usuario@IP_DO_SERVIDOR
```

## Objetivo

Realizar acesso remoto seguro ao servidor Linux.

---

# Validação Operacional

Após conexão SSH foi possível:

- acessar remotamente o servidor
- executar comandos administrativos
- validar conectividade da rede
- simular acesso operacional de suporte

---

# Aprendizados

- Conceitos básicos de rede
- Comunicação entre VMs
- Diagnóstico de conectividade
- Uso de SSH
- Administração remota Linux

---

# Mentalidade de Data Center

A conectividade entre servidores é essencial para:

- monitoramento
- suporte remoto
- administração de infraestrutura
- continuidade operacional

O objetivo do laboratório foi validar comunicação e acesso remoto de forma controlada.
