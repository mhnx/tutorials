# SDKMAN ― Cheat sheet

## Instalação
Abra seu terminal e execute os comandos:

```bash
curl -s "https://get.sdkman.io" | bash
```

```
source "$HOME/.sdkman/bin/sdkman-init.sh"
```
Verifique se o SDKMAN foi instalado com sucesso com o comando:
```bash
sdk version
```

## Java
- Para instalar a versão estável mais recente do Java execute o comando:
```bash
sdk install java
```

- Para listar uma versão específica do Java execute o comando:
```bash
sdk list java
```
> Nessa lista é possível ver quais versões já estão instaladas.

- Para instalar uma versão específica do Java execute o comando:
```bash
sdk install java 17.0.11-zulu
```

- Para trocar de SDK temporariamente:
```bash
sdk use java 17.0.11-zulu
```

- Para fixar uma versão como a versão padrão:
```bash
sdk default java 17.0.11-zulu
```

- Para ver a versão atual:
```bash
sdk current java
```
> Se você omitir a palavra Java, ele vai listar todas as ferramentas instaladas.

## Troubleshooting
- Ajuda:
```bash
sdk help
```

- Flush:
```bash
sdk flush
```

- Ver o home do Java:
```bash
sdk home java 17.0.11-zulu
```
