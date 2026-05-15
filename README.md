# 📚 Abstração de um Bootcamp com Java POO

Este repositório foi criado com o objetivo de documentar meus estudos práticos sobre a **Programação Orientada a Objetos (POO)** no ecossistema Java. 

A ideia do projeto foi desenvolver um sistema que simula o funcionamento de uma plataforma de cursos e bootcamps (como a própria DIO), aplicando conceitos de arquitetura de software, herança, polimorfismo e manipulação avançada de coleções de dados.

---

## 🔍 O que é o Desafio?

O desafio consiste em modelar e codificar o ecossistema de um Bootcamp. No mundo real, um ambiente de aprendizado possui alunos, professores, cursos, mentorias e prazos. O objetivo aqui foi traduzir essa complexidade para o código estruturado em Java.

O sistema gerencia as seguintes regras de negócio:
* **Conteúdos:** A plataforma oferece **Cursos** (com carga horária) e **Mentorias** (com uma data específica). Ambos geram XP (experiência) para o aluno, mas calculados de formas diferentes.
* **Bootcamps:** Agrupam um conjunto específico de cursos/mentorias e possuem uma data de início e fim.
* **Desenvolvedores (Devs):** Podem se inscrever em um Bootcamp. Ao se inscreverem, recebem a lista de conteúdos pendentes. À medida que avançam ("progridem"), os conteúdos saem da lista de "inscritos" e vão para a lista de "concluídos", recalculando o XP total do usuário.

---

## 💡 Por que eu fiz este projeto? (Motivação e Aprendizado)

Embora os conceitos de Classes e Objetos pareçam simples na teoria, o verdadeiro desafio do backend é **fazer os objetos interagirem entre si com segurança e performance**. Eu desenvolvi este projeto para consolidar três pilares principais:

### 1. Domínio dos Pilares de POO na Prática
* **Abstração:** Criei uma classe mãe chamada `Conteudo`. Ela não pode ser instanciada diretamente (é abstrata), servindo apenas como o molde perfeito para o que é um curso ou uma mentoria.
* **Polimorfismo:** O método `calcularXp()` nasce na classe abstrata, mas se comporta de forma diferente em cada filha. O `Curso` multiplica o XP pela carga horária, enquanto a `Mentoria` soma um bônus fixo. O sistema chama o mesmo método, mas o Java decide o cálculo correto em tempo de execução.

### 2. Uso Estratégico de Collections (`LinkedHashSet`)
Uma das maiores decisões de design desse projeto foi a escolha da estrutura de dados para listar os cursos e os devs. Em vez de usar um `ArrayList` comum, utilizei o `LinkedHashSet`:
* **Por que `Set`?** Porque um aluno não pode se inscrever duas vezes no mesmo curso e o bootcamp não pode ter alunos duplicados. O `Set` barra duplicidade automaticamente.
* **Por que o `Linked`?** Um `HashSet` comum bagunça a ordem dos elementos. O `LinkedHashSet` garante que a ordem em que os cursos foram cadastrados seja mantida, respeitando a cronologia da trilha de estudos.

---

## 🛠️ Tecnologias Utilizadas

* **Linguagem:** Java 17 (ou superior)
* **Paradigma:** Programação Orientada a Objetos (POO)
* **Estruturas de Dados:** Java Collections API (`Set`, `LinkedHashSet`)
* **IDE Recomendada:** IntelliJ IDEA / Eclipse

---

## 🚀 Como Baixar e Executar o Projeto

Se você quiser testar o projeto localmente na sua máquina, siga os passos abaixo:

### Pró-requisitos
Você vai precisar do **JDK (Java Development Kit) 17** ou superior instalado e configurado nas suas variáveis de ambiente.

### 1. Clonar o Repositório
Abra o seu terminal ou prompt de comando e execute:
```bash
git clone [https://github.com/seu-usuario/nome-do-seu-repositorio.git](https://github.com/seu-usuario/nome-do-seu-repositorio.git)
