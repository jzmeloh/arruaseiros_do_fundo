# arruaseiros_do_fundo
# Citizen Assist AI — Módulo de Energias Renováveis e Sustentáveis

*Disciplina:* Soluções em Energias Renováveis e Sustentáveis (1CC)  
*Integrantes do Grupo:*  
- [Nome Completo 1] — RM: [000000]  
- [Nome Completo 2] — RM: [000000]  
- [Nome Completo 3] — RM: [000000]  

---

## 1. Contexto e Público-Alvo
* *Público-alvo:* Famílias residentes em áreas urbanas brasileiras (classes C e D, média de 4 moradores por domicílio) que enfrentam impacto relevante da conta de energia elétrica no orçamento doméstico.
* *Necessidade energética:* Aquecimento de água para banho. Segundo o PROCEL/EPE, o chuveiro elétrico representa entre *25% e 35% do consumo elétrico residencial* no Brasil e concentra demanda no horário de ponta (18h às 21h).
* *Como o Citizen Assist AI contribui:* Traduz conceitos técnicos de potência ($W$), energia ($kWh$), eficiência energética e energia solar térmica em orientações financeiras e ambientais personalizadas, ajudando o cidadão a escolher a solução viável para o seu tipo de moradia (casa própria, alugada ou apartamento) e orçamento.

---

## 2. Análise de Consumo e Premissas dos Dados

Para garantir transparência técnica, os dados utilizados combinam referências públicas do setor elétrico brasileiro e premissas de uso claramente identificadas:

| Parâmetro | Valor Adotado | Tipo de Dado | Origem / Premissa |
| :--- | :--- | :--- | :--- |
| *Perfil familiar* | 4 pessoas (1 banho/dia cada) | Estimado | Premissa de residência urbana padrão |
| *Duração média do banho* | 10 minutos/banho (40 min/dia) | Estimado | Média comportamental urbana |
| *Período de referência* | 1 mês (30 dias = 20 h/mês de uso) | Padronizado | Base mensal de faturamento |
| *Potência chuveiro convencional* | 5.500 W (5,5 kW) | Real / Público | Etiqueta INMETRO/PROCEL (modo Inverno) |
| *Tarifa residencial média* | R$ 0,85 / kWh | Estimado | Média nacional ANEEL com tributos (bandeira verde) |
| *Fator de emissão do SIN* | 0,055 kg CO₂ / kWh | Real / Público | Base média anual do MCTI (Sistema Interligado Nacional) |

*Fórmula aplicada:*  
$$E = P \times \Delta t$$  
(Onde $E$ é a energia em kWh, $P$ é a potência em kW e $\Delta t$ é o tempo de operação em horas).

---

## 3. Comparação de Alternativas (Período Base: 1 Mês / 30 Dias)

Comparamos o *Cenário Atual* com duas soluções para a mesma necessidade (banho diário de 4 pessoas):
1. *Alternativa 1 (Eficiência Energética):* Substituição por chuveiro eletrônico (controle gradual de temperatura, operando em potência média de *3.500 W) aliado à redução consciente do banho para **8 minutos* (16 h/mês).
2. *Alternativa 2 (Fonte Renovável — Energia Solar Térmica):* Instalação de um *Aquecedor Solar de Água Residencial* (coletor solar térmico + reservatório), que supre em média *75% da demanda térmica anual* via radiação solar, mantendo resistência elétrica auxiliar (25%) para dias frios ou nublados.

