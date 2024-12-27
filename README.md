# nlp-text-speech
# Sistema de Assistência Virtual com PLN e Áudio

Este projeto implementa um sistema de assistência virtual que utiliza técnicas de **Processamento de Linguagem Natural (PLN)** e áudio para interagir com o usuário por meio de comandos de voz. A seguir, apresentamos uma explicação detalhada, ideal para quem é iniciante no assunto.

---

## **Objetivo Geral**

O sistema de assistência virtual foi projetado para realizar as seguintes funções:

1. **Text-to-Speech (Texto para fala)**: Converter texto em áudio.
2. **Speech-to-Text (Fala para texto)**: Capturar e transcrever áudio (voz) em texto.
3. **Execução de Comandos por Voz**: Responder a comandos e realizar ações automatizadas, como:
   - Pesquisar informações no Wikipedia.
   - Abrir resultados no YouTube.
   - Contar piadas.
   - Mostrar a hora atual.
   - Reproduzir músicas.

---

## **Componentes do Sistema**

### **1. Text-to-Speech (Texto para fala)**

**Biblioteca usada**: `gTTS` (Google Text-to-Speech).

#### **O que faz?**
Converte texto em áudio para que o sistema possa "falar" com o usuário.

#### **Como funciona?**
1. Define o texto que será falado e o idioma.
2. Usa a biblioteca `gTTS` para processar o texto e gerar um arquivo de áudio.
3. Salva o arquivo de áudio e o reproduz.

#### **Exemplo no Código:**
- O texto **"Hello world"** é convertido em áudio no idioma inglês.
- Outra frase em francês, **"Je vais au supermarché"**, é convertida em áudio.
- Uma frase em português também é transformada: **"Senhorita, só passamos para te lembrar que: Você combinou realizar aquela tarefa!"**.

Esses arquivos de áudio podem ser reproduzidos diretamente pelo sistema.

---

### **2. Speech-to-Text (Fala para texto)**

**Biblioteca usada**: `SpeechRecognition`.

#### **O que faz?**
Captura a voz do usuário através do microfone, converte o áudio em texto e exibe o resultado na tela.

#### **Como funciona?**
1. Usa a função `get_audio()` para capturar o áudio do microfone.
2. Ajusta automaticamente o nível de ruído ambiente para melhorar o reconhecimento.
3. Usa o serviço do Google Speech Recognition para transcrever a fala.
4. Retorna o texto reconhecido ou informa se não foi possível entender a entrada.

---

### **3. Execução de Comandos por Voz**

**Função principal**: `respond(text)`.

#### **Como funciona?**
Essa função recebe o texto transcrito da fala do usuário e executa ações específicas com base no comando reconhecido.

#### **Comandos Suportados:**
- **Pesquisar no YouTube**:
  - A assistente pergunta o que você deseja procurar.
  - Realiza a busca no YouTube e abre os resultados no navegador.

- **Pesquisar no Wikipedia**:
  - Pergunta o que você quer buscar.
  - Lê um resumo de 3 frases sobre o tema pesquisado.

- **Contar uma piada**:
  - Gera uma piada em inglês usando a biblioteca `pyjokes`.

- **Informar a hora atual**:
  - Converte a hora para um formato amigável e fala para o usuário.

- **Reproduzir música**:
  - Busca músicas em uma pasta especificada e toca a primeira música encontrada.

- **Parar música**:
  - Interrompe a reprodução de áudio.

- **Sair do programa**:
  - Encerra a assistente.

#### **Exemplo Prático**
1. **Você fala**: "What time is it?"
   - A assistente responde com o horário atual em áudio.

2. **Você fala**: "Search Python programming on Wikipedia."
   - A assistente abre uma aba no navegador com o resultado da busca e lê um resumo do artigo.

---

### **4. Bibliotecas Auxiliares**

O sistema utiliza várias bibliotecas para facilitar a implementação das funcionalidades:

- **`playsound`**: Reproduz arquivos de áudio.
- **`mixer` (do pygame)**: Gerencia a reprodução de músicas.
- **`webbrowser`**: Abre URLs em um navegador, como buscas no YouTube ou Wikipedia.
- **`pyjokes`**: Gera piadas em inglês.
- **`wikipedia`**: Realiza buscas e retorna resumos de artigos.
- **`os`**: Gerencia arquivos e operações no sistema.

---

## **Fluxo Completo do Sistema**

1. **Inicialização**:
   - Configura o microfone e o reconhecedor de voz.

2. **Entrada de Voz**:
   - Usa a função `get_audio()` para capturar a fala do usuário.

3. **Interpretação do Comando**:
   - O texto transcrito é passado para a função `respond(text)`, que identifica e executa a ação correspondente.

4. **Fala e Resposta**:
   - A assistente responde usando áudio gerado pela função `speak()`.

---

## **Conclusão**

Este sistema é um exemplo prático de como integrar Processamento de Linguagem Natural e reconhecimento de fala em um projeto de assistência virtual. Ele é capaz de interagir com o usuário de maneira natural, automatizando tarefas cotidianas de forma eficiente.
