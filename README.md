# TDD × test-last: reanálise de dados de um experimento publicado

Projeto final da disciplina MCEQ 12576 (Métodos de Computação Experimental e Quantitativa), PUC-Campinas, 2º semestre de 2026.

**Equipe:** Gabriel Adorno Simoso, Renan Ribeiro Bertolotto, Vitor Manzano Villela Dias.

## Pergunta de pesquisa

Em tarefas de implementação em Java no contexto acadêmico, adotar TDD em vez de test-last (TLD) altera a produtividade, medida pelo percentual de asserts de aceitação aprovados (PROD)?

- **H0:** µTDD = µTLD
- **H1 (bilateral):** µTDD ≠ µTLD

Este é um estudo de reanálise de dados públicos. Não há coleta própria.

## Dados

| Item | Informação |
| --- | --- |
| Origem | Fucci, Scanniello, Romano, Shepperd, Sigweni, Uyaguari, Turhan, Juristo e Oivo. *An External Replication on the Effects of Test-driven Development Using a Multi-site Blind Analysis Approach*. ESEM 2016. Artigo: [10.1145/2961111.2962592](https://doi.org/10.1145/2961111.2962592) |
| Repositório dos dados | Zenodo, versão 1.0.0, publicada em 12/09/2022: [10.5281/zenodo.7071956](https://doi.org/10.5281/zenodo.7071956) |
| Data de acesso | 27/10/2026 |
| Licença | CC BY 4.0 (reuso e redistribuição com crédito aos autores) |
| Arquivo | `dados/brutos/MetricsExtractionMR_BSK.xlsx` (md5 `062bc7f103aeb4212bca2741ad13221d`) |

O arquivo original não foi alterado. Todo tratamento é feito por script e gera arquivos em `dados/limpos/`.

### Como os dados foram produzidos

Experimento cruzado 2×2 com 21 estudantes de pós-graduação voluntários (20 válidos). Cada participante resolveu duas tarefas em sessões de 3 horas, em Java, Eclipse e JUnit: Mars Rover (dia 1, 15/04/2015) e Bowling Scorekeeper (dia 2, 22/04/2015). A sequência dos tratamentos foi sorteada pelos autores: o grupo A usou TDD no dia 1 e test-last no dia 2; o grupo B, o inverso. As métricas vêm de uma suíte de testes de aceitação escondida dos participantes.

### Variáveis da planilha

| Coluna | Significado | Escala |
| --- | --- | --- |
| `ID` | Participante (anônimo) | Inteiro |
| `Grupo` | Sequência dos tratamentos (A ou B) | Nominal |
| `#TUS` | Histórias de usuário abordadas (pelo menos 1 assert de aceitação aprovado) | Contagem |
| `PERTUS` | Percentual de histórias abordadas (não definida no artigo; deduzida dos valores) | 0 a 100 |
| `QLTY` | Qualidade externa: média, sobre as histórias abordadas, da fração de asserts aprovados | 0 a 100 |
| `PROD` | Produtividade (variável de resposta): % dos asserts de toda a suíte de aceitação aprovados | 0 a 100 |
| `#TESTS` | Esforço de teste: asserts JUnit escritos pelo participante | Contagem |

## Estrutura do repositório

```
dados/brutos/   planilha original dos autores (não editar)
dados/limpos/   arquivos gerados pelo script
docs/           protocolo do projeto, escrito antes da análise
```

## Como reexecutar

> A completar até 10/11, quando o script de carga e limpeza existir.

1. Clonar o repositório.
2. Instalar as dependências: `pip install -r requirements.txt`.
3. Rodar o script (nome e comando a registrar aqui).
4. Conferir os números e figuras do artigo.

## Protocolo e integridade

O protocolo (`docs/`) foi escrito antes de qualquer análise própria dos dados e fixa a hipótese, o teste, o nível de significância e as exclusões. Só isso é confirmatório. Qualquer análise fora do protocolo será apresentada como exploratória.

## Créditos e licença

Os dados são dos autores citados acima, usados sob CC BY 4.0. A licença do código desta equipe será definida antes da entrega.
