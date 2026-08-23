# Aplicativo Já Tomei
Repositório criado para o acompanhamento do desenvolvimento do projeto final da matéria de desenvolvimento mobile - Universidade Saint Leo.

Aqui será desenvolvido um aplicativo mobile voltado para o dia a dia das mulheres, auxiliando no controle de ingestão de contraceptivos.

Criado o nome do aplicativo, será "Já Tomei", um aplicativo para lembrar as mulheres de tomarem o seu contraceptivo, auxiliando no não esquecimento do medicamento.

# Progresso do Desenvolvimento

Status atual: **Versão 1.3**

| Versão | Status | Descrição |
|--------|--------|-----------|
| 1.0 | V | Definição da proposta do aplicativo, elaboração da documentação inicial, wireframe manual e refinamento do wireframe digital. |
| 1.1 | V | Criação do projeto Android, definição da arquitetura MVVM, navegação entre telas, construção da interface principal, componentes reutilizáveis, testes do cálculo do ciclo e estrutura inicial do banco de dados Room. |
| 1.2 | V | Implementação da persistência do ciclo contraceptivo utilizando Room Database, criação do Repository e ViewModel, desenvolvimento da tela funcional de configuração do ciclo, validação dos dados informados e armazenamento permanente das configurações da usuária. |
| 1.3 | V | Integração do calendário principal com os dados reais do ciclo contraceptivo. |
| 1.4 | V | Implementação das notificações inteligentes e confirmação da tomada da medicação. |
| 1.5 | V | Revisão das implementações anteriores e ajustes de bugs. |
| 1.6 | V| Primeira versão completa do aplicativo, contemplando todas as funcionalidades propostas no projeto acadêmico. |

# Changelog

## Versão 1.0

Principais alterações:
- Definição da ideia do projeto;
- Levantamento dos requisitos;
- Documentação inicial;
- Wireframe manual;
- Wireframe digital.

## Versão 1.1

Principais alterações:
- Criação da estrutura do projeto Android;
- Implementação da arquitetura MVVM;
- Desenvolvimento da Splash Screen;
- Desenvolvimento da tela principal;
- Criação dos componentes reutilizáveis;
- Implementação da navegação entre telas;
- Implementação da lógica de cálculo do ciclo contraceptivo;
- Criação dos testes unitários.

## Versão 1.2
Nesta versão foi implementada a primeira funcionalidade completa do aplicativo.

Principais alterações:
- Implementação da persistência local utilizando Room Database;
- Criação da arquitetura Repository + ViewModel;
- Desenvolvimento da tela de configuração do ciclo contraceptivo;
- Validação dos campos informados pela usuária;
- Salvamento automático das configurações;
- Recuperação dos dados ao reabrir o aplicativo;
- Estrutura preparada para integração do calendário com dados reais.

## Versão 1.3
Nesta versão foi realizada a integração entre o calendário principal e os dados reais cadastrados pela usuária.

Principais alterações:
- Integração do calendário com o ciclo armazenado no Room Database;
- Remoção dos dados fictícios utilizados anteriormente na tela principal;
- Geração automática dos dias ativos da cartela;
- Identificação automática dos períodos de pausa;
- Projeção automática das cartelas seguintes;
- Implementação da navegação entre os meses do calendário;
- Criação de indicadores visuais para os dias ativos, pausa, data atual e dias inativos;
- Melhoria da legenda dos indicadores do calendário;
- Exibição dinâmica do status do ciclo;
- Identificação do número atual do comprimido durante a cartela;
- Identificação do dia atual da pausa;
- Cálculo automático da próxima medicação;
- Ampliação dos testes unitários do cálculo do ciclo, totalizando 13 testes aprovados.

## Versão 1.4
Nesta versão foram implementados os sistemas de lembretes, confirmação da tomada e histórico real da medicação.

