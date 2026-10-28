# Trabalho — Proposta de Robô com Aprendizado de Máquina

**Cata-vento Seletivo.** Disciplina *Modelagem e Projeto de Algoritmos para o
Mercado Financeiro*, Prof. Alexandre Pimenta. Grupo: Luisa Caetano Araujo e
Raíssa. Enunciado em `Documentacao/Enunciado.pdf`.

**Etapa atual: só a proposta** (texto + apresentação), sem código. A
implementação vem na semana seguinte.

## A ideia em uma página

- Base: a regra do ADX Cata-vento (Trabalho 01, `../ADX-Cata-vento`),
  afrouxada para ADX ≥ 20, gera **candidatos**. DMI 12 fixo.
- **Random Forest** (escolha da Luisa: "traz resultado bom, implementa fácil,
  LSTM é chato") filtra: estima P(alvo 3 ATR antes do stop 1,5 ATR, antes das
  17:30) e só entra se P ≥ p*. Rótulo pelas três barreiras.
- Walk-forward: 120 pregões (90 treino + 30 validação) → opera 20 → avança 20.
  WIN$ M15 2023–2026, ~40 ciclos fora da amostra.
- Objetivo para escolher hiperparâmetros e p*: fator de recuperação nas
  operações filtradas da validação, com custos; N ≥ 20 e FL ≥ 1,05.
- Implementação planejada: CSV exportado do MT5 → Python (pandas,
  scikit-learn) → opcional ONNX no MT5.

O Algoritmo Genético foi a primeira escolha e foi trocado — não voltar a ele.

## Arquivos

```
Proposta/Proposta_CataVento_Seletivo.html|.pdf   texto (A4), tópicos 4.1–4.4
Apresentacao/Slides_CataVento_Seletivo.html|.pdf 11 lâminas, modo Apresentar (F)
```

PDF: Chrome headless `--print-to-pdf` com `--no-pdf-header-footer`.

## Identidade visual dos slides — "Floresta noturna" (escolhida em 28/10)

Escolhida entre 5 ideias. Os decks anteriores (Trabalho 01, RSI Sniper) foram
referência de clima, **não molde** — ela recusou a cópia. Tokens: fundo
`#08120E` com radial `#12261D`, cartões `#0E1D17`/`#122419`, menta `#5EE6A8`
(com brilho), âmbar `#F2B84B`, vermelho `#F0626B`. Schibsted Grotesk + IBM
Plex Mono. A árvore de decisão com o caminho aceso é a marca (capa e
encerramento); o progresso é uma trilha de nós no rodapé. HTML autocontido,
sem dependência dos decks antigos.

## Pendências

- Sobrenome e RA da Raíssa, RA da Luisa e data de entrega (marcados em amarelo
  na proposta; nos slides só aparece "Raíssa").
