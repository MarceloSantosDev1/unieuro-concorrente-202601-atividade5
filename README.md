# RELATÓRIO DA NOME DA ATIVIDADE

**Disciplina:** Programação Concorrente / Computação Paralela  
**Aluno(s):** Marcelo (ADS)  
**Turma:** ________  
**Professor:** Prof. Rafael  
**Data:** 10/04/2026  

---

## 1. Descrição do Problema

O problema consiste em calcular a similaridade entre pares de perguntas utilizando o dataset do Kaggle (Quora Question Pairs).

Foi implementado um algoritmo baseado em **similaridade de Jaccard**, após limpeza e tokenização dos textos.

### Objetivo
Reduzir o tempo de processamento utilizando paralelização com MPI.

### Dados utilizados
- 5.000 perguntas
- 12.497.500 comparações

### Algoritmo
- Similaridade de Jaccard

### Complexidade
- O(n²)

---

## 2. Ambiente Experimental

- Processador: (preencher)
- Número de núcleos: (preencher)
- Memória RAM: (preencher)
- Sistema Operacional: Windows
- Linguagem: Python
- Biblioteca MPI: mpi4py
- Versão Python: 3.x

---

## 3. Metodologia de Testes

O tempo de execução foi medido com `MPI.Wtime()`.

Foram executadas as seguintes configurações:

- 1 processo
- 2 processos
- 4 processos
- 8 processos
- 12 processos

Cada execução foi realizada uma vez devido ao alto custo computacional.

---

## 4. Resultados Experimentais

| Processos | Tempo (s) |
|----------|----------|
| 1 | 34.74 |
| 2 | 26.77 |
| 4 | 17.11 |
| 8 | 13.08 |
| 12 | 12.17 |

---

## 5. Speedup e Eficiência

### Fórmulas

- Speedup = T(1) / T(p)
- Eficiência = Speedup / p

---

## 6. Tabela de Resultados

| Processos | Tempo (s) | Speedup | Eficiência |
|----------|----------|---------|------------|
| 1 | 34.74 | 1.00 | 1.00 |
| 2 | 26.77 | 1.30 | 0.65 |
| 4 | 17.11 | 2.03 | 0.51 |
| 8 | 13.08 | 2.66 | 0.33 |
| 12 | 12.17 | 2.85 | 0.24 |

---

## 7. Gráficos

- Tempo de execução vs processos
- Speedup vs processos
- Eficiência vs processos

---

## 8. Análise dos Resultados

Os resultados mostram melhora significativa de desempenho com MPI.

### Observações:
- Speedup não linear
- Eficiência decrescente
- Melhor faixa: 4 a 8 processos

### Causas:
- Overhead de comunicação MPI
- Lei de Amdahl
- Sincronização entre processos
- Complexidade O(n²)

---

## 9. Conclusão

O uso de MPI trouxe redução significativa no tempo de execução.

### Conclusões:
- Melhor desempenho entre 8–12 processos
- Escalabilidade moderada
- Ganhos limitados por overhead

### Melhorias futuras:
- Otimização do algoritmo
- Melhor balanceamento de carga
- Redução de comunicação entre processos
