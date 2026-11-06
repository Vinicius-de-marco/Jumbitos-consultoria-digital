
🚀 Jumbitos – Cloud & Infra Readiness Advisor — Consultoria em Transformação Digital
🔗 Acesse o Aplicativo Online (GitHub Pages):  https://vinicius-de-marco.github.io/Jumbitos-consultoria-digital/

Simulador de Migração para a Nuvem: diagnostica a infraestrutura de uma empresa, recomenda o modelo de nuvem mais adequado (SaaS, PaaS, IaaS ou Híbrido), calcula o risco operacional da migração e gera um Laudo Técnico com roteiro seguro de migração, pronto para exportar em PDF.

👥 Especialistas Responsáveis (Autores)
Vinicius De Marco Rodrigues
Unidade Curricular: Exploração Digital e Fundamentos Tecnológicos (Objetos de Conhecimento 05 e 06)
🎯 1. O Problema Empresarial e Objetivo do Aplicativo
Muitas pequenas e médias empresas querem migrar para a nuvem, mas não sabem por onde começar. Também não sabem se a infraestrutura atual aguenta a mudança. Servidores antigos, sistemas legados sem suporte, internet sem redundância, dados pessoais sem mapeamento (LGPD) e backups que nunca foram testados fazem uma migração mal planejada virar parada da operação ou perda de dados. O Jumbitos resolve essa dor com um diagnóstico rápido (8 perguntas em cerca de 3 minutos). Ele mede a prontidão da empresa em 4 pilares técnicos (Servidores, Rede, Dados e Backup), indica o nível de risco da migração e recomenda o modelo de nuvem ideal conforme o porte e o setor. Ao final, gera um laudo com boas práticas personalizadas e um roteiro de migração em fases, com prazos. Tudo é processado localmente no navegador, sem enviar nenhum dado a servidores.

Principais funcionalidades
Assistente em 5 etapas (Perfil + 4 pilares), com validação amigável e barra de progresso.
Score Geral de Prontidão (média ponderada) com selo: Crítico, Em Transição, Estruturado ou Líder Digital.
Risco Operacional (Baixo, Moderado, Alto ou Crítico), com peso maior para Backup e Rede e agravantes automáticos.
Modelo de nuvem recomendado com justificativa em texto e a pontuação de aderência de cada modelo.
Gráfico radar (Chart.js) comparando a empresa com o nível ideal.
Plano de Boas Práticas por pilar e Roteiro Seguro de Migração em linha do tempo.
Demo aleatória: cada clique cria uma empresa fictícia diferente, a partir de 8 cenários realistas.
Exportação do laudo em PDF (tema claro de impressão), layout responsivo e tema escuro.
🏛 2. Os 4 Pilares de Boas Práticas Aplicados no Diagnóstico
☁ Infraestrutura e Migração para a Nuvem: é o núcleo do app. As perguntas avaliam a idade do hardware, a virtualização, o link de internet e a redundância, a regra de backup 3-2-1 e as metas de RPO/RTO. A partir das respostas, do porte e do setor, regras de pontuação documentadas no código recomendam SaaS, PaaS, IaaS ou Nuvem Híbrida. Exemplos: legados acoplados favorecem o rehost em IaaS; um ambiente padronizado favorece PaaS; uma microempresa sem equipe de TI favorece SaaS. As recomendações incluem alta disponibilidade (multizona, failover automático, DRaaS), FinOps e a estratégia dos 6 Rs. Quando o risco é Alto ou Crítico, o roteiro inclui uma fase extra de Estabilização antes da migração.

🔄 Sistemas Empresariais (ERP/CRM) e Fluxo de Dados: o diagnóstico identifica a dependência de sistemas legados e as integrações frágeis, como troca de arquivos ou acesso direto ao banco. Para esses casos, recomenda integração ERP ↔ CRM via APIs REST ou plataformas de integração (iPaaS), substituição de ERPs sem suporte por ERP em SaaS e centralização de dados que hoje estão espalhados em PCs, pendrives e planilhas. Nos níveis mais maduros, sugere uma plataforma de dados (data lake/lakehouse) para BI unificado.

