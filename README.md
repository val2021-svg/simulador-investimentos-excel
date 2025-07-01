# Simulador de Investimentos em Fundos Imobiliários (FIIs)

Esta planilha em Excel foi criada para ajudar investidores a simular aportes mensais em FIIs, acompanhar a evolução do patrimônio e projetar dividendos futuros de maneira rápida e transparente.

## Como usar

1. **Abra** o arquivo `simulador_fii.xlsx` no Excel (ou Google Sheets‑compatível).  
2. **Altere** os parâmetros de entrada (coluna **B**):  
   - **Investimento inicial** (`B1`)  
   - **Aporte mensal** (`B2`)  
   - **Taxa de rendimento mensal** (`B3`) – use formato decimal (ex.: 0,008 ⇒ 0,8 %/mês)  
   - **Meses** (`B4`) – horizonte da simulação  
3. A tabela a partir da linha 7 é atualizada automaticamente com:  
   - Patrimônio acumulado mês a mês  
   - Rendimento/dividendo de cada mês  
   - Dividendos acumulados  
4. No final da planilha você encontra um **resumo** com:  
   - **Total investido**  
   - **Patrimônio final**  
   - **Dividendos totais**  

> **Dica:** sinta‑se à vontade para copiar/colar a tabela em um dashboard ou usar gráficos do Excel para visualizar a evolução do patrimônio.

## Estrutura da planilha

| Seção | Descrição |
|-------|-----------|
| **Entradas (linhas 1‑4)** | Parâmetros que o usuário pode editar |
| **Tabela de simulação (linhas 6‑…)** | Cálculo mês a mês do patrimônio e dividendos |
| **Resumo (após a tabela)** | Métricas finais da simulação |

## Fórmulas principais

- **Patrimônio acumulado**  
  ```excel
  =C{n-1}*(1+$B$3)+$B$2
  ```  
  (capital do mês anterior rendendo à taxa mensal e somando o aporte)

- **Rendimento do mês**  
  ```excel
  =C{n-1}*$B$3
  ```

- **Dividendos acumulados**  
  ```excel
  =E{n-1}+D{n}
  ```

- **Total investido**  
  ```excel
  =$B$1 + $B$2*$B$4
  ```

## Requisitos

- Microsoft Excel 2016 ou superior (ou equivalente que suporte fórmulas do Excel).
