# App_Investoll_Simula-o_de_Investimentos
Simulador de investimentos desenvolvido como parte do projeto App Investool — DIO.me, com foco em transformar parâmetros financeiros simples em projeções de patrimônio, renda mensal estimada e uma sugestão de distribuição de aportes entre diferentes tipos de FIIs.

Sobre o projeto

O Investool é uma ferramenta de simulação financeira criada para responder, de forma simples e visual, perguntas como:

Quanto devo investir por mês?

Por quantos anos devo investir?

Quanto posso acumular ao longo do tempo?

Qual patrimônio posso atingir mantendo um determinado aporte?

Quanto esse patrimônio poderia gerar de dividendos mensais?

Como distribuir o aporte mensal entre diferentes categorias de Fundos de Investimento Imobiliário (FIIs), de acordo com um perfil de investidor?

A proposta é permitir que o usuário altere poucos parâmetros e consiga visualizar rapidamente diferentes cenários de acumulação.

Importante: o Investool é uma ferramenta educacional de simulação. Os valores apresentados são projeções matemáticas e não representam garantia de rentabilidade, recomendação de investimento ou promessa de dividendos futuros.

🎯 Objetivos

O projeto tem como principais objetivos:

Simplificar o planejamento de investimentos;

Demonstrar o impacto dos aportes recorrentes no longo prazo;

Estimar o patrimônio acumulado considerando uma taxa de rendimento mensal;

Estimar uma renda mensal hipotética a partir de uma taxa de distribuição definida;

Apresentar cenários de curto, médio e longo prazo;

Sugerir uma distribuição do aporte entre categorias de FIIs conforme o perfil selecionado;

Servir como base para uma futura aplicação web ou aplicativo de simulação financeira.

🧮 Como o simulador funciona

O fluxo principal do Investool pode ser resumido da seguinte forma:

Salário
   ↓
Sugestão de aporte
   ↓
Aporte mensal + prazo + taxa de rendimento
   ↓
Projeção de patrimônio
   ↓
Estimativa de dividendos
   ↓
Cenários de longo prazo
   ↓
Perfil de investidor
   ↓
Distribuição sugerida do aporte entre FIIs

⚙️ Parâmetros principais

A planilha que serve como base do projeto possui uma área de configurações e uma área de simulação.

Configurações

Parâmetro

Exemplo

Descrição

Salário

R$ 4.200

Renda mensal utilizada como referência

Rendimento da carteira

0,60% a.m.

Taxa utilizada para estimar dividendos

Sugestão de investimento

30%

Percentual do salário usado como referência para sugestão de aporte

A sugestão de investimento é calculada pela fórmula:

Salário × 30%

No exemplo da planilha:

R$ 4.200 × 30% = R$ 1.260

Esse valor é uma referência de simulação, e não uma regra financeira.

💰 Simulação de investimento mensal

O usuário informa três variáveis principais:

1. Quanto investir por mês?

Representa o aporte mensal realizado pelo investidor.

Exemplo:

R$ 200 por mês

2. Por quantos anos?

Define o período da simulação.

Exemplo:

5 anos

O simulador converte o período para meses:

5 × 12 = 60 meses

3. Taxa de rendimento mensal

Representa a taxa mensal utilizada na projeção de crescimento do patrimônio.

Exemplo:

1,08% ao mês

📈 Cálculo do patrimônio acumulado

O patrimônio projetado é calculado utilizando o conceito de valor futuro (Future Value / FV).

A lógica utilizada na planilha é equivalente a:

FV(taxa mensal, quantidade de meses, aporte mensal)

Na planilha, a fórmula utilizada é:

=FV(taxa_mensal;qtd_anos*12;aporte*-1)

O aporte é multiplicado por -1 porque, na função FV, os aportes são tratados como saídas de caixa.

Exemplo conceitual

Considerando:

Aporte mensal: R$ 200
Prazo: 5 anos
Taxa: 1,08% a.m.

O simulador calcula o valor futuro dos aportes considerando a capitalização mensal.

O resultado representa uma projeção matemática, considerando que a taxa informada permaneça constante durante todo o período.

💸 Estimativa de dividendos mensais

