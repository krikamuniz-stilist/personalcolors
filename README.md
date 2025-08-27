# Colorimetria & Pantone — Questionário + Laudo (Web App)

Um app **100% estático (HTML único)** para consultoria de imagem e colorimetria:
- Questionário guiado → **Gera Laudo** com estação sugerida, subtom, contraste e intensidade.
- **Exporta em PDF** (impressão do navegador).
- **Assinaturas** via *canvas* (cliente e analista).
- **QR duplo** no PDF: site/Instagram e **vCard** (contato).
- **Dark mode** alternável.
- **Numeração do laudo** (PREFIXO-ANO-SEQ) com auto-contador por ano.
- **Baixar HTML**: salva uma cópia do app com seu estado (logo, fotos, respostas, tema/cor).

## ✨ Como usar (localmente)
1. Baixe os arquivos deste repositório (ou o `.zip` aqui do chat).
2. Abra **`index.html`** no seu navegador.
3. Preencha o questionário → clique **Gerar laudo** → **Exportar PDF**.
4. Para salvar o app com tudo preenchido, clique **Baixar HTML** (gera um novo arquivo com o estado embutido).

> Nada é enviado a servidor. Os dados ficam no **localStorage do navegador**.

## 🚀 Publicar com GitHub Pages
1. Crie um repositório e faça upload de **`index.html`** e **`favicon.ico`**.
2. Vá em **Settings → Pages** e selecione **Deploy from a branch (main / root)**.
3. A URL pública aparecerá em poucos minutos (ex.: `https://seuusuario.github.io/seu-repo/`).

## 🧩 Integração em site (iframe)
Depois de publicar, você pode incorporar uma página do seu site com:
```html
<iframe src="https://SEU-APP-aqui.netlify.app" style="width:100%;height:90vh;border:0" allowfullscreen></iframe>
```
> Se o construtor bloquear impressão/download via `sandbox`, inclua também um botão **“Abrir em nova aba”**.

## 🎨 Personalização rápida
- **Logo**: carregue a imagem no topo do *builder*.
- **Cor da marca**: ajuste no seletor de cor (memorizado automaticamente).
- **Estilo do laudo**: *Minimal* (sans) ou *Editorial* (serif).
- **Nº do laudo**: escolha **Prefixo / Ano / Sequencial** (deixe Sequencial em branco para autonumerar por ano).
- **Dark mode**: botão “🌙 Modo escuro”.

## 🧠 Como o laudo é calculado
O app pondera respostas (quente × frio, claro × escuro, suave × intenso) para sugerir uma **estação sazonal** e gerar:
- **Subtom** (Warm/Cool/Neutro)
- **Contraste** (Alto/Médio/Baixo)
- **Intensidade** (Alta/Baixa)
- Paletas e **sugestões de cores** (com referências Pantone aproximadas)
- **Dicas de maquiagem** por estação

> O resultado é um **ponto de partida**. Recomendado validar com **teste de tecidos** em luz natural.

## 🧪 Exportar PDF
- Usa a janela de impressão do navegador (`window.print()`).
- Em iOS/iPadOS: Compartilhar → **Salvar como PDF**.
- Há um **rodapé de impressão** com marca/contatos e **QR duplo** (site e vCard).

## 🧾 Arquivos
- **`index.html`** – o app completo.
- **`favicon.ico`** – ícone do site (incluído no `<head>`).
- (Opcional) **`README.md`** – este guia.

## ❓ Dúvidas comuns
- **Perdi o sequencial do laudo**: o contador fica no `localStorage` por ano (`colorim_seq_YYYY`). Limpe o site/dados para reiniciar.
- **Quero trocar a paleta**: edite o array `palettes` em `index.html`.
- **Sem internet o QR funciona?** O QR do vCard sim; o QR do site depende de conexão para abrir.

---

Feito com ❤️ para Consultoria de Imagem.