🤖 IA Generativa e Automação: conforme a maturidade da empresa, o plano recomenda AIOps (detecção de anomalias e previsão de capacidade), copilotos operacionais para automatizar tarefas repetitivas de sustentação, segurança com IA (SIEM/XDR e playbooks SOAR de resposta automática) e assistentes de IA generativa (RAG) sobre bases internas. A fase final do roteiro (Otimização) inclui automações com IA e integrações inteligentes entre ERP e CRM.

🛡 Governança, Ética e Segurança Digital (LGPD): uma pergunta específica avalia o mapeamento de dados pessoais (ROPA), o Encarregado (DPO), a classificação e a criptografia. Setores regulados (Saúde, Financeiro e Governo) com baixa maturidade em LGPD têm o risco elevado automaticamente. As recomendações incluem MFA, NGFW, segmentação, Zero Trust, controle de acesso por perfil, DLP, RIPD e cuidados com transferência internacional de dados (art. 33). Também tratam do uso ético de IA: anonimização/pseudonimização e trilha de auditoria antes de usar IA generativa sobre dados internos. O próprio app segue o princípio de Privacy by Design: nenhum dado sai do navegador.

🛠 3. IAs Generativas e Ferramentas Utilizadas
Ferramenta / IA	Como foi utilizada no projeto
Claude (Anthropic), via Claude Code	Estruturação das regras de negócio, pesos do diagnóstico e textos técnicos; geração do código HTML/JS; criação do logo em SVG; escrita e execução dos testes automatizados; revisão visual por capturas de tela.
TailwindCSS & Chart.js (CDN)	Estilização executiva responsiva (tema escuro na tela e claro na impressão) e geração do gráfico radar de maturidade.
Lucide Icons (CDN)	Ícones da interface (pilares, etapas, cards e botões).
Playwright + Node.js (node:test)	65 testes automatizados de lógica, interface, impressão/PDF, celular/tablet e animações.
axe-core	Testes de acessibilidade (WCAG 2.1 AA), incluindo contraste de cores.
GitHub & GitHub Pages	Versionamento de código e publicação em nuvem estática (PaaS/CDN).
GitHub Actions	Execução automática dos testes a cada push (integração contínua).
🧠 4. Diário de Construção: Como Construímos e Refinamos o App
Concepção e Engenharia de Prompt: o prompt inicial foi um prompt estruturado com papel, restrições e critérios de aceite. Pedimos à IA que atuasse como Engenheiro de Software Sênior e Consultor Especialista em Infraestrutura em Nuvem. Definimos restrições técnicas fechadas: um único index.html, sem backend e sem build, com Tailwind, Chart.js e ícones via CDN, JavaScript puro e processamento 100% local. Fixamos os 4 pilares exatos do diagnóstico. Listamos cada requisito obrigatório: 8 perguntas com pontuação de 0 a 4, validação, demo, fórmulas de nota e score ponderado, faixas dos selos, regra de risco com peso maior para Backup e Rede, recomendação de modelo de nuvem, dashboard, radar, boas práticas, roteiro e impressão em PDF. Por fim, exigimos o código completo, sem trechos omitidos e com funções comentadas, para facilitar a edição. A estratégia foi deixar pouco espaço para interpretação: quanto mais específico o pedido, mais próximo do esperado veio o resultado.

Ajustes e Refinamentos Técnicos: na primeira versão, a própria IA testou o app num navegador automatizado e corrigiu detalhes visuais: texto sobreposto na mensagem de validação, espaço vazio no card do score e o plural "1 pts". Depois do nosso teste, fizemos um segundo pedido:

visual mais profissional e minimalista, com tema escuro;
um logo próprio;
demo aleatória que nunca repete a mesma empresa;
navegação mais intuitiva e animada;
testes melhores.
O resultado:

o formulário virou um assistente em etapas;
o laudo ganhou animações (anel do score, contadores, painel "Analisando…");
o logo foi escolhido entre 4 variações renderizadas;
a demo passou a combinar 8 cenários realistas com nomes nunca repetidos;
foi criada uma suíte de 65 testes automatizados.
Os testes encontraram problemas que passariam despercebidos a olho nu: contraste insuficiente em uma das cores do selo (só aparecia em algumas demos sorteadas), notificação vazando para fora da tela no celular e o "J" do logo invisível para quem usa a opção de reduzir animações. Todos foram corrigidos.

