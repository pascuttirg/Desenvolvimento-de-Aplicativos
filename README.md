# Desenvolvimento-de-Aplicativos
Repositório criado para o acompanhamento do desenvolvimento do projeto final da matéria.

Aqui será desenvolvido um aplicativo mobile voltado para o dia a dia das mulheres, auxiliando no controle de ingestão de contraceptivos.

Criado o nome do aplicativo, será "Já Tomei", um aplicativo para lembrar as mulheres de tomarem o seu contraceptivo, auxiliando no não esquecimento do medicamento.

Projeto de desenvolvimento mobile “Já Tomei”

# Progresso do Desenvolvimento

Status atual: **Versão 1.2**

| Versão | Status | Descrição |
|--------|--------|-----------|
| 1.0 | V | Definição da proposta do aplicativo, elaboração da documentação inicial, wireframe manual e refinamento do wireframe digital. |
| 1.1 | V | Criação do projeto Android, definição da arquitetura MVVM, navegação entre telas, construção da interface principal, componentes reutilizáveis, testes do cálculo do ciclo e estrutura inicial do banco de dados Room. |
| 1.2 | V | Implementação da persistência do ciclo contraceptivo utilizando Room Database, criação do Repository e ViewModel, desenvolvimento da tela funcional de configuração do ciclo, validação dos dados informados e armazenamento permanente das configurações da usuária. |
| 1.3 |  | Integração do calendário principal com os dados reais do ciclo contraceptivo. |
| 1.4 |  | Implementação das notificações inteligentes e confirmação da tomada da medicação. |
| 2.0 |  | Primeira versão completa do aplicativo, contemplando todas as funcionalidades propostas no projeto acadêmico. |

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

# Roadmap

- [x] Planejamento do aplicativo
- [x] Wireframes
- [x] Estrutura inicial do projeto
- [x] Arquitetura MVVM
- [x] Persistência com Room
- [x] Cadastro do ciclo contraceptivo
- [ ] Calendário inteligente
- [ ] Notificações automáticas
- [ ] Confirmação da tomada
- [ ] Histórico de utilização
- [ ] Configurações do aplicativo
- [ ] Versão final (v2.0)

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
