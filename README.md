# Jarvis: Um assistente de voz utilizando Google GenerativeAI

Este repositório contém o código-fonte para um assistente de voz chamado Jarvis, construído com o Google GenerativeAI e bibliotecas Colab. O Jarvis é capaz de converter texto em fala, realizar gravações de áudio e responder a perguntas utilizando o modelo de linguagem generativa Gemini-1.5-pro-latest.

## Instalação

1. **Instale as dependências:**

   ```bash
   !pip install -q -U google-generativeai
   !pip install gtts
   ```

## Bibliotecas Utilizadas

O Jarvis utiliza as seguintes bibliotecas:

* `IPython.display`: usada para exibir elementos HTML e Javascript no Colab.
* `google.colab.output`: usada para avaliar código Javascript no Colab.
* `gtts`: usada para converter texto em fala (Text-to-Speech).
* `base64`: usada para codificação e decodificação de dados binários.
* `google.generativeai`: usada para interagir com a API do Google GenerativeAI.

## Funções do Código

* **`text_to_speech(text)`:** Converte texto em fala (Português) e reproduz o áudio.
* **`gravacao()`:** Cria um botão de gravação, captura o áudio do usuário e salva-o como um arquivo `.wav`.
* **`audio_prompt()`:** Envia o áudio gravado para o modelo Gemini e retorna a resposta do modelo como texto.

## Configuração da API

1. **Crie uma conta do Google Cloud** ([https://cloud.google.com/](https://cloud.google.com/)) e habilite a API do GenerativeAI.
2. **Obtenha a sua chave de API** e armazene-a com segurança usando `google.colab.userdata.set('API_KEY', 'sua-chave-api')`.

## Configuração do Modelo

* **`generation_config`:** Define o número de candidatos de resposta (1) e a temperatura (0.5).
* **`safety_settings`:** Define o nível de bloqueio para diferentes tipos de conteúdo prejudicial.
* **`model`:** Inicializa o modelo Gemini-1.5-pro-latest com a configuração de geração e os ajustes de segurança.

## Loop de Conversação

O código implementa um loop que permite a conversação com o Jarvis. O loop funciona da seguinte maneira:

1. O usuário grava um áudio.
2. O áudio gravado é enviado para o modelo Gemini.
3. O modelo retorna uma resposta textual.
4. A resposta textual é convertida em fala e reproduzida para o usuário.
5. O loop continua até que o usuário diga "fim".

## Executando o Código

1. **Faça upload do código para o Colab** ([https://colab.research.google.com/notebook](https://colab.research.google.com/notebook)).
2. **Substitua `'sua-chave-api'`** pela sua chave de API real.
3. **Execute o código** pressionando `Shift + Enter`.
4. **Clique no botão "Start Recording"** para gravar sua pergunta.
5. **Fale sua pergunta** e clique em "Stop Recording" quando terminar.
6. O Jarvis irá responder à sua pergunta por voz.

## Licença

GPL v3
