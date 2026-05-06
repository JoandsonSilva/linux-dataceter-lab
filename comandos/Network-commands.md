# Network Commands

## Identificar IP do servidor

```bash
ip a
```

## Alternativa para ver IP de forma resumida

```bash
hostname -I
```

## Testar conectividade do cliente para o servidor

```bash
ping IP_DO_SERVIDOR
```

## Instalar servidor SSH

```bash
sudo apt install openssh-server -y
```

## Verificar status do SSH

```bash
sudo systemctl status ssh
```

## Iniciar serviço SSH

```bash
sudo systemctl start ssh
```

## Habilitar SSH na inicialização

```bash
sudo systemctl enable ssh
```

## Acessar servidor via SSH pelo cliente

```bash
ssh usuario@IP_DO_SERVIDOR
```

## Verificar portas abertas no servidor

```bash
ss -tuln
```

## Testar porta SSH

```bash
ss -tuln | grep :22
```

## Verificar rota de rede

```bash
ip route
```

## Verificar configuração DNS

```bash
cat /etc/resolv.conf
```

## Sair da conexão SSH

```bash
exit
```

# Fluxo recomendado

1. Identificar IP do servidor
2. Testar ping entre cliente e servidor
3. Instalar SSH no servidor
4. Verificar se o serviço SSH está ativo
5. Acessar servidor remotamente pelo cliente
6. Validar porta 22
7. Documentar evidências