Principais alterações:
- Implementação do sistema de notificações para o horário da medicação;
- Agendamento automático dos lembretes com WorkManager;
- Integração dos lembretes com o horário configurado no ciclo;
- Implementação da opção de adiar o lembrete;
- Respeito automático aos dias ativos e períodos de pausa do ciclo;
- Criação da tela de confirmação da tomada;
- Armazenamento das confirmações no Room Database;
- Atualização automática do calendário após a confirmação da medicação;
- Identificação visual dos dias com tomada confirmada;
- Bloqueio de novas confirmações após a medicação do dia já ter sido registrada;
- Implementação do histórico real das tomadas;
- Navegação entre os meses no histórico;
- Identificação dos registros como tomado, pendente ou não confirmado;
- Criação do resumo mensal de tomadas e não confirmações;
- Cálculo automático do percentual de adesão mensal;
- Exclusão dos dias futuros do cálculo de adesão;
- Cancelamento dos lembretes após a confirmação da tomada;
- Validação da confirmação antes do envio de uma notificação, evitando lembretes após a medicação já ter sido registrada;
- Realização de testes funcionais de notificações, confirmação, persistência dos dados, histórico e cálculo de adesão.

## Versão 1.5
Nesta versão o foco do projeto foi a implementação e validação do sistema de lembretes da medicação, garantindo que as notificações acompanhem corretamente o ciclo cadastrado pela usuária.

### Principais alterações:
- Agendamento de notificações no horário configurado para a medicação.
- Utilização do `AlarmManager` para agendamento dos lembretes.
- Utilização de alarmes exatos quando permitido pelo sistema.
- Recebimento dos alarmes através do `ReminderReceiver`.
- Exibição da notificação mesmo com o aplicativo em segundo plano.
- Funcionamento da notificação após reinicialização do dispositivo.
- Reagendamento automático do próximo lembrete.
- Reagendamento após a confirmação da medicação.
- Função de adiamento do lembrete.
- Atualização automática da Home ao retornar ao aplicativo.
- Atualização do calendário conforme o dia atual.
- Bloqueio das ações de confirmação e adiamento durante o período de pausa.
- Suspensão automática dos lembretes durante a pausa da cartela.
- Retomada automática dos lembretes após o período de pausa.
- Cancelamento do alarme ao excluir o ciclo.
- Tratamento da interface quando nenhum ciclo está cadastrado.

### Testes realizados
Durante a Sprint foram realizados testes manuais utilizando o emulador Android e ferramentas de depuração do Android Studio.

Foram validados os seguintes cenários:
1. Disparo da notificação no horário configurado.
2. Funcionamento da notificação com o aplicativo em segundo plano.
3. Funcionamento após reinicialização do dispositivo.
4. Adiamento do lembrete.
5. Confirmação da medicação e reagendamento para o próximo dia.
6. Alteração do horário da medicação.
7. Atualização da interface após mudança de data.
8. Entrada automática no período de pausa.
9. Ausência de notificações durante a pausa.
10. Agendamento automático para o primeiro dia da próxima cartela.
11. Exclusão do ciclo e cancelamento do próximo alarme.
12. Estado da Home sem ciclo cadastrado.

Os alarmes também foram verificados através do `adb shell dumpsys alarm`, permitindo confirmar as datas e horários registrados pelo sistema Android.

### Resultado da versão 1.5
O sistema de lembretes foi integrado ao ciclo de medicação e os principais fluxos foram validados com sucesso.
O aplicativo agora consegue acompanhar automaticamente:
**Cartela ativa → lembrete → confirmação → próximo lembrete → pausa → retomada da próxima cartela.**
Com isso, a versão 1.5 foi concluída e o projeto está preparado para a etapa final de revisão, testes e documentação.

## Versão 1.6
A versão 1.6 foi dedicada à revisão final do projeto, limpeza do código, validação da aplicação e geração do APK da versão final do **Já Tomei**.
Nesta etapa, as funcionalidades desenvolvidas nas versões anteriores foram revisadas e testadas de forma integrada, garantindo o funcionamento do fluxo completo de gerenciamento do ciclo e dos lembretes.

### Atividades realizadas
- Revisão final da estrutura do projeto;
- Limpeza de imports não utilizados;
- Busca por códigos temporários, TODOs e elementos utilizados durante o desenvolvimento;
- Execução de Clean e Build completo do projeto;
- Validação da compilação sem erros;
- Geração do APK de debug;
- Instalação limpa do APK no emulador Android;
- Validação das permissões necessárias;
- Teste completo do fluxo de cadastro do ciclo;
- Teste do disparo das notificações;
- Teste de confirmação da tomada;
- Teste de reagendamento automático do próximo lembrete;
- Teste da função de adiamento do lembrete;
- Teste de persistência dos dados após fechamento e reinicialização do aplicativo;
- Validação do calendário e dos períodos de pausa;
- Validação do histórico de tomadas e do cálculo de adesão.

