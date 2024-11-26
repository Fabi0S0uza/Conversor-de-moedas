# 💱 Currency Converter - Aplicativo de Conversão de Moedas

**Projeto Android Nativo com Integração à API de Conversão de Moedas**

## 📝 Descrição do Projeto

O **Currency Converter** é um aplicativo Android nativo que permite aos usuários converter valores entre diferentes moedas utilizando uma API de conversão de moedas. O app oferece uma interface simples, onde o usuário pode selecionar moedas, inserir valores e obter o resultado instantaneamente.

---

## 📱 Telas do Aplicativo

### 1. Tela Principal

![image](https://github.com/user-attachments/assets/10a67e4a-8c69-4bb7-94ec-917ef3ec7c08)


---

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: Java (Android Nativo) ☕  
- **Plataforma**: Android 🤖  
- **Integração API**: Retrofit e API de Conversão de Moedas 🌐  
- **Biblioteca JSON**: Gson para manipulação dos dados retornados pela API  
- **IDE**: Android Studio 🛠️  

---

## 🚀 Funcionalidades

1. **🌎 Conversão de Moedas**  
   - Entrada de valores para conversão.
   - Seleção de moedas de origem e destino.
   - Requisição à API para calcular o valor convertido.

2. **📤 API de Conversão de Moedas**  
   - Consome dados da API para obter taxas de câmbio atualizadas.
   - Manipula respostas JSON de forma eficiente.

3. **💡 Interface Intuitiva**  
   - Layout minimalista e fácil de usar.
   - Resultado da conversão exibido de forma clara.

---

## 📂 Estrutura de Códigos e Classes

1. **MainActivity (Tela Principal)**  
   - **Componentes**: Campos para entrada do valor, dropdowns para selecionar moedas de origem e destino, botão para realizar a conversão e campo para exibir o resultado.
   - **Método**: `convertCurrency`: Faz a requisição à API, processa os dados retornados e exibe o resultado na tela.

2. **RetrofitClient**  
   - Classe para configurar a comunicação com a API utilizando Retrofit.

3. **CurrencyApi**  
   - Interface que define os endpoints da API de conversão.

---

## 🌟 Pontos Fortes

- **Integração com API Externa**: O app utiliza uma API real para fornecer taxas de câmbio atualizadas.  
- **Interface Simples**: Layout direto e funcional, permitindo conversões rápidas.  
- **Uso de Retrofit e Gson**: Boa prática no consumo de APIs e manipulação de dados.  

---

## 🛠️ Sugestões de Melhorias Futuras

1. **🛡️ Validação de Entradas**  
   - Garantir que o valor inserido seja numérico e maior que zero.  

2. **📈 Histórico de Conversões**  
   - Permitir que o usuário visualize as conversões realizadas recentemente.  

3. **📱 Suporte Offline**  
   - Implementar cache para taxas de câmbio para permitir o uso do app sem conexão à internet.  

4. **🌐 Suporte a Mais Moedas**  
   - Expandir para incluir mais opções de moedas e exibir suas bandeiras para melhor identificação.  

---

## 🎯 Conclusão

O Currency Converter é um aplicativo funcional que proporciona uma experiência direta para conversão de moedas. Com uma integração eficiente à API e uma interface amigável, o app é uma ótima ferramenta para quem precisa de conversões rápidas e confiáveis. Com melhorias futuras, ele pode oferecer ainda mais valor aos usuários.