Principal Aprendizado: (texto sugerido — revisem e reescrevam com as palavras de vocês) Ficou claro que migrar para a nuvem não é só "mover servidores". Backup testado, internet redundante e dados mapeados conforme a LGPD são pré-requisitos, e por isso pesam mais no risco. Não existe um modelo de nuvem melhor para todos: a escolha entre SaaS, PaaS, IaaS ou Híbrido depende do porte, do setor, dos sistemas legados e da maturidade da empresa. Sobre IA generativa, aprendemos que ela acelera muito o desenvolvimento, mas o resultado depende de especificar bem o problema e de validar o que foi gerado. Os testes automatizados encontraram erros que não tínhamos percebido. A IA funciona como uma equipe técnica, mas a responsabilidade pelas regras de negócio, pela ética e pela qualidade continua sendo de quem a orienta.

▶️ 5. Como Usar
Abra o app pelo link do GitHub Pages (ou abra o index.html direto no navegador).
Clique em Iniciar diagnóstico, preencha o perfil da empresa e responda às 2 perguntas de cada pilar.
Clique em Gerar diagnóstico para ver o laudo. Para um exemplo pronto, use Carregar Caso Exemplo (Demo).
Use Imprimir / Exportar Laudo em PDF. No diálogo de impressão, marque "Gráficos de fundo" para manter as cores.
Lógica de cálculo (resumo)
Item	Regra
Nota do pilar	Soma dos pontos das 2 perguntas ÷ 8 × 100
Score Geral	Média ponderada: Servidores 25% · Rede 20% · Dados 25% · Backup 30%
Selos	Crítico 0–39% · Em Transição 40–59% · Estruturado 60–79% · Líder Digital 80–100%
Risco	100 − média ponderada (Backup 35% · Rede 30% · Servidores 20% · Dados 15%), com agravantes para ausência de backup, rede frágil e setor regulado sem maturidade LGPD
Modelo de nuvem	Regras de pontuação por porte, setor, legados, hardware, rede, LGPD e maturidade (empate → modelo mais simples)
🧪 6. Testes Automatizados
Requer Node.js 20 ou mais recente.

npm install
npx playwright install chromium
npm test
Comando	O que testa
npm run test:logic	Cálculos: notas, score, selos, risco, modelo de nuvem, roteiro, recomendações e demo aleatória
npm run test:ui	Assistente, validação, demo, laudo, gráfico, impressão/PDF, celular, tablet e animações
npm run test:a11y	Acessibilidade WCAG 2.1 AA com axe-core (inclui contraste)
npm run test:cdn	Os mesmos testes usando os CDNs reais (precisa de internet)
Por padrão, os testes rodam offline, com as mesmas versões das bibliotecas instaladas em node_modules. Capturas de tela e um PDF de exemplo ficam em test-results/. O workflow .github/workflows/tests.yml roda tudo a cada push.

✏️ 7. Personalização
Todo o conteúdo editável fica em constantes no início do <script> do index.html:

Constante	O que controla
APP_CONFIG.authors	Créditos dos autores (rodapé e assinaturas do PDF)
PILLARS	Pesos do score e do risco
QUESTIONS	Perguntas e alternativas
RECOMMENDATIONS	Plano de boas práticas
ROADMAP_PHASES	Fases do roteiro
DEMO_ARCHETYPES	Cenários da demo aleatória
📁 Estrutura do Repositório
index.html                  → o aplicativo completo (é o que o GitHub Pages publica)
tests/                      → testes automatizados (lógica, interface e acessibilidade)
package.json                → dependências e comandos de teste
.github/workflows/tests.yml → integração contínua (GitHub Actions)
⚠️ Ferramenta educacional e orientativa: o laudo é uma estimativa baseada nas respostas informadas e não substitui um assessment técnico com métricas reais do ambiente.

