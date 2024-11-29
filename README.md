# 💱 Currency Converter - Aplicativo de Conversão de Moedas

**Projeto Android Nativo com Integração à API de Conversão de Moedas**

---

## 📝 Descrição do Projeto

O **Currency Converter** é um aplicativo Android nativo que permite aos usuários converter valores entre diferentes moedas utilizando uma API de conversão de moedas. O app oferece uma interface simples, onde o usuário pode selecionar moedas, inserir valores e obter o resultado instantaneamente.

---

## 📱 Telas do Aplicativo

### 1. Tela Principal

![image](https://github.com/user-attachments/assets/10a67e4a-8c69-4bb7-94ec-917ef3ec7c08)

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

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: Java (Android Nativo) ☕  
- **Plataforma**: Android 🤖  
- **Integração API**: Retrofit e API de Conversão de Moedas 🌐  
- **Biblioteca JSON**: Gson para manipulação dos dados retornados pela API  
- **IDE**: Android Studio 🛠️  

---

## 📄 Estrutura Explicativa

### 1. Descrição da API

A API utilizada fornece taxas de câmbio atualizadas entre diversas moedas. O objetivo principal é permitir a conversão de valores com base em uma moeda de origem para uma moeda de destino.

### 2. URL Base e Endpoints

- **URL Base:** `https://api.exchangerate-api.com/v4/latest/`
- **Endpoints principais:**
  - `/USD` - Retorna as taxas de câmbio com o dólar americano como referência.
  - Exemplos de dados retornados:
    ```json
    {
      "base": "USD",
      "rates": {
        "BRL": 5.22,
        "EUR": 0.85,
        "JPY": 110.65
      }
    }
    ```

### 3. Autenticação

A API não requer autenticação, permitindo acesso direto às taxas de câmbio. Para APIs que exigem autenticação, seria necessário registrar-se no serviço e configurar uma chave de acesso no código.

### 4. Passo a Passo de Implementação

#### Configuração do Retrofit e Gson

1. **Adicionar as dependências no arquivo `build.gradle`:**
   ```gradle
   implementation 'com.squareup.retrofit2:retrofit:2.9.0'
   implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
   ```
2. **Criar a interface para os Endpoints:**
   ```java
   public interface CurrencyApi {
       @GET("{base}")
       Call<CurrencyResponse> getExchangeRates(@Path("base") String base);
   }
   ```
3. **Configurar o Retrofit no código:**
   ```java
   Retrofit retrofit = new Retrofit.Builder()
       .baseUrl("https://api.exchangerate-api.com/v4/latest/")
       .addConverterFactory(GsonConverterFactory.create())
       .build();

   CurrencyApi api = retrofit.create(CurrencyApi.class);
   ```

#### Realizar Requisição e Exibir Resultados

1. **Fazer a requisição:**
   ```java
   Call<CurrencyResponse> call = api.getExchangeRates("USD");
   call.enqueue(new Callback<CurrencyResponse>() {
       @Override
       public void onResponse(Call<CurrencyResponse> call, Response<CurrencyResponse> response) {
           if (response.isSuccessful() && response.body() != null) {
               double rate = response.body().getRates().get("BRL");
               // Atualizar UI com o valor convertido
           }
       }

       @Override
       public void onFailure(Call<CurrencyResponse> call, Throwable t) {
           // Tratar erro
       }
   });
   ```
2. **Exemplo de classe de modelo para os dados JSON:**
   ```java
   public class CurrencyResponse {
       private String base;
       private Map<String, Double> rates;

       public Map<String, Double> getRates() {
           return rates;
       }
   }
   ```

#### Atualizar o Layout

1. **Adicionar um botão de conversão e exibir o resultado:**
   - Use componentes como `EditText` para entrada de valores e `TextView` para exibição do resultado.
2. **Integração do resultado com a interface:**
   ```java
   double convertedValue = value * rate; // Cálculo da conversão
   resultTextView.setText(String.format("%.2f", convertedValue));
   ```

### 5. Testes e Resultados

#### Exemplos de Testes Realizados:
- **Teste 1:** Conversão de 100 USD para BRL. Resultado esperado: 522 BRL (com taxa fictícia de 5.22).  
- **Teste 2:** Alteração de moeda base e destino, verificando a atualização correta dos valores.  
- **Teste 3:** Mensagem de erro exibida corretamente ao perder a conexão com a API.  

---

## 🌟 Pontos Fortes

- **Integração com API Externa:** O app utiliza uma API real para fornecer taxas de câmbio atualizadas.  
- **Interface Simples:** Layout direto e funcional, permitindo conversões rápidas.  
- **Uso de Retrofit e Gson:** Boa prática no consumo de APIs e manipulação de dados.  

---

## 🛠️ Sugestões de Melhorias Futuras

1. **🛡️ Validação de Entradas:** Garantir que o valor inserido seja numérico e maior que zero.  
2. **📈 Histórico de Conversões:** Permitir que o usuário visualize as conversões realizadas recentemente.  
3. **📱 Suporte Offline:** Implementar cache para taxas de câmbio para permitir o uso do app sem conexão à internet.  
4. **🌐 Suporte a Mais Moedas:** Expandir para incluir mais opções de moedas e exibir suas bandeiras para melhor identificação.  

---

**Desenvolvido  por Fabio Souza**
