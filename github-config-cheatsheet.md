# Nova forma de autenticação do Github
## *Vamos usar chaves SSH para garantir uma maior segurança ao dar push nos projetos.*

> As chaves criadas podem ser vistas e gerenciadas no link:
https://github.com/settings/keys

Para criar uma chave vamos para o terminal (Git Bash) e vamos realizar os seguintes comandos:
```
ssh-keygen -t ed25519 -C seu-email@dominio.com
```
> Lembre de substituir pelo seu e-mail!

> ed25519 é um tipo de criptografia

Com esse comando serão geradas duas chaves, uma privada e outra pública. Por padrão elas serão salvas numa pasta oculta localizada em:
```/C/Users/Mahonri/.ssh/id_ed25519``` e 
```/C/Users/Mahonri/.ssh/id_ed25519.pub``` (A chave pública)

O terminal vai perguntar se você quer mudar o local onde essas chaves serão salvas. Não precisa mexer em nada. Basta teclar Enter. Assim as chaves serão criadas na pasta padrão mostrada acima.

Em seguida uma senha será pedida. Você também pode deixar em branco apenas teclando ```Enter``` (sem senha).

Uma chave será impressa no terminal com a SHA-256 seguida do e-mail e de uma espécie de QR code como no exemplo a seguir:
```
The key fingerprint is:
SHA256:1LaPeFcHb+f3E20qIcOAvag68Nw2Jdv050uXAD4pBI4 seu-email@dominio.com
The key's randomart image is:
+--[ED25519 256]--+
|  .      .       |
| o .    ...      |
|E . .   ooo.  .  |
|     . o.+o.   o |
|      ..V o+  . *|
|  .   o..o.++o =+|
|   + o =. +.=. o+|
|    = =..o.o. ..o|
|     o oooo. .  o|
+----[SHA256]-----+
```
Isso confirma que as chaves foram geradas. Para acessar a chave vamos entrar na pasta oculta.
```
cd .ssh
```

E para mostrar o conteúdo da pasta vamos digitar:
```
cat id_ed25519.pub
```

Exemplo de resposta:
```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAINLHJLDvZOdHuTllblng4DFt22ylqvK5uOicP82t4kZa seu-email@dominio.com
```

Essa é a nossa chave pública e vamos adicionar ela em nossas chaves SSH no Github através do link: https://github.com/settings/keys

Depois de adicionar a chave no Github, vamos voltar ao terminal e fazer mais uma configuração. **Ainda dentro da pasta oculta ssh**, digite:
```
eval $(ssh-agent -s)
```

O terminal vai retornar algo mais ou menos assim:
```
Agent pid 587
```

Em seguida vamos digitar, ainda dentro da pasta ssh:
```
ssh-add id_ed25519
```

Vamos adicionar nossa chave privada...
A senha que foi criada mais acima será pedida, caso você não tenha deixado em branco.

Depois disso, podemos adicionar repositórios privados.
Já que temos uma chave SSH configurada no computador, podemos usar o código SSH do repositório do Github. 👏👏👏
