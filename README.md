# Yaguareté — instaladores

Yaguareté é um aplicativo de gabinete que leva o processo trabalhista do PDF à minuta de sentença: lê os autos, monta o mapa do caso, as provas e as diretrizes, e redige a minuta para revisão do juiz. Este repositório publica **só os instaladores** (na página de [Releases](https://github.com/fgbkiwi/yaguarete-releases/releases/latest)), estas instruções e o manual.

📘 **[Manual do Yaguareté (PDF)](Manual-do-Yaguarete.pdf)** — primeiro uso, as telas, a minuta, a auditoria e solução de problemas.

## Windows (10 ou 11, 64 bits)

1. Abra a [última Release](https://github.com/fgbkiwi/yaguarete-releases/releases/latest) e baixe `Yaguarete_<versão>.exe`.
2. Execute o arquivo e siga o assistente. A instalação é na pasta do seu usuário e **não pede administrador**.
3. Abra o **Yaguareté** pelo menu Iniciar. A janela usa o Microsoft Edge WebView2, que já vem com o Windows 11 e com as versões atuais do Windows 10.

Se o Windows exibir o aviso do SmartScreen ("O Windows protegeu o computador"), clique em **Mais informações** e em **Executar assim mesmo**: o instalador ainda não é assinado digitalmente.

## Linux (Ubuntu 22.04 ou mais novo, Pop!_OS, Debian equivalente; amd64 ou arm64)

1. Na [última Release](https://github.com/fgbkiwi/yaguarete-releases/releases/latest), baixe `Yaguarete_<versão>_<arquitetura>.deb`.
2. Instale:

```bash
sudo apt install ./Yaguarete_<versão>_amd64.deb
```

3. Abra o **Yaguareté** pelo menu de aplicativos, ou rode `yaguarete` no terminal. No Linux o aplicativo abre no navegador padrão e continua rodando até ser encerrado (Ctrl+C no terminal, ou `pkill -f yaguarete_launcher`).

## Conferir o arquivo baixado (opcional)

Cada instalador vem com um arquivo `.sha256` na mesma Release. O aplicativo faz essa conferência sozinho ao atualizar; para conferir à mão:

```powershell
(Get-FileHash .\Yaguarete_<versão>.exe -Algorithm SHA256).Hash
```

```bash
sha256sum -c Yaguarete_<versão>_amd64.deb.sha256
```

## Atualizações

Uma vez por dia o Yaguareté consulta esta página de Releases. Havendo versão nova, aparece um aviso no alto da tela com **Baixar e instalar**, **Página da versão** e **Depois**. O instalador só é aberto depois de conferido pelo SHA-256; feche o Yaguareté antes de concluir a instalação. Processos, ajustes e acervo não são alterados. Sem internet, o aplicativo segue normalmente, sem aviso.

## Onde ficam os dados

Tudo fica no seu computador:

| Sistema | Pasta de dados |
| --- | --- |
| Windows | `%LOCALAPPDATA%\Yaguarete` |
| Linux | `~/.local/share/Yaguarete` |

As chaves dos provedores de modelo vão para o cofre de credenciais do sistema, nunca para arquivos. Desinstalar o programa não apaga essa pasta.

## Desinstalar

Windows: *Configurações > Aplicativos > Yaguarete > Desinstalar*. Linux: `sudo apt remove yaguarete`.
