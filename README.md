# RoteiroApp
## Descrição
* O RoteiroApp é um aplicativo móvel desenvolvido em React Native, projetado para ajudar usuários a criar roteiros de viagens personalizados. Utilizando a API GPT-3.5 Turbo do ChatGPT, o * aplicativo gera roteiros detalhados com base na cidade e no tempo de estadia fornecidos pelo usuário.

## Funcionalidades
* Entrada do Usuário: Permite ao usuário inserir o nome da cidade e o número de dias de estadia.
* Geração de Roteiros: Utiliza a API GPT-3.5 Turbo do ChatGPT para criar roteiros detalhados, destacando os principais pontos turísticos e atividades.
* Interface Amigável: Com componentes modernos de React Native, incluindo react-native-slider para selecionar a duração da estadia e @expo/vector-icons para ícones intuitivos.
* Experiência de Usuário: Interface simples e eficiente, com feedback visual para carregamento e exibição de resultados.
## Consumo de API
* Para gerar os roteiros, o aplicativo faz uma requisição à API GPT-3.5 Turbo do ChatGPT. A chave da API deve ser fornecida e é utilizada para autenticar as requisições.

Exemplo de Requisição javascript

const prompt = `Crie um roteiro para uma viagem de exatos ${days.toFixed(0)} dias na cidade de ${city}, busque por lugares turísticos, lugares mais visitados, seja preciso nos dias de estadia fornecidos e limite o roteiro apenas na cidade fornecida. Forneça apenas em tópicos com nome do local onde ir em cada dia.`;

fetch("https://api.openai.com/v1/chat/completions", 
{
  method: "POST",
  headers: {
  "Content-Type": "application/json",
  Authorization: `Bearer ${KEY_GPT}`
  },
  body: JSON.stringify({
  model: "gpt-3.5-turbo",
  messages: [
  {
  role: 'user',
  content: prompt
  }
  ],
  temperature: 0.20,
  max_tokens: 500,
  top_p: 1,
  })
  })
  
## Navegação
* A navegação entre as telas do aplicativo (Home e Resultado) foi implementada utilizando o pacote react-navigation, proporcionando uma experiência de usuário fluida ao alternar entre a tela inicial, onde se insere a cidade e os dias de estadia, e a tela de resultados, onde é exibido o roteiro gerado.

## Implementação do Código
Arquivos Principais
* App.js: Componente principal que gerencia os estados do aplicativo e a interação do usuário.
* HomeScreen.js: Tela inicial para entrada da cidade e dias de estadia.
* ResultScreen.js: Tela que exibe o roteiro gerado.

## Conclusão
* O RoteiroApp oferece uma solução prática e intuitiva para criar roteiros de viagens personalizados, utilizando tecnologias modernas como React Native e a API GPT-3.5 Turbo do ChatGPT. A interface amigável e a navegação fluida proporcionam uma experiência agradável para os usuários que desejam planejar suas viagens de maneira eficiente e detalhada.
