# Organizador de resultados de simulações

Script em Python que automatiza a organização de resultados de simulações compactadas em `.tar.gz`.

Para cada pacote encontrado na pasta (e em todas as subpastas), o script:

1. Lê o arquivo `initialConditions` **direto do pacote**, sem descompactar tudo, e extrai a temperatura e a velocidade do escoamento.
2. Cria uma pasta de destino com nome padronizado, por exemplo `mach08e-T300-V100_0_0-008_04`, combinando o prefixo da subpasta, os parâmetros lidos e o número do caso.
3. Copia para essa pasta apenas os arquivos de interesse.
4. Pula os casos que já foram processados.

Assim, um trabalho manual de abrir e renomear dezenas de pacotes vira um único comando.

## Como usar

1. No `main.py`, ajuste `pasta_mae` (onde estão as simulações) e `pasta_destino_geral` (onde ficam os resultados).
2. Se quiser, defina `limite_por_tar` e `limite_total` para processar só uma amostra.
3. Rode:

```bash
python main.py
```

Usa apenas a biblioteca padrão (`os`, `tarfile`, `re`).
