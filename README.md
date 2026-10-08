# Explorando Práticas de Teste

Neste exercício, vamos explorar práticas de teste em sistemas reais utilizando a ferramenta [TestMiner](https://andrehora.github.io/testminer).

O TestMiner permite visualizar e analisar testes de software em repositórios do GitHub, fornecendo dados sobre como os projetos organizam seus testes, como eles evoluem entre versões e quais bibliotecas de teste são utilizadas.
Explore a ferramenta antes de começar para se familiarizar com seu funcionamento.

Mais detalhes no GitHub da ferramenta: https://github.com/andrehora/testminer.

---

## Passo 1: Selecionar DOIS repositórios

Escolha dois repositórios reais que possuam testes de software.
Abaixo estão alguns links para ajudá-lo a encontrar projetos interessantes:

- Python: https://github.com/topics/python?l=python
- JavaScript: https://github.com/topics/javascript?l=javascript
- TypeScript: https://github.com/topics/typescript?l=typescript
- Java: https://github.com/topics/java?l=java

- Tópicos: [ai](https://andrehora.github.io/testminer/#topic:ai), [llm](https://andrehora.github.io/testminer/#topic:llm), [api](https://andrehora.github.io/testminer/#topic:api), [nodejs](https://andrehora.github.io/testminer/#topic:nodejs), [android](https://andrehora.github.io/testminer/#topic:android)

- Por organização: [Google](https://andrehora.github.io/testminer/#google), [Microsoft](https://andrehora.github.io/testminer/#microsoft), [Apple](https://andrehora.github.io/testminer/#apple), [Facebook](https://andrehora.github.io/testminer/#facebook), [Netflix](https://andrehora.github.io/testminer/#netflix), 
[GitHub](https://andrehora.github.io/testminer/#github), [Apache](https://andrehora.github.io/testminer/#apache), [HuggingFace](https://andrehora.github.io/testminer/#huggingface)

## Passo 2: Explorar os repositórios selecionados

Busque os repositórios escolhidos no [TestMiner](https://andrehora.github.io/testminer) e analise os dados de teste gerados pela ferramenta.

## Passo 3: Explicar as prática de teste

Para cada repositório, escolha uma prática ou dado de teste relevante e explique com suas próprias palavras.

---

## Instruções de entrega

1. Faça um `fork` deste repositório (saiba mais sobre forks [aqui](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)).
2. Responda às questões abaixo diretamente neste arquivo `README.md` do seu fork. Pode adicionar imagens para enriquecer sua explicação.
3. No Moodle, submeta apenas a URL do seu fork.

---

## Respostas

### Repositório 1 

Repositório: `https://github.com/n8n-io/n8n`

URL TestMiner: `https://andrehora.github.io/testminer/#n8n-io/n8n`

Explicação: `No repositório do n8n, uma plataforma de automação de workflows, destaca-se a prática de testes de integração baseados em fixtures e mocks de APIs externas, atrelada à divisão arquitetural da suíte de testes em um ambiente monorepo.

Como o n8n interage com centenas de serviços de terceiros (como Slack, GitHub e Google Sheets), a validação de cada "nó" de integração é feita utilizando arquivos de respostas simuladas (fixtures) em vez de realizar chamadas de rede reais durante a execução da suíte. Essa abordagem é crucial para a confiabilidade do processo de integração contínua, pois impede que limitações de taxa de requisição (rate limits), oscilações na conexão ou instabilidades nas APIs externas quebrem os testes de forma falso-positiva.

Além disso, a estrutura de pastas do projeto isola rigidamente os testes do motor central de execução (packages/cli) dos testes focados nas integrações individuais (packages/nodes-base). Isso permite que os mantenedores validem o comportamento do ecossistema central — como o gerenciamento de memória, gatilhos e fila de tarefas — sem a necessidade de rodar exaustivamente a suíte inteira de cada um dos nós disponíveis, otimizando o uso de recursos e acelerando os testes automatizados.`

### Repositório 2

Repositório: `https://github.com/angular/angular`

URL TestMiner: `https://andrehora.github.io/testminer/#angular/angular`

Explicação: `No repositório da framework Angular, uma prática de teste bastante marcante é a co-localização de testes unitários (In-source Testing), combinada a uma separação clara para os testes de integração e ponta a ponta (End-to-End).

A co-localização consiste em manter os arquivos de testes unitários (identificados pela extensão *.spec.ts) no mesmo diretório em que reside o código-fonte correspondente, como posicionar button.component.spec.ts diretamente ao lado de button.component.ts. Essa estratégia traz um ganho significativo na manutenibilidade do projeto: a proximidade física entre o código funcional e suas validações facilita a navegação do desenvolvedor, sinaliza de imediato a ausência de cobertura de testes em um componente e incentiva a atualização constante das suítes sempre que uma alteração é realizada.

Por outro lado, o Angular organiza as suas suítes de testes de integração e E2E em diretórios e pacotes dedicados dentro do monorepo. Como os testes de integração exigem um tempo maior de execução e configurações de ambiente mais pesadas, mantê-los isolados evita que a execução rápida dos testes unitários seja prejudicada, garantindo um ciclo de feedback ágil durante o desenvolvimento diário.`