| Indicador (Mensal) | Cenário Atual (Convencional) | Alt. 1: Eficiência Energética | Alt. 2: Aquecedor Solar (Renovável) |
| :--- | :--- | :--- | :--- |
| *Fonte de Energia* | 100% Rede Elétrica | 100% Rede Elétrica (Otimizada) | 75% Solar Térmica + 25% Rede |
| *Consumo Elétrico* | 110,0 kWh/mês | 56,0 kWh/mês (-49,1%) | 27,5 kWh/mês (-75,0%) |
| *Custo na Conta de Luz* | R$ 93,50/mês | R$ 47,60/mês | R$ 23,38/mês |
| *Economia Financeira* | — | R$ 45,90/mês (R$ 550,80/ano) | R$ 70,12/mês (R$ 841,50/ano) |
| *Investimento Inicial (Estimado)* | R$ 0,00 | R$ 160,00 | R$ 2.800,00 (kit instalado) |
| *Retorno (Payback Simples)* | — | ~3,5 meses | ~40 meses (3,3 anos) |
| *Emissão de Carbono* | 6,05 kg CO₂/mês | 3,08 kg CO₂/mês (-2,97 kg) | 1,51 kg CO₂/mês (-4,54 kg) |

---

## 4. Justificativas Técnicas (Custos, Viabilidade e Meio Ambiente)

* *Custos e Retorno:* A *Alternativa 1* possui barreira de entrada mínima (R$ 160,00) e se paga em menos de 4 meses, sendo ideal para famílias com orçamento restrito. A *Alternativa 2* exige aporte inicial maior (R$ 2.800,00), mas gera a maior economia recorrente (~R$ 841/ano) e valoriza o imóvel.
* *Viabilidade Técnica:* O aquecedor solar exige telhado ou laje com boa incidência solar (preferencialmente face Norte no Brasil), espaço estrutural para o boiler (reservatório térmico) e autorização do proprietário. Em apartamentos ou imóveis alugados sem permissão de reforma, o assistente recomenda automaticamente a Alternativa 1.
* *Impactos Ambientais:* Além de evitar até *54,45 kg de CO₂ por ano* (na opção solar), ambas as soluções reduzem o pico de carga elétrica entre 18h e 21h, diminuindo a necessidade de acionamento de usinas termelétricas fósseis no Sistema Interligado Nacional.

---

## 5. Integração ao Citizen Assist AI e Limitações

O módulo citizen_assist_energia.py consulta a base dados_energia.json, calcula o perfil personalizado do cidadão e entrega respostas em linguagem acessível contendo obrigatoriamente:
1. Diagnóstico do consumo atual em kWh e Reais;
2. Comparativo entre eficiência energética e fonte renovável;
3. *Condições e Limitações:* O assistente alerta explicitamente que os valores são estimativas sujeitas a variações climáticas (irradiação solar local), bandeiras tarifárias da distribuidora, temperatura ambiente da água e hábitos de uso.

---

## 6. Testes com Usuários e Ajustes Realizados

Foram realizados testes de compreensão e utilidade com 3 perfis de usuários (dados anonimizados):

| Cenário Testado | Feedback Recebido | Ajuste Implementado no Assistente |
| :--- | :--- | :--- |
| *Usuário A* (Morador de apartamento alugado, 3 pessoas) | "O sistema sugeriu aquecedor solar, mas não posso furar o teto do prédio." | Inclusão do filtro de tipo de moradia (casa_propria vs. apartamento_ou_aluguel) para priorizar eficiência energética quando há restrição estrutural. |
| *Usuário B* (Dona de casa, 5 pessoas) | "Não entendi o que significa 'fator de emissão em kg CO₂'." | Tradução do dado ambiental para comparações cotidianas (ex.: equivalência em quilômetros rodados de carro a gasolina). |
| *Usuário C* (Estudante, 2 pessoas) | "Queria saber quanto tempo demora para recuperar o dinheiro do painel solar." | Exibição explícita do tempo de retorno do investimento (payback em meses/anos) junto com o custo inicial estimado. |

---

## 7. Como Executar o Projeto

1. Certifique-se de ter o *Python 3.8+* instalado.
2. Clone este repositório e acesse a pasta do projeto:
   ```bash
   python citizen_assist_energia.py
   git clone [https://github.com/SEU-USUARIO/citizen-assist-energia.git](https://github.com/SEU-USUARIO/citizen-assist-energia.git)
   cd citizen-assist-energia