### Validação final
O APK foi instalado diretamente no emulador, sem execução pelo Android Studio, permitindo simular uma instalação limpa da aplicação.

Foram validados os principais fluxos do aplicativo:
1. Instalação e primeira execução;
2. Solicitação e concessão das permissões;
3. Cadastro de uma nova cartela;
4. Exibição correta do ciclo na tela inicial;
5. Disparo da notificação no horário configurado;
6. Confirmação da tomada;
7. Atualização do calendário;
8. Reagendamento automático do próximo lembrete;
9. Persistência dos dados;
10. Consulta ao histórico de tomadas.

Todos os testes finais foram concluídos com sucesso.

### Status da Versão
**Versão 1.6 concluída com sucesso.**

Com a conclusão desta versão, o aplicativo **Já Tomei** possui uma versão funcional e validada, contemplando o fluxo proposto para o projeto acadêmico.

A publicação na Google Play Store não faz parte do escopo desta versão, tendo em vista que a entrega final não contempla esta etapa.

# Roadmap

- [x] Planejamento do aplicativo
- [x] Wireframes
- [x] Estrutura inicial do projeto
- [x] Arquitetura MVVM
- [x] Persistência com Room
- [x] Cadastro do ciclo contraceptivo
- [X] Calendário inteligente
- [X] Notificações automáticas
- [X] Confirmação da tomada
- [X] Histórico de utilização
- [X] Configurações do aplicativo
- [X] Versão final (v1.6)

# 1-	Descrição do projeto

O projeto consiste no desenvolvimento de um aplicativo mobile para Android, utilizando a linguagem Kotlin. O aplicativo busca auxiliar mulheres no controle diário do uso de contraceptivos, permitindo que o usuário cadastre informações importantes, como o horário em que costuma tomar o medicamente, a data de início da cartela, a quantidade de comprimidos ativos e o período de pausa entre uma cartela e outra.
Com esses dados, o aplicativo irá realizar automaticamente o cálculo dos dias em que a medicação deve ser tomada e os dias de pausa, bem como no período ativo da cartela, o aplicativo enviará notificações diárias no horário configurado pela usuária. Já durante a pausa, os alertas serão interrompidos automaticamente, retornando apenas quando uma nova cartela for iniciada, conforme o ciclo cadastrado.

# 2-	Problema que o aplicativo pretende resolver

O aplicativo busca solucionar um problema comum relacionado ao esquecimento ou irregularidade no uso do anticoncepcional, como esse tipo de medicação depende de horários consistentes para que sua eficácia não seja prejudicada, o esquecimento pode gerar insegurança, ansiedade e até risco real de falha no método contraceptivo, muitas usuárias também precisam controlar manualmente o período de pausa entre cartelas, o que pode gerar confusão sobre quando interromper e quando retornar ao uso do medicamento, dessa forma, o aplicativo pretende ofertar uma solução simples, prática e automatizada que reduza a necessidade de controle manual e auxilie na organização da rotina das usuárias. Diversos estudos demonstram que aplicativos móveis com lembretes, notificações e mecanismos de confirmação podem contribuir significativamente para melhorar a adesão medicamentosa, auxiliando o usuário na manutenção de sua rotina de tratamento (Dayer et al., 2013).

# 3-	Plataforma escolhida

A plataforma escolhida para o desenvolvimento do aplicativo será o Android, utilizando a linguagem Kotlin, essa escolha se baseia e justifica principalmente na ampla utilização do sistema Android no mercado brasileiro, o que torna o aplicativo acessível a uma maior parcela de usuárias. A escolha da linguagem Kotlin se deve ao fato de a linguagem atualmente ser uma das principais escolhas recomendadas para o desenvolvimento Android, oferecendo uma boa integração com o Android Studio, possuindo uma sintaxe moderna, interoperabilidade com Java, maior segurança contra erros de objetos nulos e uma integração completa com bibliotecas Jetpack (Kotlin, 2025; Google, 2026).

# 4-	Interface do Usuário (UI)

