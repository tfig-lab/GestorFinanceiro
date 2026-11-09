# Gestor Financeiro · Cash Flow Serra Norte

Painel de fluxo de caixa do engagement **Autônomos Exp Serra Norte** (Eng. 2002342439). É um único arquivo HTML que roda no navegador, sem servidor.

**Abrir:** `https://tfig-lab.github.io/GestorFinanceiro/` (depois de ativar o GitHub Pages)

## Acesso

O painel abre com login. Os dados ficam criptografados no HTML (AES-256-GCM, chave derivada do usuário e senha via PBKDF2) e só são lidos com as credenciais corretas. Peça o acesso ao responsável. As cópias geradas em **Salvar cópia** saem criptografadas com a mesma senha.

## Visões

| Aba | O que mostra |
|---|---|
| Visão executiva | Covered/Uncovered, Gain/Loss, faturas vencidas, posição acumulada e ponte do custo incorrido até o caixa |
| Fluxo de caixa | Tabela mensal: custos (receita de profissionais, receita do BOT, despesas) × faturamento e recebimento |
| Faturamento × Receita | Mês a mês e acumulado |
| Profissionais | Horas e receita por código ENG; por profissional em resumo, por mês ou por ENG (onde cada um debitou); filtros por código ENG e Henrique / Thomas |
| Despesas | Realizado × programado, faturado × a faturar, por categoria, pessoa ou código ENG, com filtro Henrique / Thomas |
| Contas a receber | Aging e lista de faturas |
| Projeção | Receita/despesa programadas e faturamento estimado para meses sem nota emitida |

## Atualizar os dados

1. Clique em **Importar bases** (ou arraste os arquivos para a página).
2. Selecione as exportações originais: **AR** e **TIME/EXPENSE** (.xls).
3. Use **Salvar cópia** para baixar um HTML com as bases e premissas novas. Para atualizar este site, substitua o `index.html` por essa cópia.

## Regras de cálculo

- Receita = Std. Price × Realização (padrão 14%, editável no topo).
- Faturamento líquido = valor da fatura − Tax Amount (AR).
- O AR não traz data de pagamento: faturas pagas entram no mês de vencimento; vencidas em aberto entram no mês corrente.
- BOT = recurso cujo nome começa com "BOT" ou cujo nível contém "BOT".
- Faturamento estimado entra como recebimento após o prazo de recebimento (padrão 2 meses).
- Responsável por código ENG: descrição terminando em "TH" = Thomas; demais = Henrique (ajustável na aba Projeção).
- Premissas editadas ficam salvas no navegador de quem editou.

## Ativar o GitHub Pages

Settings → Pages → Source: *Deploy from a branch* → Branch: `main` / `(root)` → Save.
