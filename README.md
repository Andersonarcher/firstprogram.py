Este código é um programa que valida e consulta CPFs no site Jusbrasil para verificar se há processos associados a esse CPF. Aqui está o que ele faz, passo a passo:

### 1. **Função de Validação do CPF (`validar_cpf`)**
   - **Objetivo**: Verificar se o CPF informado é válido.
   - **Como funciona**: 
     - O código remove pontos e hífens do CPF para garantir que ele seja apenas números.
     - Em seguida, verifica se o CPF tem exatamente 11 dígitos e se são números (usando `isdigit()`).
     - Após isso, aplica um algoritmo matemático de validação (cálculo dos dois últimos dígitos verificadores do CPF) para checar se o CPF está corretamente formado.
   - **Resultado**: Retorna `True` se o CPF for válido, e `False` se for inválido.

### 2. **Função de Consulta do CPF no Jusbrasil (`consultar_cpf`)**
   - **Objetivo**: Consultar no site Jusbrasil se há processos relacionados ao CPF.
   - **Como funciona**: 
     - Cria uma URL de consulta no Jusbrasil utilizando o CPF informado.
     - Faz uma requisição HTTP para essa URL e verifica o conteúdo da resposta. Se o site retornar a mensagem "nenhum resultado encontrado", significa que não há processos relacionados ao CPF.
     - Caso contrário, o CPF tem processos associados.
   - **Resultado**: Retorna uma mensagem como "Sem processos" ou "Com processos", ou ainda "Erro na consulta" se ocorrer algum problema ao acessar o site.

### 3. **Função Principal (`main`)**
   - **Objetivo**: Controlar o fluxo do programa.
   - **Como funciona**:
     - Exibe um menu inicial pedindo ao usuário para digitar um CPF ou "sair" para encerrar.
     - Valida o CPF utilizando a função `validar_cpf`. Se o CPF for inválido, ele informa ao usuário e pede um novo CPF.
     - Se o CPF for válido, o programa gera a URL de consulta no Jusbrasil e a exibe.
     - Chama a função `consultar_cpf` para verificar se há processos relacionados ao CPF e exibe o resultado.
     - Abre a URL do Jusbrasil no navegador automaticamente.
     - O processo se repete até o usuário digitar "sair".

### 4. **Comportamento Interativo**
   - O programa executa no terminal (linha de comando) e pede que o usuário insira um CPF para verificar.
   - O programa informa se o CPF é válido ou inválido e, se válido, verifica no Jusbrasil se há processos associados.
   - Se o usuário quiser encerrar, pode digitar "sair".

### Exemplificação do Fluxo:
   1. O usuário digita um CPF.
   2. O sistema valida o CPF. Se inválido, informa o erro.
   3. Se válido, ele consulta a base de dados do Jusbrasil e retorna o status ("Sem processos" ou "Com processos").
   4. O sistema então abre a URL da consulta no navegador.

### Detalhes Importantes:
   - **Validação do CPF**: A função aplica uma fórmula matemática que verifica a integridade do CPF.
   - **Consulta no Jusbrasil**: O Jusbrasil é consultado via uma busca simples, e o sistema retorna se o CPF tem ou não processos.

Essa explicação pode ajudar seu chefe a entender como o programa pode ser usado para verificar rapidamente a validade de CPFs e se há registros de processos vinculados a eles.
