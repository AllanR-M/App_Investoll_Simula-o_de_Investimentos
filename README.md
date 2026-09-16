# App_Investoll_Simula-o_de_Investimentos
Simulador de investimentos desenvolvido como parte do projeto App Investool — DIO.me, com foco em transformar parâmetros financeiros simples em projeções de patrimônio, renda mensal estimada e uma sugestão de distribuição de aportes entre diferentes tipos de FIIs.

Investool

Simulador de investimentos para projeção de patrimônio, dividendos e distribuição de aportes.

🎯 Objetivo

Permitir que o usuário simule diferentes estratégias de investimento informando:

Aporte mensal

Prazo de investimento

Taxa de rendimento mensal

Perfil de investidor

A ferramenta apresenta o patrimônio projetado, uma estimativa de dividendos e uma sugestão de distribuição do aporte entre categorias de FIIs.

📊 Funcionalidades

Simulação de patrimônio

Calcula o valor futuro dos aportes considerando juros compostos.

Entradas:

Aporte mensal

Prazo em anos

Taxa de rendimento mensal

Resultado:

Patrimônio acumulado

Estimativa de dividendos

Calcula uma estimativa de renda mensal com base no patrimônio projetado e na taxa de rendimento da carteira.

Dividendos = Patrimônio × Taxa de rendimento

Cenários

Permite visualizar projeções para diferentes períodos:

2 anos

5 anos

10 anos

20 anos

30 anos

Perfil de investidor

A ferramenta possui três perfis:

Conservador

Moderado

Agressivo

Cada perfil possui uma distribuição percentual específica entre categorias de FIIs.

🏢 Categorias de FIIs

A distribuição considera:

Categoria

Descrição

Papel

Recebíveis e títulos imobiliários

Tijolo

Imóveis físicos

Híbridos

Estratégias e ativos diversificados

FOFs

Fundos que investem em outros FIIs

Desenvolvimento

Projetos e desenvolvimento imobiliário

Hotelárias

Segmento hoteleiro

📈 Distribuição por perfil

Categoria

Conservador

Moderado

Agressivo

Papel

30%

32%

50%

Tijolo

50%

35%

10%

Híbridos

10%

8%

5%

FOFs

10%

5%

5%

Desenvolvimento

0%

10%

20%

Hotelárias

0%

10%

10%

Total

100%

100%

100%

O valor destinado a cada categoria é calculado por:

Aporte mensal × percentual da categoria

🧮 Cálculos

Patrimônio futuro

A projeção utiliza a função financeira FV:

=FV(taxa_mensal;anos*12;aporte*-1)

Dividendos

=patrimonio*rendimento_carteira

Sugestão de aporte

A ferramenta utiliza como referência 30% do salário:

Salário × 30%

📁 Estrutura da planilha

APP_Investool

Interface principal do simulador.

Contém:

Configurações

Simulação

Resultados

Cenários

Perfil de investidor

Distribuição do aporte

Tbd_apoio

Tabela auxiliar utilizada para armazenar as regras de distribuição dos perfis.

Estrutura:

CHAVE | PERFIL | TIPO DE FII | %

A interface consulta essa tabela para identificar o percentual correspondente ao perfil selecionado.

🔄 Fluxo

Salário
   ↓
Sugestão de aporte

Aporte + Prazo + Taxa
   ↓
Projeção de patrimônio
   ↓
Estimativa de dividendos

Perfil selecionado
   ↓
Percentuais de distribuição
   ↓
Valor por categoria de FII

⚠️ Premissas

A ferramenta é uma simulação matemática e não representa garantia de rentabilidade ou recomendação de investimento.

A versão atual não considera automaticamente:

Inflação

Impostos

Taxas e custos

Oscilação das cotas

Variação dos dividendos

Aportes extraordinários

Alterações no aporte ao longo do tempo

Os resultados dependem das taxas e demais parâmetros informados pelo usuário.

🚀 Próximas evoluções

Transformar em aplicação web

Adicionar gráficos

Permitir aporte inicial

Simular inflação

Comparar diferentes cenários

Permitir aumento anual dos aportes

Permitir personalização da carteira

Criar testes automatizados

Publicar versão online

📌 Status

Protótipo / MVP

A versão atual está implementada em Excel e contém o motor de simulação e as regras de distribuição necessárias para evolução do projeto.

📄 Arquivo-base

App_Investool_Dio.me.xlsx

Investool — transforme seus aportes em cenários.
