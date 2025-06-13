# 🩺 Pulseira IoT para Monitoramento de Sinais Vitais Pediátricos

VitalCare – Sistema Inteligente de Monitoramento de Sinais Vitais em Tempo Real

## 🎯 Objetivo

Desenvolver uma solução completa baseada em IoT para o monitoramento contínuo de sinais vitais de pacientes pediátricos. A solução permite a coleta de dados por sensores embarcados em uma pulseira, envio das informações via protocolo MQTT para um back-end em nuvem, e visualização em tempo real por meio de um dashboard acessível a médicos e enfermeiros.

O sistema tem como foco principal aumentar a segurança clínica, otimizar o tempo de resposta médica e humanizar o cuidado infantil.

## 🧑‍⚕️ Público-alvo

- Hospitais e clínicas pediátricas
- Equipes médicas e de enfermagem
- Instituições de pesquisa em saúde
- Startups e empresas da área de saúde digital

## 💡 Problema que o Projeto Resolve

Em hospitais com alta demanda, o monitoramento constante de sinais vitais é um desafio. Equipamentos tradicionais são caros, desconfortáveis para crianças e nem sempre fornecem alertas em tempo real. Além disso, a sobrecarga das equipes pode comprometer a qualidade do atendimento.

O projeto resolve esse problema ao oferecer:
- Um dispositivo portátil e confortável
- Coleta contínua de dados vitais como temperatura, oxigenação, batimentos cardíacos
- Envio automático dos dados à nuvem com alertas inteligentes
- Dashboard acessível para facilitar a análise médica
- Sistema de baixo custo, escalável e pronto para ser integrado à rotina hospitalar

---

## 🧩 Principais Componentes do Projeto

A arquitetura da solução é dividida em três camadas principais: IoT, Back-End e Aplicação. Abaixo, listamos os componentes de cada camada e suas respectivas funções:

### 🟦 1. **Camada IoT – Microcontroladores, Sensores e Atuadores**
- **ESP32:** Microcontrolador responsável por ler os sensores e enviar os dados via Wi-Fi utilizando o protocolo MQTT.
- **Sensor de Temperatura (DHT11 ou DHT22):** Captura a temperatura corporal do paciente em tempo real.
- **Sensor de Batimentos Cardíacos / Oxímetro (simulado):** Mede a frequência cardíaca e a oxigenação do sangue.

### 🟨 2. **Camada Back-End – Plataforma de IoT e Processamento**
- **Broker MQTT (Mosquitto):** Responsável por intermediar a comunicação entre o ESP32 (IoT) e o servidor, recebendo e encaminhando mensagens dos sensores.
- **Servidor Node.js:** Recebe os dados dos sensores via MQTT, processa as informações, armazena no banco de dados e envia para o front-end via WebSocket.
- **WebSocket:** Permite a comunicação em tempo real entre o servidor e o dashboard, mantendo os dados sempre atualizados.
- **Banco de Dados MongoDB (Atlas):** Armazena os dados coletados dos sensores para histórico, análise e emissão de alertas futuros.

### 🟩 3. **Camada de Aplicação – Dashboard e Visualização**
- **Dashboard Web (React.js + Tailwind CSS):**: Interface que permite a visualização em tempo real dos sinais vitais através de gráficos e indicadores.
- **Gráficos Recharts:** Exibem os dados dos sensores de forma visual e intuitiva, com tooltips, escalas claras e legendas.
- **Responsividade:** O front-end é responsivo, podendo ser acessado em tablets, celulares ou computadores, facilitando o uso pela equipe médica em diferentes contextos.
- **Hospedagem Front-End: Vercel:** O dashboard está hospedado na plataforma Vercel, garantindo disponibilidade e acesso remoto.
- **Hospedagem Back-End: Render:** O servidor Node.js está hospedado na Render, garantindo conectividade com a nuvem e com os dispositivos IoT.

---

## 🗂️ Descrição do Diagrama em Camadas
O diagrama da arquitetura da solução está dividido em três camadas principais: IoT, Back-End e Aplicação (Front-End). A seguir, explicamos o fluxo de dados e o papel de cada componente envolvido:
1. O ESP32 lê os sensores e envia os dados via MQTT ao broker.
2. O servidor Node.js escuta os tópicos MQTT, processa os dados e os armazena no MongoDB.
3. Ao mesmo tempo, o servidor envia os dados via WebSocket ao front-end.
4. O dashboard exibe as informações em tempo real e emite alertas se necessário.

---

## 🧠 Diagrama da Arquitetura

🔗 O diagrama em camadas foi desenvolvido no [draw.io](https://app.diagrams.net/) e está salvo no arquivo VitalCare.drawio.

### 🖼 Descrição do Diagrama

1. **Paciente**: Fonte dos sinais vitais.
2. **Sensores (MAX30100 e MLX90614)**: Realizam a coleta de batimentos, oxigenação e temperatura.
3. **ESP32**: Envia os dados via Wi-Fi para o servidor.
4. **Servidor**: Recebe os dados, processa e salva no banco.
5. **Dashboard**: Visualização pelos médicos e enfermeiros.
6. **Usuários**: Profissionais de saúde têm acesso.

---

## 🧪 Como Rodar o Projeto - Siga todos os passos para ter a aplicação completa

1. Acesse e rode o projeto no Wokwi: 👉 [https://wokwi.com/projects/429772766362621953](https://wokwi.com/projects/429772766362621953)
2. Acesse: [https://backend-vitalcare.onrender.com/](https://backend-vitalcare.onrender.com/) para rodar o backend em produção
3. Acesse: [https://sprint4-web-two.vercel.app](https://sprint4-web-two.vercel.app) para acessar o frontend
4. Faça o login na plataforma
```admin@vitalcare.com``` 
```password123``` 

- Link para o projeto backend: [https://github.com/NeriJyu/backend-vitalcare](https://github.com/NeriJyu/backend-vitalcare)
- Link para o projeto frontend: [https://github.com/Gustavo-Meroni/sprint4-web](https://github.com/Gustavo-Meroni/sprint4-web)
---

## 📺 Demonstração em Vídeo

Confira a demonstração do projeto no YouTube:
   👉 [https://youtu.be/rcrYZ053t7M](https://youtu.be/rcrYZ053t7M)

---

## 👥 Equipe

- Diogo Cecchini      RM560427
- Gustavo Neri        RM560239
- Gustavo Pandolfo    RM560271
- Matheus Plati       RM559813


