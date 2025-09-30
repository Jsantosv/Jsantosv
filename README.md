#include <stdio.h>   // Biblioteca para entrada e saída padrão (printf, scanf)
#include <string.h>  // Biblioteca para manipulação de strings (strcpy)
#include <ctype.h>   // Biblioteca para funções de caracteres (toupper)

int main() {
    
    // ---- Declaração de Variáveis ----
    // Conforme solicitado, todas as variáveis são declaradas no início.
    // Em C, isso é obrigatório.

    // Variáveis para os dados de UM produto. Elas serão reutilizadas dentro do loop.
    char nome[50];          // Array de 50 caracteres para armazenar o nome do produto.
    double preco_anterior;  // 'double' é o tipo para números reais de alta precisão.
    double preco_atual;

    // Variáveis para os cálculos e classificação
    double variacao;
    char situacao[10];      // Array de caracteres para "AUMENTO", "QUEDA" ou "ESTÁVEL".

    // Loop 'for' para repetir o processo para 3 produtos.
    for (int i = 0; i < 3; i++) {
        
        printf("\n--- INSERINDO DADOS DO PRODUTO %d ---\n", i + 1);

        // ---- Leitura dos Dados do Produto ----
        
        // Leitura do nome
        printf("Digite o nome do produto: ");
        // Usamos " %[^\n]" para ler uma linha inteira, incluindo espaços.
        // O espaço antes de '%' limpa qualquer caractere de nova linha pendente no buffer.
        scanf(" %[^\n]", nome);

        // Leitura do preço anterior
        printf("Digite o preço ANTERIOR de '%s': ", nome);
        // Usamos "%lf" (long float) para ler um valor do tipo 'double'.
        scanf("%lf", &preco_anterior);

        // Leitura do preço atual
        printf("Digite o preço ATUAL de '%s': ", nome);
        scanf("%lf", &preco_atual);
        
        // ---- Lógica de Cálculo e Classificação ----
        
        // Tratamento para evitar divisão por zero
        if (preco_anterior > 0) {
            // Fórmula da variação percentual
            variacao = ((preco_atual - preco_anterior) / preco_anterior) * 100.0;
        } else if (preco_atual > 0 && preco_anterior == 0) {
            variacao = 100.0;
        } else {
            variacao = 0.0;
        }

        // Classificando a situação com base na variação
        if (variacao > 0) {
            // Em C, para atribuir um valor a uma string, usamos strcpy (string copy)
            strcpy(situacao, "AUMENTO");
        } else if (variacao < 0) {
            strcpy(situacao, "QUEDA");
        } else {
            strcpy(situacao, "ESTÁVEL");
        }

        // ---- Exibição dos Resultados para o Produto Atual ----

        // Bloco para deixar o nome do produto em maiúsculas para exibição
        char nome_maiusculo[50];
        strcpy(nome_maiusculo, nome);
        for(int j = 0; nome_maiusculo[j]; j++){
          nome_maiusculo[j] = toupper(nome_maiusculo[j]);
        }

        printf("\n--- ANÁLISE DO PRODUTO: %s ---\n", nome_maiusculo);
        // "%.2f" formata o número para exibir sempre duas casas decimais.
        printf("Preço Anterior: R$ %.2f\n", preco_anterior);
        printf("Preço Atual:     R$ %.2f\n", preco_atual);
        // Para imprimir um caractere '%' literal, precisamos escrever '%%'.
        printf("Variação Percentual: %.2f%%\n", variacao);
        printf("Situação: %s\n", situacao);
        printf("----------------------------------------\n");
    }

    printf("\nAnálise dos 3 produtos concluída!\n");

    return 0; // Indica que o programa terminou com sucesso.
}
Como Compilar e Executar o Código
Salve o código em um arquivo com a extensão .c, por exemplo, produtos.c.
Abra um terminal ou prompt de comando.
Use um compilador C (como o GCC, que é o mais comum) para compilar o arquivo:
gcc produtos.c -o produtos
Execute o programa gerado:
No Windows: produtos.exe
No Linux ou macOS: ./produtos
crie um Readme para um perfil no github de alguem que esta em fase inicial de aprendizagem com o foco em python