Depois de calcular o patrimônio, o Investool estima uma renda mensal aplicando a taxa de rendimento da carteira sobre o patrimônio acumulado.

A lógica utilizada é:

Patrimônio acumulado × rendimento da carteira

Na planilha:

=patrimonio*rendimento_carteira

Exemplo conceitual

Se o patrimônio projetado fosse:

R$ 100.000

e a taxa considerada fosse:

0,60% ao mês

a estimativa seria:

R$ 100.000 × 0,60% = R$ 600/mês

Esse cálculo representa uma estimativa hipotética de renda, não uma previsão de dividendos reais.

🗓️ Cenários de longo prazo

O Investool também apresenta automaticamente diferentes horizontes de investimento.

Os cenários existentes na versão atual são:

2 anos;

5 anos;

10 anos;

20 anos;

30 anos.

Para cada período, são apresentados:

patrimônio projetado;

estimativa de dividendos mensais.

A fórmula utiliza o mesmo aporte mensal e a mesma taxa informada pelo usuário, alterando apenas o prazo.

Exemplo da lógica:

=FV(taxa_mensal;anos*12;aporte*-1)

Isso permite visualizar o efeito do tempo e dos juros compostos sobre o patrimônio.

👤 Perfil do investidor

Uma das funcionalidades adicionais do projeto é a possibilidade de selecionar um perfil:

Conservador

Moderado

Agressivo

O perfil determina uma distribuição percentual do aporte entre categorias de FIIs.

A nomenclatura de perfil e os percentuais são parâmetros definidos na base da ferramenta e devem ser tratados como uma referência de simulação, não como recomendação personalizada.

🏢 Categorias de FIIs

A versão atual considera seis categorias:

Categoria

Descrição geral

Papel

FIIs predominantemente relacionados a recebíveis imobiliários e títulos de crédito

Tijolo

Fundos com exposição a imóveis físicos

Híbridos

Fundos que podem combinar diferentes estratégias e tipos de ativos

FOFs

Fundos de fundos, que investem em outros FIIs

Desenvolvimento

Fundos ligados a projetos e desenvolvimento imobiliário

Hotelárias

Fundos relacionados ao segmento hoteleiro

📊 Distribuição por perfil

A base Tbd_apoio contém a distribuição percentual utilizada pela ferramenta.

Perfil Conservador

Tipo de FII

Percentual

Papel

30%

Tijolo

50%

Híbridos

10%

FOFs

10%

Desenvolvimento

0%

Hotelárias

0%

Total

100%

Perfil Moderado

Tipo de FII

Percentual

Papel

32%

Tijolo

35%

Híbridos

8%

FOFs

5%

Desenvolvimento

10%

Hotelárias

10%

Total

100%

Perfil Agressivo

Tipo de FII

Percentual

Papel

50%

Tijolo

10%

Híbridos

5%

FOFs

5%

Desenvolvimento

20%

Hotelárias

10%

Total

100%

💵 Cálculo do valor sugerido por categoria

Depois de selecionar o perfil, o simulador utiliza o aporte mensal para calcular quanto seria direcionado para cada categoria.

A lógica é:

Aporte mensal × percentual da categoria

Exemplo:

Aporte mensal = R$ 1.000
Perfil = Agressivo
Papel = 50%

Resultado:

R$ 1.000 × 50% = R$ 500

O mesmo cálculo é realizado para todas as categorias.

A soma final dos valores distribuídos deve representar 100% do aporte mensal.

Na planilha, a conferência é realizada pela fórmula:

=SUM(D34:D39)

🗂️ Estrutura do arquivo-base

O arquivo utilizado como referência para o projeto possui duas abas principais.

APP_Investool

É a interface principal da ferramenta.

Nela estão:

configurações;

salário;

sugestão de investimento;

aporte mensal;

prazo;

taxa mensal;

patrimônio projetado;

dividendos estimados;

cenários de longo prazo;

perfil do investidor;

distribuição do aporte por categoria de FII.

Tbd_apoio

É a tabela auxiliar utilizada para armazenar as regras de distribuição.

A estrutura possui:

CHAVE
PERFIL
TIPO DE FII
%

A coluna CHAVE combina o perfil e o tipo de FII:

=B3&"-"&C3

