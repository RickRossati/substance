# SUBSTANCE
### HYBRID BASS ENGINE

Plugin de baixo em C++ com JUCE. VST3 e Standalone, Windows e Linux.

O baixo real continua no centro do sinal. O que muda é que você para de caçar o
parâmetro certo e passa a escolher uma personalidade sonora, e o motor traduz
essa intenção numa cadeia de processamento que continua aberta pra edição por
baixo do capô.

Feito por quem toca baixo: Ricardo Rossati, Mister RickRoss, 28 anos de
instrumento, professor da School of Rock, com passagem por televisão, rádio e
palcos de todo o país.

**[Download e descrição completa](https://misterrickross.com/substance/)** ·
[Manual em PDF](docs/MANUAL_SUBSTANCE_PT-BR.pdf) ·
[Read in English](README.md)

![Tela principal](res/main-screen.png)

## O que ele faz de verdade

Seu baixo entra. O plugin mede como aquele instrumento específico responde, e
amplia o timbre em cima do que você já toca.

- **Learn Tone** ouve 30 segundos de sinal válido, silêncio não conta, e guarda
  um perfil espectral do seu instrumento
- **Bass Vision** mostra cinco regiões musicais, então você vê o que está ouvindo
- **Equalizador gráfico de cinco bandas**, mais ou menos 12 dB, alinhado a essas
  mesmas regiões
- **Tracking monofônico** por autocorrelação, com afinador cromático que pode ser
  desligado sem desativar o tracking interno
- **Sub e oitavador sintetizados**, com preservação de ataque
- **CAB IR**, cinco gabinetes internos ou um WAV seu
- **Snapshots Cognitivos**, biblioteca de fábrica e quatro slots de captura e recall
- Cadeia completa: `OCTAVE → DRIVE → WAH FILTER → CHORUS → SYNTH LAYER → AMBIENCE → CAB IR → EQ`

## Os cinco Engines

Esta é a parte que não é preset com nome diferente. Cada Engine é um
comportamento distinto.

| Engine | O que faz |
|---|---|
| **Tequila** | Válvula assimétrica, memória magnética, corpo, sag e imagem central |
| **AI Mentor** | Nivelamento limpo, ataque protegido, ar controlado e imagem mix-ready |
| **Joker** | Ataque preservado e quatro gestos determinísticos, Bite, Drop, Squawk e Fracture, disparados pela sua execução |
| **Future Adviser** | Grave firme em mono, glass harmônico e campo estéreo bass-safe próprio |
| **N.I.N.A.** | Correção lenta e adaptativa em sentidos opostos para fontes escuras ou brilhantes, aprofundada pelo perfil aprendido |

Em cima disso vêm seis macros de personalidade: Texture, Weight, Motion, Chaos,
Space e Blend. O Blend é o único crossfade global de dry e wet.

O **ROSSIFY** lê as medições atuais e adapta a cadeia a elas. Em Manual, todos os
controles continuam inteiramente seus.

![Personalidades e macros](res/personalities.png)

## Como os Engines foram verificados

O projeto tem um renderizador offline que manda o mesmo groove e uma nota isolada
para os cinco Engines e compara os resultados. Um build só é aceito quando passa
em tudo isto:

- 10 de 10 pares de Engine distintos, nos dois cenários
- 30 de 30 respostas de macro
- Loudness calibrado entre os Engines
- DC seguro
- Determinismo do Joker, a mesma execução produz os mesmos gestos
- Estéreo bass-safe no Future Adviser
- Adaptação de polaridade correta na N.I.N.A.

O teste roda por `ctest`. É isso que impede cinco Engines de virarem, calados, um
Engine com cinco etiquetas.

## Free e Pro

Na primeira abertura aparece o **trial Pro de 15 dias**, sem cartão. Depois do
prazo, o áudio continua funcionando no modo Free.

- **Free** mantém o som central, processamento LIVE, tooltips e snapshots de fábrica
- **Pro** libera HYBRID, Advanced e DNA, presets do usuário e o conjunto completo de módulos

O Pro custa **R$ 297**, licença vitalícia, não é assinatura, com atualizações 1.x
incluídas. Uma licença ativa em até dois computadores.

## Instalação

### Windows

Baixar o `SUBSTANCE-Setup.exe` em
[Releases](https://github.com/RickRossati/substance/releases/latest) e executar.
O VST3 vai para `Program Files\Common Files\VST3`. Depois, rescan de VST3 na DAW.

O instalador ainda não é assinado digitalmente, então o Windows pode avisar
"Windows protegeu seu PC". Basta clicar em "Mais informações" e depois em
"Executar assim mesmo".

### Linux

```bash
tar xzf SUBSTANCE-Linux-x86_64.tar.gz
cd SUBSTANCE-Linux-x86_64
./install.sh
```

Instala o VST3 em `~/.vst3` e o standalone junto.

### Configuração rápida

1. Conectar o baixo na interface
2. Abrir o SUBSTANCE num canal de áudio
3. Tocar forte e subir o **INPUT** sem clipar
4. Conferir **AUDIO IN / ACTIVE** no rodapé
5. Rodar o **Learn My Bass** uma vez e escolher um Engine

![Análise de timbre](res/tone-analysis.png)

## O que ainda não existe

Dito na cara, pra ninguém comprar por promessa:

- **macOS**, está no roadmap, não foi lançado
- **Assinatura digital** do instalador Windows, por isso o SmartScreen avisa na primeira execução
- **Camada de samples reais** de dedo, palheta, mute e slide
- **Compressor multibanda e oversampling**
- Treinamento de longo prazo multi sessão da N.I.N.A.

## Código-fonte

O código não é público. Este repositório é a página do produto, o canal de
releases e o rastreador de problemas.

Relato de bug, log de crash e relato de compatibilidade com DAW são bem-vindos de
verdade nas [Issues](https://github.com/RickRossati/substance/issues), e são o
caminho mais rápido pra alguma coisa ser corrigida.

## Suporte

[Página de suporte](https://misterrickross.com/substance/support.html) ·
[Reembolso](https://misterrickross.com/substance/refund.html) ·
[Privacidade](https://misterrickross.com/substance/privacy.html)

Para trocar de máquina, o suporte pode resetar uma ativação mediante verificação
da compra.

## Licença

Proprietária. Ver [LICENSE.txt](LICENSE.txt).

O plugin pode ser baixado e usado livremente no modo Free. O que não é permitido
é compartilhar chave de licença, remover mecanismo de ativação, ou redistribuir o
plugin ou o instalador como produto próprio.

Construído com [JUCE](https://juce.com) 8.

---

© 2026 Ricardo Rossati, Mister RickRoss · Ross Audio
