# Roteiro de desenvolvimento — primeiros 90 dias

## Princípio do projeto
Os primeiros 90 dias são dedicados a estudo, definição de regras, coleta de dados e simulação. Não existe obrigação de operar ao vivo ao final desse período. O avanço depende da qualidade das evidências, não do calendário nem do saldo de aportes.

## Objetivos dos 90 dias
Ao final do ciclo, queremos ter:
1. Uma ficha técnica do WDO conferida nas fontes oficiais e atualizada quando houver mudanças.
2. Um diário de mercado com fatos, hipóteses e resultados claramente separados.
3. Uma ou duas hipóteses de estratégia descritas em regras objetivas.
4. Um protocolo de backtest/simulação que inclua custos, slippage e regras de execução.
5. Um relatório de avaliação que diga se a hipótese merece novos testes, precisa ser ajustada ou deve ser descartada.

## Fase 1 — Fundamentos e preparação (dias 1–30)

### Semana 1 — Contrato e ambiente
- Estudar especificação, vencimentos, código do contrato, tick, valor financeiro do ponto, horários e ajustes.
- Confirmar as informações em fonte oficial B3; registrar a data de consulta.
- Entender margem de garantia, ajuste diário, custos da corretora, emolumentos, tributação e risco de alavancagem.
- Identificar plataforma e ambiente de simulação disponíveis, sem enviar ordens reais.
- Entregável: ficha técnica WDO e checklist de custos/margem.

### Semana 2 — O que movimenta o dólar
- Estudar relação entre USD/BRL, juros brasileiros e americanos, diferencial de juros, fluxo, risco global e commodities relevantes.
- Acompanhar agenda de indicadores e decisões de política monetária.
- Separar fato observado de interpretação e hipótese.
- Entregável: glossário e mapa de fatores macroeconômicos, sem transformar correlação em sinal automático.

### Semana 3 — Leitura de mercado e contexto
- Aprender a registrar abertura, máxima/mínima, amplitude, volatilidade, volume e comportamento em torno de eventos.
- Comparar sessões de tendência, congestão e alta volatilidade.
- Não procurar padrões em retrospecto sem definir antes o que seria observado.
- Entregável: 10 fichas de sessão com contexto e observações.

### Semana 4 — Regras de risco e diário
- Definir como registrar entrada hipotética, stop, alvo, motivo, horário, contexto, custos e resultado.
- Definir limite de perda hipotético por operação e por sessão para fins de simulação.
- Criar regras de pausa: erro operacional, perda do limite simulado, evento extraordinário ou ausência de setup.
- Entregável: modelo de diário e protocolo de risco de simulação.

## Fase 2 — Hipóteses e testes iniciais (dias 31–60)

### Semana 5 — Escolher uma hipótese
- Escolher apenas um padrão observável para investigar.
- Escrever condições de entrada, invalidação/stop, saída, horário permitido e situações em que não operar.
- Definir quais dados seriam necessários para testar.
- Entregável: ficha da hipótese versão 1, antes de olhar os resultados do teste.

### Semana 6 — Teste histórico exploratório
- Aplicar as regras sem alterá-las operação a operação.
- Registrar todas as ocorrências elegíveis, inclusive perdas e sinais ignorados.
- Incluir custos estimados e slippage conservador.
- Separar dados de desenvolvimento dos dados reservados para validação.
- Entregável: primeira amostra documentada e lista de limitações dos dados.

### Semana 7 — Simulação em tempo real
- Acompanhar o mercado sem dinheiro real e registrar cada sinal elegível.
- Não inventar preenchimentos: considerar spread, fila, latência e possibilidade de não execução.
- Marcar desvios de regra e motivos.
- Entregável: diário de simulação e relatório de aderência.

### Semana 8 — Revisão sem otimização excessiva
- Medir resultado líquido simulado, média por operação, payoff, taxa de acerto, drawdown, sequência de perdas e frequência.
- Avaliar se o resultado depende de poucos casos ou de um período específico.
- Não escolher parâmetros apenas porque melhoraram o passado.
- Entregável: relatório intermediário e decisão documentada: continuar, revisar ou descartar.

## Fase 3 — Validação e decisão de próximos testes (dias 61–90)

### Semana 9 — Validação fora da amostra
- Aplicar a regra congelada em dados não usados para desenvolver a hipótese.
- Não alterar a regra durante a validação.
- Registrar custos, slippage e condições de mercado.
- Entregável: resultado fora da amostra.

### Semana 10 — Robustez
- Verificar comportamento em sessões de tendência, congestão e volatilidade elevada.
- Testar sensibilidade a custos e slippage maiores.
- Identificar dependência de horário, evento ou condição rara.
- Entregável: análise de robustez e limitações.

### Semana 11 — Simulação disciplinada
- Repetir a execução simulada seguindo o plano sem exceções.
- Medir aderência às regras, erros e qualidade de registro.
- Não aumentar lote virtual para perseguir meta diária.
- Entregável: relatório de disciplina operacional.

### Semana 12 e dias finais — Revisão do ciclo
- Consolidar dados, decisões, mudanças de hipótese e pontos ainda desconhecidos.
- Verificar se existe amostra suficiente; se não houver, prolongar a simulação.
- Definir o próximo ciclo de 90 dias.
- Entregável: relatório final do ciclo e plano de continuidade.

## Métricas mínimas do diário
- Data, horário e contexto da sessão.
- Hipótese/setup e versão da regra.
- Entrada, stop, saída e motivo da saída.
- Resultado bruto, custos estimados, slippage e resultado líquido simulado.
- Maior excursão favorável/adversa, quando os dados permitirem.
- Aderência à regra e observações.
- Captura ou referência dos dados utilizados, quando disponível.

## Critérios para considerar qualquer operação real
O fim dos 90 dias não autoriza automaticamente operar ao vivo. Antes disso, exigir:
- estratégia objetiva, reproduzível e documentada;
- amostra suficiente e validação fora da amostra;
- expectativa líquida positiva após custos e slippage, sem depender de poucos resultados;
- drawdown e sequência de perdas compatíveis com limites pessoais definidos previamente;
- margem, custos, tributos e regras atuais confirmados com B3 e corretora;
- capacidade financeira de suportar perdas sem tocar em despesas ou reserva;
- plano de contingência, limite de perda e tamanho mínimo compatível com o risco.

Se qualquer critério falhar ou houver incerteza relevante, continuar em estudo/simulação. Não há prazo máximo para essa fase.

## Rotina semanal sugerida
- **Antes da sessão:** ler agenda macro e notícias relevantes; anotar cenários possíveis sem prever certeza.
- **Durante a sessão:** observar e registrar; não improvisar regras.
- **Depois da sessão:** revisar diário, execução simulada e desvios.
- **Fim da semana:** consolidar métricas e escrever o que foi aprendido, o que é hipótese e o que continua desconhecido.

## Controle de versões
Toda mudança nas regras deve receber nova versão e justificativa. Não misturar resultados de versões diferentes como se fossem a mesma estratégia.

## Aviso
Este roteiro é educacional e não constitui recomendação individual de investimento. Contratos futuros são alavancados e podem causar perdas rápidas. Meta financeira não é garantia de resultado e nunca deve justificar aumento de risco.
