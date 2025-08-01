<h1 align="center">Monitoramento com Prometheus e Grafana 📊</h1>
<div align="center">
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white" />
  <img src="https://img.shields.io/badge/Grafana-F46800?style=flat&logo=grafana&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2CA5E0?style=flat&logo=docker&logoColor=white" />
</div>

<div align="left">
  <h3>📖 Descrição</h3>

  <p>
    Este projeto configura um ambiente completo de monitoramento utilizando <strong>Prometheus</strong> para coleta de
    métricas e <strong>Grafana</strong> para visualização dos dados.
  </p>

  <p>
    A solução é ideal para monitorar aplicações Spring Boot que expõem métricas no formato Prometheus através do
    endpoint <code>/actuator/prometheus</code>, proporcionando insights valiosos sobre o desempenho e saúde da
    aplicação.
  </p>
</div>

<div align="left">
  <h3>🛠️ Tecnologias Utilizadas</h3>

  <ul>
    <li><strong>Prometheus</strong> – Coleta e armazena métricas temporais</li>
    <li><strong>Grafana</strong> – Plataforma de visualização e análise de dados</li>
    <li><strong>Docker</strong> – Conteinerização dos serviços</li>
    <li><strong>Docker Compose</strong> – Orquestração dos containers</li>
  </ul>
</div>

<div align="left">
  <h3>🚀 Como Executar</h3>

  <h4>🔧 Pré-requisitos</h4>
  <ul>
    <li>Docker e Docker Compose instalados</li>
    <li>Aplicação Spring Boot com actuator/prometheus habilitado</li>
  </ul>

  <h4>▶️ Execução com Docker Compose</h4>

  ```bash
  # 1. Clone o repositório
  git clone https://github.com/Robson-Carvalho/monitoring-prometheus-grafana

  cd monitoring-prometheus-grafana

  # 2. Suba os containers
  docker-compose up -d
  ```

  <h4>⚙️ Configuração do Prometheus</h4> Edite o arquivo <code>prometheus/prometheus.yml</code> para apontar para sua
  aplicação:

  ```yml
  scrape_configs:
  - job_name: "Metrics"
  metrics_path: "/actuator/prometheus"
  scrape_interval: 3s
  static_configs:
  - targets: ["spring-boot:8080"] # Altere para seu endereço de aplicação
  labels:
  application: "Application"
  ```

  <h4>🌐 Acesso aos Serviços</h4>
  <ul>
    <li><strong>Prometheus:</strong> http://localhost:9090</li>
    <li><strong>Grafana:</strong> http://localhost:3000 (usuário/senha: admin/admin)</li>
  </ul>
</div>
<div align="left">
  <h3>📁 Estrutura do Projeto</h3>
  <ul>
    <li><code>prometheus/</code>: Configurações e arquivos do Prometheus</li>
    <li><code>grafana/</code>: Configurações e dashboards do Grafana</li>
    <li><code>docker-compose.yml</code>: Definição dos serviços</li>
  </ul>
</div>
<div align="left">
  <h3>🔍 Fluxo de Monitoramento</h3>
  <ol>
    <li>Aplicação expõe métricas no endpoint <code>/actuator/prometheus</code></li>
    <li>Prometheus coleta as métricas periodicamente</li>
    <li>Grafana visualiza os dados armazenados no Prometheus</li>
    <li>Dashboards fornecem insights em tempo real</li>
  </ol>
</div>
<div align="left">
  <h3>🤝 Contribuindo</h3>
  <ol>
    <li>Faça um fork do projeto</li>
    <li>Crie uma branch para sua feature (<code>git checkout -b feature/nova-feature</code>)</li>
    <li>Commit suas alterações (<code>git commit -m 'feat: nova funcionalidade'</code>)</li>
    <li>Dê push na sua branch (<code>git push origin feature/nova-feature</code>)</li>
    <li>Abra um Pull Request</li>
  </ol>
</div>
<div align="left">
  <h3>🐛 Problemas?</h3>
  <p> Se você encontrar algum problema ou tiver sugestões de melhoria, sinta-se à vontade para abrir uma <a
      href="https://github.com/robson-carvalho/monitoring-prometheus-grafana/issues"><strong>issue</strong></a>. </p>
</div>
<div align="left">
  <h3>📜 Licença</h3>
  <p>Distribuído sob a licença MIT. Consulte o arquivo <a href="./LICENSE"><strong>LICENSE</strong></a> para mais
    detalhes.</p>
</div>