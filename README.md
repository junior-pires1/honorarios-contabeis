# Honorários Contábeis — Sistema de Precificação

Sistema de precificação técnica para escritórios de contabilidade: calcula o
honorário mensal de cada cliente a partir do custo-hora real da equipe, do
regime tributário, do volume operacional, do fator de risco fiscal e de um
piso mínimo (anti-dumping) — e já gera a proposta comercial pronta para
enviar ao cliente.

## Como usar

Não precisa instalar nada. É um único arquivo HTML autocontido.

1. Baixe (ou clone este repositório) e abra `honorarios.html` em qualquer
   navegador — funciona offline, sem servidor.
2. Ou publique com **GitHub Pages** (Settings → Pages → Deploy from branch →
   `main` → `/ (root)`) para ter um link que qualquer pessoa da equipe acessa
   direto do navegador.

## Onde ficam os dados

Cada pessoa que abre o arquivo tem seus próprios dados salvos **no
armazenamento local do navegador dela** (`localStorage`) — não existe um
banco de dados central nem sincronização entre pessoas ou dispositivos.
Isso significa:

- Se você limpar os dados de navegação, ou abrir em outro navegador/computador,
  os dados não aparecem — use o backup abaixo para levar seus dados com você.
- Cada colaborador que for usar o sistema começa com os clientes de exemplo
  (pode editar ou remover) e mantém sua própria carteira salva localmente.

## Backup e restauração

No rodapé do menu lateral existem dois botões:

- **⭳ Backup** — baixa um arquivo `.json` com todos os dados atuais (custos
  fixos, equipe, parâmetros, clientes, tabela de serviços avulsos).
- **⭱ Importar** — carrega um arquivo `.json` de backup, substituindo os
  dados atuais neste navegador.

Recomendado: exportar um backup periodicamente (ex.: toda sexta-feira) e
guardar em local seguro (Drive, e-mail, etc.), e sempre que for repassar a
base de clientes para outra pessoa/computador.

## O que o sistema calcula

- **Custo-hora por função** (Fiscal, Contábil, Departamento Pessoal, BPO,
  Sênior) a partir da folha da equipe e dos encargos.
- **Fórmula de precificação**: `(Custo Direto + Custo Indireto) × (1 + Margem) × Fator de Risco`,
  com fator de risco por regime (Simples = 1,0 · Presumido = 1,3–1,5 ·
  Real = 1,8–2,5).
- **Piso de honorários** (trava anti-dumping: maior entre piso de mercado e
  múltiplo de horas do sênior).
- **Franquias e excedentes** de documentos e lançamentos bancários.
- **Grupo econômico / múltiplos CNPJs**, **provisão de inadimplência**,
  **sazonalidade** (fechamento anual — ECD/ECF), **tabela de serviços
  avulsos** e **condições comerciais** (vencimento, multa/juros, reajuste,
  aviso prévio).
- **Proposta comercial pronta** para copiar ou imprimir/exportar em PDF.

## Aviso

Ferramenta de apoio à decisão comercial — os parâmetros (margens, fatores de
risco, franquias, alíquotas) refletem a realidade de cada escritório e devem
ser revisados e ajustados por um responsável técnico antes de uso em
produção.
