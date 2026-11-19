# ComfyUI no Google Colab com Google Drive e Ngrok

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/alexandrebsimao/comfyUI/blob/main/comfyUI.ipynb)

Notebook pronto para rodar o **[ComfyUI](https://github.com/Comfy-Org/ComfyUI)** no **Google Colab** usando GPU gratuita (como a Tesla T4), com persistência de modelos e *custom nodes* no **Google Drive** e acesso à interface web via túnel **Ngrok**.

## O que este notebook faz

- **Persistência no Google Drive:** instala o ComfyUI em `/content/drive/MyDrive/ComfyUI`, preservando seus `models/`, `loras/` e `custom_nodes/` entre sessões do Colab.
- **Atualização automática:** nas execuções seguintes, detecta a instalação existente e atualiza o repositório com `git pull --ff-only`.
- **ComfyUI-Manager incluído:** já prepara o [ComfyUI-Manager](https://github.com/ltdrdata/ComfyUI-Manager) para facilitar a instalação de modelos e *custom nodes* pela própria interface.
- **Acesso externo via Ngrok:** solicita seu *Authtoken* do Ngrok via `getpass` (sem expor sua chave no código) e gera um link HTTPS público para acessar o ComfyUI no navegador.

## Pré-requisitos

1. Conta no **Google Colab** e espaço disponível no **Google Drive** (para o ComfyUI e os modelos que você baixar).
2. Conta gratuita no **[Ngrok](https://ngrok.com/)** para obter o seu **Authtoken**.

## Como usar

1. Clique no botão **Open In Colab** acima (ou faça upload do arquivo `comfyUI.ipynb` no Google Colab).
2. No menu do Colab, vá em **Ambiente de execução → Alterar o tipo de ambiente de execução** e selecione uma **GPU** (ex.: `T4 GPU`).
3. Execute a **Célula 1** para conectar o Google Drive, instalar/atualizar o ComfyUI e instalar as dependências.
4. Execute a **Célula 2**, cole o seu **Authtoken do Ngrok** quando solicitado e aguarde o link `🚀 LINK DE ACESSO` aparecer no output.
5. Abra o link gerado no navegador para usar a interface do ComfyUI.
6. *(Opcional)* Use a **Célula 3** para listar rapidamente os modelos presentes no seu Google Drive.

## Estrutura no Google Drive

```text
MyDrive/
└── ComfyUI/
    ├── models/
    │   ├── checkpoints/
    │   ├── loras/
    │   └── ...
    ├── custom_nodes/
    │   └── ComfyUI-Manager/
    └── main.py
```

## Observações

- Os modelos de geração de imagem/vídeo costumam ter vários gigabytes — fique atento ao espaço livre no seu Google Drive.
- Nunca salve seu token do Ngrok diretamente no código do notebook antes de compartilhar ou subir no GitHub.