Exemplo:

AGRESSIVO-PAPEL

A interface principal utiliza essa chave para buscar automaticamente o percentual correspondente.

A busca é realizada com:

=VLOOKUP($C$30&"-"&B34;Tbd_apoio!A:D;4;0)

🔄 Fluxo de cálculo

O funcionamento completo pode ser representado desta maneira:

[Salário]
    │
    ├── × 30%
    │
    ▼
[Sugestão de investimento]

[Usuário define]
    ├── Aporte mensal
    ├── Prazo
    └── Taxa mensal
            │
            ▼
    [Valor futuro - FV]
            │
            ▼
    [Patrimônio acumulado]
            │
            ├── × taxa da carteira
            │
            ▼
    [Dividendos mensais estimados]

[Usuário seleciona perfil]
            │
            ▼
[Busca tabela auxiliar]
            │
            ▼
[Percentuais por categoria]
            │
            ▼
[Aporte × percentual]
            │
            ▼
[Valor sugerido por tipo de FII]

🧠 Conceitos financeiros utilizados

O projeto utiliza principalmente três conceitos.

Juros compostos

Os rendimentos são incorporados ao patrimônio e passam a participar dos próximos ciclos de capitalização.

Quanto maior o período, maior tende a ser o efeito da capitalização, assumindo uma taxa constante.

Aportes recorrentes

O simulador considera contribuições mensais constantes durante o período selecionado.

Isso permite visualizar como pequenas contribuições podem se acumular ao longo de vários anos.

Valor futuro

A função FV calcula o valor futuro de uma série de pagamentos considerando uma determinada taxa de juros e quantidade de períodos.

De forma simplificada:

Patrimônio futuro =
efeito dos aportes
+
efeito da capitalização

🧪 Exemplo de utilização

Uma simulação pode seguir este fluxo:

Salário:                 R$ 4.200
Aporte mensal:           R$ 200
Prazo:                   5 anos
Taxa mensal:             1,08%
Rendimento da carteira:  0,60%
Perfil:                  Agressivo

A ferramenta então:

calcula uma sugestão de aporte com base no salário;

utiliza o aporte informado pelo usuário;

converte 5 anos em 60 meses;

calcula o patrimônio futuro;

estima os dividendos mensais;

apresenta cenários de 2 a 30 anos;

identifica os percentuais correspondentes ao perfil agressivo;

calcula o valor destinado a cada categoria de FII.

⚠️ Premissas e limitações

Os resultados do Investool dependem diretamente das premissas informadas.

A ferramenta não considera automaticamente, na versão atual:

inflação;

imposto de renda;

custos de corretagem;

taxas de administração;

taxas de performance;

variação do preço das cotas;

vacância dos imóveis;

inadimplência;

alterações nos dividendos;

mudanças na composição da carteira;

aportes extraordinários;

crescimento ou redução salarial;

reinvestimento variável dos dividendos;

períodos de rentabilidade negativa.

Por isso, os resultados devem ser interpretados como simulações matemáticas, e não como projeções garantidas.

🔐 Segurança e responsabilidade

O projeto não deve ser interpretado como consultoria ou recomendação de investimento.

Os percentuais de distribuição apresentados são regras da própria ferramenta e servem para demonstrar como uma carteira poderia ser organizada dentro de diferentes cenários.

Antes de tomar decisões financeiras reais, é importante considerar:

objetivos pessoais;

horizonte de investimento;

tolerância a risco;

liquidez necessária;

situação financeira;

tributação;

características dos ativos;

diversificação.

🚀 Possíveis evoluções

O arquivo atual funciona como uma prova de conceito e pode ser transformado em uma aplicação mais completa.

Algumas evoluções possíveis:

Interface

transformar a planilha em uma aplicação web;

criar cards para os principais resultados;

adicionar gráficos;

criar sliders para aporte, prazo e taxa;

criar uma interface responsiva para celular;

adicionar modo claro/escuro.

Simulação

permitir aporte inicial;

permitir aumento anual do aporte;

simular inflação;

permitir diferentes taxas por período;

comparar cenários otimista, base e conservador;

permitir reinvestimento dos dividendos;

simular retiradas mensais;

calcular patrimônio real descontado pela inflação.

