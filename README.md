# Quem Sou Eu?

Jogo de adivinhação para jogar com amigos, direto no celular. Escolha um tema, segure o celular na testa com a tela virada para os outros, eles dão as dicas e você tenta descobrir quem (ou o que) você é.

**Jogar:** https://gustavoktausend.github.io/quem-sou-eu/

## Como funciona

- 12 temas prontos (animais, comidas, profissões, filmes e séries, personagens, marcas…) com mais de 900 palavras, além do modo "Tudo misturado".
- Rodadas de 30, 60 ou 90 segundos, ou sem limite de tempo.
- O jogo é na horizontal: instalado no Android ele já abre deitado; no navegador ele trava a orientação ao começar a rodada quando o sistema permite, e em pé mostra um aviso para girar o celular.
- Para responder, incline o celular **para baixo** quando acertar e **para cima** para pular (estilo Heads Up). Quem está vendo a tela também pode tocar em **Acertou** ou **Pular**. No fim aparece o placar com tudo que saiu.
- No iPhone, o Safari pede permissão para usar o sensor de movimento na primeira rodada; se negar, os botões continuam funcionando.
- Temas personalizados: crie o seu com uma palavra por linha (fica salvo só no aparelho).
- As palavras não se repetem até a lista do tema esgotar.

## PWA

É um app instalável e funciona offline depois do primeiro acesso:

- **Android/Chrome:** toque em "Instalar na tela inicial" ou use o menu do navegador.
- **iPhone/Safari:** Compartilhar → Adicionar à Tela de Início.

## Estrutura

```
index.html            jogo inteiro (HTML, CSS e JS)
manifest.webmanifest  manifesto do PWA
sw.js                 service worker (cache para uso offline)
icons/                ícones do app
```

Não há build nem dependências: é só servir os arquivos estáticos. Para rodar local, `python3 -m http.server` na pasta e abrir `http://localhost:8000`.

Para publicar uma versão nova, troque o valor de `VERSION` em `sw.js` (ex.: `qse-v2`) para que os aparelhos que já instalaram baixem os arquivos atualizados.
