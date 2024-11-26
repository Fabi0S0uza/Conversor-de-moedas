# 🔐 FireAuth - Aplicativo de Autenticação e Frases Motivacionais

**Projeto Android Nativo com Firebase Authentication e Frases Motivacionais**

## 📝 Descrição do Projeto

FireAuth evoluiu para um aplicativo Android nativo que combina autenticação de usuários usando Firebase Authentication com a exibição de frases motivacionais. Além de gerenciar o login, os usuários podem navegar por diversas frases inspiradoras através de botões "anterior" e "próxima", com uma interface simples e fluida.

## 📱 Telas do Aplicativo

### 1. Tela de Login

![Tela de Login](https://github.com/user-attachments/assets/16807e85-0223-4da5-9523-396de19c3822)

### 2. Tela de Cadastro

![Tela de Cadastro](https://github.com/user-attachments/assets/6fb83654-0814-460f-9eab-da4e3b0abc28)

### 3. Tela de Redefinição de Senha

![Tela de Redefinição de Senha](https://github.com/user-attachments/assets/db18741a-8a4e-4bc7-9a77-48738c5ae436)

### 4. Home do App

![Home do App](https://github.com/user-attachments/assets/a3101d13-28a0-40d1-8733-878c07c73abb)

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: Java (Android Nativo) ☕
- **Plataforma**: Android 🤖
- **Banco de Dados**: Firebase Authentication 🔥
- **IDE**: Android Studio 🛠️

## 🚀 Funcionalidades

1. **🔑 Tela de Login**  
   - Entrada de email e senha.
   - Autenticação via `FirebaseAuth.signInWithEmailAndPassword`.
   - Mensagem de erro exibida em caso de falha.
   - Redirecionamento para a tela de sucesso (`LogadoActivity`) após login bem-sucedido.

2. **📝 Tela de Registro**  
   - Botão para navegação até a tela de registro (`RegisterActivity`).
   - Registro de novos usuários via `FirebaseAuth.createUserWithEmailAndPassword`.
   - Login disponível imediatamente após o registro.

3. **👤 Tela Logado com Frases Motivacionais**  
   - Exibe o email do usuário logado.
   - Apresenta uma frase motivacional inicial, com botões para navegar entre frases.
   - Botão "Próxima": exibe a próxima frase motivacional.
   - Botão "Anterior": exibe a frase anterior.
   - Botão de Logout: desconecta o usuário usando `FirebaseAuth.signOut()` e redireciona para a tela de login.

4. **🚪 Logout**  
   - Opção de logout na `LogadoActivity` para desconectar o usuário.

## 📂 Estrutura de Códigos e Classes

1. **MainActivity (Tela de Login)**  
   - **Componentes**: Campos de entrada (EditText) para email e senha, botão de login e botão para navegar à tela de registro.
   - **Método**: `loginUser`: Autentica o usuário com o Firebase e redireciona após login bem-sucedido.

2. **RegisterActivity (Tela de Registro)**  
   - **Componentes**: Funcionalidade para registrar novos usuários via Firebase. Login habilitado logo após o registro.

3. **LogadoActivity (Tela de Frases Motivacionais)**  
   - **Componentes**: Exibe o email do usuário logado, apresenta frases motivacionais com botões para alternar entre elas, e um botão de Logout.

## 🔥 Firebase Authentication

- **Configuração**: Firebase integrado ao projeto utilizando o arquivo `google-services.json`.
- **Autenticação**: Login e logout implementados com segurança utilizando a API do Firebase Authentication.

## 🌟 Pontos Fortes

- **Integração Simples com Firebase**: A implementação segue boas práticas, garantindo fácil manutenção e entendimento.
- **Navegação Suave**: Alternância eficiente entre as telas de login, registro e frases motivacionais.
- **Gerenciamento de Sessão**: Login e logout funcionam corretamente, mantendo o estado do usuário durante a sessão.
- **Adição de Conteúdo Motivacional**: O app oferece uma experiência interativa, permitindo que o usuário navegue por frases que trazem positividade e motivação.

## 🛠️ Sugestões de Melhorias Futuras

1. **🛡️ Validação de Entradas**: Verificar se o email tem um formato válido e garantir que a senha possua um número mínimo de caracteres.
2. **🔄 Persistência de Sessão**: Verificar se o usuário já está autenticado ao abrir o aplicativo, redirecionando diretamente para a `LogadoActivity` se estiver logado.
3. **⏳ Feedback Visual**: Adicionar um indicador de progresso (como um ProgressBar) durante as operações de login e registro.
4. **📃 Mais Frases Motivacionais**: Adicionar novas frases motivacionais ou permitir que o usuário adicione suas próprias frases para maior personalização.

## 🎯 Conclusão

O FireAuth oferece uma experiência completa e interativa, combinando funcionalidades essenciais de autenticação com o toque positivo das frases motivacionais. A navegação entre as telas é fluida, o gerenciamento de sessão é seguro, e as frases fornecem um toque agradável para os usuários. Com algumas melhorias adicionais, o app pode evoluir ainda mais em termos de experiência do usuário.