Carteira

adicionar mais classes de ativos;

permitir personalização dos percentuais;

criar regras de diversificação;

mostrar a distribuição percentual e monetária em gráficos;

permitir comparação entre diferentes perfis.

Relatórios

gerar resumo da simulação;

exportar resultados em PDF;

gerar planilha personalizada;

compartilhar uma simulação por link;

salvar diferentes cenários.

🤖 Possível evolução com tecnologia

Embora o nome Investool faça referência a uma ferramenta de investimentos, o projeto não depende de Inteligência Artificial para realizar os cálculos.

Uma futura versão poderia, opcionalmente, utilizar IA para funcionalidades complementares, como:

explicar os resultados em linguagem simples;

responder dúvidas sobre os indicadores;

comparar cenários;

identificar inconsistências nos parâmetros;

criar resumos personalizados;

transformar os resultados em insights educativos.

A IA, nesse caso, seria uma camada adicional de interação — não o mecanismo responsável pelo cálculo financeiro.

🛠️ Tecnologias e conceitos

Na versão-base atual, o projeto utiliza principalmente recursos de planilha:

Microsoft Excel;

fórmulas financeiras;

função FV;

função VLOOKUP;

operações matemáticas;

tabelas auxiliares;

parametrização por perfil.

Em uma futura implementação web, uma arquitetura possível seria:

Frontend
   │
   ├── HTML / CSS / JavaScript
   │
   ▼
Motor de simulação
   │
   ├── Aportes
   ├── Juros compostos
   ├── Cenários
   └── Distribuição da carteira
   │
   ▼
Interface de resultados

📁 Estrutura sugerida para uma versão de software

Caso o projeto seja convertido em aplicação, uma estrutura possível seria:

investool/
├── README.md
├── src/
│   ├── calculator/
│   │   ├── futureValue
│   │   ├── dividends
│   │   └── scenarios
│   │
│   ├── portfolio/
│   │   ├── profiles
│   │   └── allocation
│   │
│   ├── components/
│   │   ├── calculator
│   │   ├── results
│   │   └── portfolio
│   │
│   └── app/
│
├── data/
│   └── profiles
│
└── tests/
    ├── calculator
    └── portfolio

✅ Validações recomendadas

Para uma implementação em software, os seguintes testes são importantes:

Entrada

impedir aporte negativo;

impedir prazo igual ou menor que zero;

validar taxas;

validar salário;

garantir que um perfil válido tenha sido selecionado.

Cálculos

conferir cálculo do valor futuro;

conferir conversão de anos para meses;

conferir dividendos;

verificar distribuição de 100% do aporte;

testar valores muito altos e muito baixos.

Cenários

2 anos;

5 anos;

10 anos;

20 anos;

30 anos.

Carteira

verificar se todos os perfis possuem distribuição;

garantir que os percentuais de cada perfil somem 100%;

conferir se o valor monetário distribuído corresponde ao aporte informado.

📌 Status do projeto

Status: 🟡 Protótipo / prova de conceito

A versão atual está estruturada em uma planilha Excel e já contempla:

Configuração de salário;

Sugestão de investimento;

Aporte mensal;

Prazo de investimento;

Taxa de rendimento mensal;

Cálculo de patrimônio futuro;

Estimativa de dividendos;

Cenários de 2 a 30 anos;

Seleção de perfil;

Distribuição por categoria de FII;

Tabela auxiliar de parametrização.

Próximos passos sugeridos

Criar interface web;

Adicionar gráficos;

Adicionar aporte inicial;

Adicionar inflação;

Criar cenários comparativos;

Permitir personalização da carteira;

Criar testes automatizados;

Criar documentação técnica da API, caso uma API seja implementada;

Publicar uma versão online.

📄 Arquivo-base

A lógica inicial do projeto está documentada na planilha:

App_Investool_Dio.me.xlsx

Ela contém a implementação original dos cálculos e das regras de distribuição utilizadas como referência para a evolução do Investool.

👨‍💻 Projeto

Investool

Uma ferramenta de simulação financeira para visualizar o potencial de aportes recorrentes, juros compostos e geração de renda ao longo do tempo.

Investool — transforme seus aportes em cenários.
