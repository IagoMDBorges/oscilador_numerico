# Oscilador Harmônico: Euler, RK2 e RK4

Comparação de métodos numéricos para a integração da equação de movimento do oscilador harmônico simples, contrastando os resultados com a solução analítica.

## Descrição

O projeto resolve numericamente o sistema

```
dx/dt = v
dv/dt = -ω² x
```

usando três métodos de integração:

- **Euler (explícito)** — método de 1ª ordem
- **RK2 (Runge-Kutta de 2ª ordem)**
- **RK4 (Runge-Kutta de 4ª ordem)**

Os resultados numéricos são comparados com a solução analítica exata, permitindo avaliar a precisão e o comportamento do erro de cada método em função do passo de integração `h`.

## Estrutura

```
.
├── oscilador_euler_rk2_rk4.ipynb   # Notebook principal com implementação e análise
└── imagens/   # gráficos gerados          
```

## Resultados

### Trajetória temporal

Comparação da posição `x(t)` obtida por cada método com a solução exata. O método de Euler acumula erro de fase visivelmente ao longo do tempo, enquanto RK2 e RK4 permanecem praticamente sobrepostos à solução analítica.

![Trajetória temporal](imagens/trajetória_temporal.png)

### Espaço de fase

No plano `(x, v)`, a solução exata e as de RK2/RK4 descrevem uma órbita fechada (círculo), como esperado para o oscilador harmônico. Já o método de Euler diverge visivelmente, espiralando para fora — evidência de que o método introduz um ganho irreal de energia.

![Espaço de fase](imagens/espaço_de_fase.png)

### Análise de convergência

Erro absoluto final em função do passo de integração `h`, em escala log-log. As inclinações das retas confirmam a ordem de convergência esperada de cada método: Euler (1ª ordem), RK2 (2ª ordem) e RK4 (4ª ordem), com RK4 mantendo erro desprezível mesmo para passos maiores.

![Análise de convergência](imagens/análise_de_convergência.png)

## Requisitos

- Python 3.8+
- NumPy
- Matplotlib

## Como executar

Abra o notebook com Jupyter:

```bash
jupyter notebook oscilador_euler_rk2_rk4.ipynb
```

