# ROTA LIVRE · Generative AI for Engineering

Entrega das etapas 1, 2 e 3 da Global Solution FIAP 2026.2. Este repositório independente reúne os arquivos da disciplina e se integra ao ROTA LIVRE por contratos documentados.

| Etapa | Entrega |
| --- | --- |
| 1 | [Problema, tarefa e critérios de aceite](docs/01_problema_tarefa.md) |
| 2 | [Metodologia e 30 casos com gabarito](avaliacao/README.md) |
| 3 | [Curadoria e proveniência](docs/03_base_documental.md) e [base documental](base/README.md) |

Na pasta deste README, execute com Python 3.10 ou superior. A validação funciona offline com a biblioteca padrão.

```sh
python -B scripts/validar_base.py
python -B -m unittest discover -s tests -v
```

A entrega inclui o contrato do assistente, a base e os testes de integridade. As etapas 4 a 6 acrescentam recuperação, geração JSON e comparação local. Os resultados estão em avaliacao/.

## Próximos passos

1. Indexar apenas os chunks, preservando os IDs, dispositivos e URLs. Comparar busca lexical e semântica usando as evidências esperadas e medir Recall@k.
2. Executar um LLM local com a pergunta e os trechos recuperados. Validar as citações contra o contexto enviado e aplicar o contrato de esclarecimento, recusa e ausência de evidência.
3. Rodar a avaliação com o gabarito isolado e revisar manualmente as respostas, incluindo omissões, alucinações e recusas incorretas.

## Etapas 4 a 6 · Execução local

- [Recuperação semântica e instalação no Windows](docs/04_busca_rag.md)
- [Geração JSON com modelo local](docs/05_geracao_json.md)
- [Agente especializado e comparação](docs/06_agente_especializado.md)

## Etapas 7 a 9 · Auditoria local

Execute na raiz, com o ambiente Python das etapas 4 a 6 ativo:

- `python -B -m scripts.avaliar_qualidade`
- `python -B -m unittest discover -s tests -v`

A auditoria lê o histórico das 90 execuções. Consulte o [placar](avaliacao/analise_comparativa.md), os [critérios](docs/08_acertos_alucinacoes.md) e os [cinco diagnósticos](avaliacao/cinco_erros_reais.md).
