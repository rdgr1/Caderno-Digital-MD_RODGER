Para descompactar esses arquivos, você vai precisar do pacote xz-utils. Para  
realizar a instalação do mesmo, utilize o comando abaixo:

```
sudo apt install xz-utils
```

Com o pacote instalado você pode realizar a extração do arquivo utilizando o  
comando "tar" com alguns parâmetros.

Para apenas realizar a descompactação do arquivo, utilize o comando abaixo:

```
tar -xJf [nomeDoArquivo].xz
```

**x** - Realiza a extração dos arquivos  
**J** - Informa que será um arquivo xz (Tem que ser "J" maiúsculo, pois, faz diferença)  
**f** - Usa o arquivo ou dispositivo

Para realizar a descompactação exibindo os arquivos, utilize o comando abaixo:

```
tar -xvJf [nomeDoArquivo].tar.xz
```

**x** - Realiza a extração dos arquivos  
**v** - Lista verbosamento os arquivos processados  
**J** - informa que será um arquivo xz (Tem que ser "J" maiúsculo, pois, faz diferença)  
**f** - Usa o arquivo ou dispositivo