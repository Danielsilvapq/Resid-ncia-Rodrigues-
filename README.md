# Residência Rodrigues — Finanças da casa

Sistema para Daniel e Roberta acompanharem as finanças da casa.

**Abrir o sistema:** https://claude.ai/artifact/A3mbX71xjCJEHfsqShzcs6

## O que tem

- **Resumo:** receitas, despesas, saldo e quanto do orçamento já foi usado no mês; gráfico dos últimos 6 meses; despesas por categoria; quem pagou (Daniel, Roberta ou os dois); situação das contas fixas.
- **Lançamentos:** lista do mês agrupada por dia, com filtros por tipo, pessoa, categoria e busca. Toque num lançamento para editar ou excluir.
- **Orçamento:** limite mensal por categoria, com barra de progresso (verde, atenção a partir de 80%, vermelho quando estoura) e o ritmo do mês.
- **Contas fixas:** aluguel, luz, internet etc. Ao marcar como paga, a despesa entra sozinha nos lançamentos do mês.

## Como funciona

O app é um único arquivo, `index.html`, publicado como página no claude.ai. Os dados ficam num banco de dados da própria página e sincronizam em tempo real entre quem tem acesso.

Para Roberta poder lançar, compartilhe o link pelo menu **Compartilhar** da página com o e-mail dela, com permissão de **Editor**.

Aberto fora do Claude (por exemplo, direto no navegador), o arquivo funciona em modo de teste: nada é salvo.

### Dados

| Coleção | Conteúdo |
|---|---|
| `lancamentos` | `tipo` (despesa/receita), `valor` (em centavos), `data` (AAAA-MM-DD), `categoria`, `pessoa`, `descricao`, `fixaId` (quando veio de uma conta fixa), `criadoEm` |
| `fixas` | `nome`, `valor` (centavos), `dia` de vencimento, `categoria`, `pessoa`, `ativa` |
| `config/orcamento` | `limites`: categoria → valor em centavos |
