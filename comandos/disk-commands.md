
# Disk Commands

## Verificar espaço em disco

```bash
df -h
```

## Criar arquivo grande

```bash
fallocate -l 1G arquivo_teste.img
```

## Verificar uso do disco

```bash
df -h
```

## Analisar diretórios

```bash
du -sh *
```

## Verificar logs

```bash
sudo du -h /var/log | sort -h
```

## Remover arquivo

```bash
rm arquivo_teste.img
```

## Validar recuperação

```bash
df -h
```
