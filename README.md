# DivisionX 🎧

![License](https://img.shields.io/badge/License-GPLv3-blue.svg)
![Python](https://img.shields.io/badge/Python-3.8+-yellow.svg)
![OS](https://img.shields.io/badge/OS-Windows%20%7C%20Linux-success.svg)

**DivisionX** é um downloader de áudio multi-plataforma e otimizador construído com Python e CustomTkinter. Desenvolvido para ser rápido, robusto e lidar perfeitamente com metadados e conversões pesadas de áudio.

Além de baixar músicas em alta qualidade com injeção automática de capas (ID3 tags), o sistema conta com um **Modo Tok Escola**, que padroniza faixas de áudio especificamente para sistemas de som escolares e PAs antigos, evitando travamentos por excesso de metadados ou taxas de amostragem incompatíveis.

## ✨ Funcionalidades

* **Downloader Multi-plataforma:** Suporte nativo para YouTube, SoundCloud, e outras centenas de plataformas via motor `yt-dlp`.
* **Corte de Tempo Dinâmico (Cutter):** Defina o início e o fim (ex: `00:30` até `01:30`) e o aplicativo cortará o áudio *durante* o download, economizando tempo e banda.
* **Modo Tok Escola:** Um switch dedicado que otimiza o áudio para hardwares limitados:
  * Taxa de amostragem cravada em `44100Hz`.
  * Conversão para canal `Mono` (evita cancelamento de fase em caixas de som).
  * Normalização de volume inteligente (`loudnorm`).
  * Remoção completa de imagens e metadados pesados do arquivo final.
* **Modo Normal:** Qualidade máxima (`320kbps`) com injeção nativa da capa do vídeo direto no arquivo `.mp3`.
* **Interface Moderna:** Tema escuro *Midnight Purple* construído com `customtkinter`.

## 🚀 Como usar

### Pré-requisitos
* **Python 3.8** ou superior.
* **FFmpeg** instalado na máquina e adicionado às variáveis de ambiente (PATH).

### Instalação

1. Clone este repositório:
   ```bash
   git clone https://github.com/yukkibr/DivisionX
   cd DivisionX
   
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Execute o aplicativo:
   ```bash
   python app.py
   ```

## 🛠️ Build (Criando o Executável)

Para compilar o aplicativo de forma nativa e isolada (Linux ou Windows), utilize o PyInstaller com os parâmetros de injeção da interface:

```bash
pyinstaller --noconfirm --onedir --windowed \
  --add-data "caminho_do_seu_python/site-packages/customtkinter:customtkinter/" \
  --add-data "JetBrainsMonoNerdFont-Regular.ttf:." \
  --hidden-import PIL._tkinter_finder \
  app.py
```

## 📄 Licença

Este projeto está licenciado sob a **GNU General Public License v3.0 (GPL-3.0)**. Isso significa que o aplicativo é livre e de código aberto. Você pode usar, modificar e distribuir, desde que as modificações também sejam abertas sob a mesma licença.

---
*Desenvolvido por Eduardo Campos*