Raciocínio
Abrir para mostrar as sugestões resumidas do modelo
Excelente ideia! Um bom perfil no GitHub é um cartão de visitas fundamental, mesmo (e especialmente) para quem está começando. Ele mostra iniciativa, organização e paixão pelo aprendizado.

Aqui está um modelo de README.md completo, projetado especificamente para um iniciante com foco em Python. Ele é escrito em português, é convidativo, honesto sobre o nível de habilidade e fácil de personalizar.

Como Usar Este Modelo
Crie um repositório especial: No GitHub, crie um novo repositório com o mesmo nome do seu nome de usuário. Por exemplo, se seu usuário for ana-silva, o repositório deve se chamar ana-silva.
Marque a opção "Initialize this repository with a README".
Copie e cole o código abaixo no arquivo README.md que foi criado.
Personalize as seções marcadas com [SUAS INFORMAÇÕES].
Código do README.md (Copie e Cole no seu Perfil)
### Olá, Mundo! 👋 Eu sou [Seu Nome]

<br>

Sou um entusiasta de tecnologia e estou no início da minha jornada no mundo do desenvolvimento de software, com um foco especial em **Python**. 🐍

Atualmente, estou imerso em estudos para construir uma base sólida em lógica de programação, estruturas de dados e boas práticas de desenvolvimento. Acredito que a melhor forma de aprender é colocando a mão na massa, por isso você encontrará aqui alguns dos meus primeiros projetos, exercícios e anotações de estudo.

- 🔭 Estou atualmente trabalhando em... projetos pessoais para praticar Python.
- 🌱 Estou aprendendo... **Python, Git, Lógica de Programação e Estruturas de Dados**.
- 🤔 Estou procurando ajuda com... dicas de projetos para iniciantes e melhores práticas.
- 📫 Como me encontrar: [Seu LinkedIn (opcional)] ou pelo e-mail [seu.email@exemplo.com].
- 😄 Pronomes: [Ele/Dele, Ela/Dela, etc.]

<br>

---

### 📚 O que estou aprendendo

Aqui estão algumas das tecnologias e conceitos nos quais estou focando meus estudos agora:

| Linguagem | Ferramentas | Próximos Passos |
| :---: | :---: | :---: |
| ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) | ![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white) <br> ![VScode](https://img.shields.io/badge/VScode-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white) | ![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white) <br> ![Pandas](https://img.shields.io/badge/Pandas-2C2D72?style=for-the-badge&logo=pandas&logoColor=white) |

<br>

---

### 🚀 Meus Projetos em Destaque

Estes são alguns dos projetos que desenvolvi para praticar. São simples, mas representam passos importantes no meu aprendizado!

*(Dica: Para destacar projetos, vá até a página principal do seu perfil, clique em "Customize your pins" e selecione os repositórios que deseja mostrar).*

1.  **[Nome do Projeto 1](link-para-o-repositório)**
    -   **Descrição:** Uma breve descrição do que o projeto faz (ex: "Um script que automatiza a organização de arquivos em pastas").
    -   **Tecnologias:** Python.

2.  **[Nome do Projeto 2](link-para-o-repositório)**
    -   **Descrição:** (ex: "Calculadora simples com interface de linha de comando para praticar funções e lógica").
    -   **Tecnologias:** Python.

<br>

---

### 📊 Minhas Estatísticas no GitHub

<p align="center">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=[SEU-USUARIO-DO-GITHUB]&show_icons=true&theme=dracula&include_all_commits=true&count_private=true"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=[SEU-USUARIO-DO-GITHUB]&layout=compact&langs_count=7&theme=dracula"/>
</p>

<br>

---

### 📫 Conecte-se comigo!

Estou sempre aberto a dicas, sugestões e a me conectar com outros desenvolvedores. Vamos aprender juntos!

<p align="left">
<a href="mailto:[seu.email@exemplo.com]"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"></a>
<a href="[LINK-DO-SEU-PERFIL-NO-LINKEDIN]" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
</p>

<!--
**Jsantosv/Jsantosv** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
