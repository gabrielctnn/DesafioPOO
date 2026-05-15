### 1. `Conteudo` (Classe Abstrata Mãe)
Funciona como o contrato base para tudo o que pode ser ensinado na plataforma.
* **Atributos:** `titulo` (String), `descricao` (String).
* **Constante:** `XP_PADRAO = 10.0` (Double).
* **Método Abstrato:** `calcularXp()`.

### 2. `Curso` (Classe Filha)
Representa um bloco de aulas tradicionais com carga horária fixa.
* **Atributos:** Herda de `Conteudo` e adiciona `cargaHoraria` (int).
* **Polimorfismo:** `calcularXp()` retorna o `XP_PADRAO` multiplicado pela `cargaHoraria`.

### 3. `Mentoria` (Classe Filha)
Representa um evento ou live com uma data específica.
* **Atributos:** Herda de `Conteudo` e adiciona `data` (`LocalDate`).
* **Polimorfismo:** `calcularXp()` retorna o `XP_PADRAO` acrescido de um bônus fixo de `20.0`.

### 4. `Bootcamp` (Classe Gerencial)
Agrupa uma coleção de conteúdos e uma lista de desenvolvedores participantes.
* **Atributos:** `nome` (String), `descricao` (String), `dataInicial` (`LocalDate`), `dataFinal` (`LocalDate`), `devsInscritos` (`Set<Dev>`), `conteudos` (`Set<Conteudo>`).

### 5. `Dev` (Classe de Regra de Negócio)
Representa o usuário da plataforma e gerencia suas matrículas e conquistas.
* **Atributos:** `nome` (String), `conteudosInscritos` (`Set<Conteudo>`), `conteudosConcluidos` (`Set<Conteudo>`).
* **Métodos Principais:**
    * `inscreverBootcamp(Bootcamp bootcamp)`: Adiciona todos os conteúdos do bootcamp à lista de inscritos do Dev e o matricula no respectivo bootcamp.
    * `progredir()`: Remove o primeiro conteúdo da lista de pendentes (`conteudosInscritos`) e o move para a lista de sucessos (`conteudosConcluidos`).
    * `calcularTotalXp()`: Varre o conjunto de conteúdos concluídos e soma o XP gerado por cada um de forma polimórfica.

---

## 🛠️ Por que usar `LinkedHashSet`?

O uso da estrutura de dados correta é crucial na arquitetura de software:
* **`Set`:** Garante que um desenvolvedor **não possa se inscrever repetidamente no mesmo curso** dentro do mesmo contexto (evitando duplicidade).
* **`LinkedHashSet`:** Diferente de um `HashSet` comum (que não garante nenhuma ordenação), o `LinkedHashSet` mantém os elementos exatamente na **ordem cronológica em que foram adicionados**. Isso simula uma trilha de aprendizagem sequencial perfeitamente.

---

## 🚀 Como Executar o Projeto

1. Certifique-se de ter o **JDK 11 ou superior** instalado em sua máquina.
2. Clone este repositório:
   ```bash
   git clone [https://github.com/seu-usuario/desafio-poo-dio.git](https://github.com/seu-usuario/desafio-poo-dio.git)