A interface será desenvolvida priorizando a simplicidade, organização e facilidade de navegação, seguindo as recomendações do Material Design, conjunto de diretrizes elaborada pelo Google para promover consistência visual, acessibilidade e melhor experiencia do usuário (Google, 2026).
Na tela principal, o elemento central será um calendário mensal em destaque, permitindo à usuário visualizar rapidamente o andamento do ciclo atual, os dias serão identificados por indicadores visuais que diferenciam os comprimidos já tomados dos dias que ainda estão pendentes, bem como do período de pausa entre as cartelas. Na parte superior da tela, haverá dois botões principais, O primeiro, representado por um ícone de engrenagem, será a configuração geral do aplicativo, como idioma, informações sobre a conta logada, permissões do aplicativo e o local de armazenamento das fotos de confirmação. O segundo botão, que será representado por um ícone de pílula, será destinado ao gerenciamento do ciclo contraceptivo, onde será cadastrado ou alterado a data de início da cartela, a quantidade de comprimidos tomados, os dias de pausa entre as cartelas, o horário de notificação desejado e os períodos de notificação em caso de adiamentos.
O calendário também permitirá consultas meses anteriores, funcionando como um histórico de utilização da medicação, onde a usuária poderá acompanhar seu desempenho ao longo do tempo e identificar possíveis esquecimentos.
Como diferencial, o aplicativo exigirá uma confirmação após cada lembrete recebido, sendo necessário um registro fotográfico da cartela ou do medicamento, funcionando como evidência de que a usuária registrou uma ingestão do medicamento, embora esse mecanismo não comprove efetivamente a ingestão, ele incentiva um maior comprometimento com a rotina e fornece um histórico das confirmações realizadas. Caso a usuário não possa tomar o medicamento imediatamente, será disponibilizada uma opção de adiar o lembrete, desta forma, o aplicativo continuará enviando novas notificações em intervalos configurados anteriormente pela própria usuária, como 10, 15 ,30 minutos, repetindo os alertas até que a confirmação seja registrada. Estratégias de lembretes recorrentes são amplamente utilizadas em aplicativos voltados à adesão de medicamentos por contribuírem para reduzir os esquecimentos (Dayer et al., 2013).
Visualmente, a interface utilizará componentes do Material Design, ícones padronizados, cores suaves e indicadores intuitivos, buscando oferecer uma experiencia agradável, acessível e consistente para diferentes perfis de usuárias.

# 5-	Principais funcionalidades

As principais funcionalidades são:
•	Cadastro do ciclo contraceptivo: Permite informar a data de início da cartela, quantidade de comprimidos ativos, o número de dias de pausa entre cartelas e o horário diário do lembrete e tempo de adiamento.
•	Cálculo automático do ciclo: A partir das informações cadastradas, o aplicativo calcula automaticamente os dias de uso do medicamento, o período de pausa e a data de início da próxima cartela, dispensando cálculos manuais da usuária.
•	Notificação inteligente: Envia lembretes diários no horário configurado durante o período de utilização do anticoncepcional e interrompe automaticamente os alertas durantes os dias de pausa, retornando o envio quando uma nova cartela for iniciada.
•	Confirmação de medicação: Após cada notificação, a usuária deve confirmar que realizou a tomada do medicamento, como recursos adicional, ela pode registrar uma foto da cartela ou do comprimido, criando um histórico das confirmações realizadas.
•	Adiamento do lembrete: Caso a medicação não possa ser tomada imediatamente, será possível adiar a notificação, o sistema continuará enviando novos lembretes em intervalos configurados até que a confirmação seja registrada.
•	Calendário interativo: Apresenta de forma visual o andamento do ciclo, destacando os dias em que a medicação já foi confirmada, os dias pendentes e o período de pausa, permite também a consulta de meses anteriores para acompanhar o histórico de utilização.
•	Gerenciamento das configurações: Disponibiliza uma área destinada às configurações gerais do aplicativo, incluindo idioma, preferências de conta e validação das fotos registradas.

# 6-	Design de telas
 
Referências
Dayer, L., Heldenbrand, S., Anderson, P., Gubbins, P. O., & Martin, B. C. (2013). Smartphone medication adherence apps: Potential benefits to patients and providers. Journal of the American Pharmacists Association, 53(2), 172-181. https://doi.org/10.1331/JAPhA.2013.12202
Google. (2026). Material Design for Android. Android Developers. https://developer.android.com/develop/ui/views/theming/look-and-feel
Kotlin. (2025). Kotlin for Android. Kotlin Documentation. https://kotlinlang.org/docs/android-overview.html
