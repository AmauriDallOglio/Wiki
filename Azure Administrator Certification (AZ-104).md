
# Cloud First e Administração de Serviços de Nuvem

Tem um termo que está ficando cada vez mais popular nesse momento e esse termo é o **Cloud First**. O que ele prega é justamente explorar os recursos que a nuvem oferece antes de sair desenvolvendo alguma coisa do zero. Dentro do serviço da nuvem, temos várias ferramentas prontas, vários modelos e sistemas que se integram entre si para que seja possível criar uma solução mais escalável, com uma infraestrutura flexível e fácil de lembrar. É importante lembrar desse termo, pois nele você encontra recursos que estão sempre sendo atualizados, com novas ferramentas surgindo constantemente. Assim, você tem hoje um ambiente muito rico para desenvolvimento, que não depende apenas de código como era antigamente. É por isso que as empresas estão cada vez mais se baseando em aplicações totalmente feitas na nuvem.

Esse cenário emenda em um segundo termo, o **Cloud Native Applications**, que são aplicações construídas nativamente na web. Desde o banco de dados até funções de API, tudo é 100% em serviços de nuvem. Não há nada fora da nuvem. Cada vez mais empresas estão baseando o core de seus negócios dentro desses serviços. A grande vantagem disso é contar com um ecossistema apoiado por uma gigante como a Microsoft, que oferece suporte robusto e confiável. Não estamos falando de qualquer empresa, mas de uma das titãs colossais do mundo da tecnologia. Esse modelo inspira empresas mundo afora, seja em ambientes híbridos ou totalmente em nuvem.

---

# O Papel do Administrador de Cloud

Nesse contexto surge um cargo muito importante: o **Administrador de Serviços de Cloud** (ou Cloud Manager). Esse profissional é responsável por monitorar o que outras pessoas estão fazendo com a nuvem dentro da empresa. Imagine uma organização onde todas as áreas utilizam serviços de nuvem, cada uma de forma diferente. Sem controle, isso se tornaria caótico. É aí que entra o administrador, garantindo organização e governança.

As responsabilidades incluem gerenciar quem pode ter acesso a quê, monitorar atividades, criar relatórios inteligentes, configurar alertas, movimentar backups corretamente e controlar custos da nuvem. O administrador deve extrair o melhor que a nuvem tem a oferecer sem prejudicar outros times ou clientes finais.

---

# Habilidades Necessárias

Além de gerenciar usuários e permissões, o administrador precisa identificar gargalos e otimizar soluções. Ele deve avaliar se o banco de dados utilizado é o mais adequado, se as integrações estão funcionando da melhor forma e se há intermediários desnecessários. Hoje vivemos na era das **IaaS**, onde não apenas pessoas e APIs interagem com a nuvem, mas também agentes autônomos que tomam decisões e fazem solicitações de recursos. O administrador deve garantir previsibilidade em custos, segurança e governança.

Outras habilidades incluem cuidar da camada de rede virtual, aplicar boas práticas de mercado, escolher o melhor tipo de armazenamento para diferentes dados (arquivos, vídeos, áudios), configurar máquinas virtuais de forma otimizada e flexível, criar backups eficientes e utilizar ferramentas de monitoramento. É essencial saber analisar logs, criar alertas e configurar o **Azure Monitor** para acompanhar recursos consumidos e oferecidos.

---

# Certificação e Carreira

Esse conteúdo prepara você para se tornar um administrador de nuvem e conquistar certificações oficiais da Microsoft, como a **AZ-104** e a **AZ-164**, ambas de reconhecimento internacional. Essas certificações validam habilidades práticas e teóricas, cobrindo desde governança e identidade até armazenamento, redes virtuais e monitoramento. Elas são intensas e exigem dedicação, mas representam um divisor de águas na carreira de profissionais de tecnologia.

---

# Roteiro de Aprendizagem Entra ID

Iniciando o conteúdo do primeiro módulo, vamos falar sobre a parte de identidade dentro do cenário do **Microsoft Azure**. É importante entender como funcionará o roteiro de aprendizagem. O **Módulo 1** é dividido em dois capítulos: a configuração do **Microsoft Entra ID** e a configuração de contas de usuário e de grupo. Assim, este módulo é estruturado em dois grupos de conhecimento, e começamos pela primeira parte: a configuração do Microsoft Entra ID.

Neste objetivo de aprendizagem, é essencial compreender os benefícios e recursos do **Microsoft Entra ID** e também comparar como funciona a autenticação na nuvem em relação à autenticação em ambientes antigos, conhecidos como **on-premises**. É necessário entender como fazer com que esses ambientes coexistam, quais estratégias podem ser utilizadas, quais são as diferenças de protocolos entre um e outro e outros fatores relevantes. Além disso, é importante conhecer como funcionam os planos de preço, lembrando que na nuvem existem cenários em que se paga por licenciamento. Assim, é preciso compreender quais modelos existem e como configurar identidades em dispositivos, além de entender como funciona a implementação de senha por autoatendimento, conhecida como **SSPR (Self-Service Password Reset)**.


# Benefícios e Recursos do Entra ID

Falando sobre os benefícios e recursos do **Entra ID**, existe um detalhe importante: muitas vezes as pessoas não têm certeza se o ambiente precisa ser movido totalmente para a nuvem ou se é possível mantê-lo coexistindo com o ambiente on-premises. Surge também a dúvida de como trabalhar a questão das autenticações e autorizações, lembrando que autenticação e autorização são processos diferentes.

Imagine um cenário em que existe um ambiente on-premises, com uma empresa que possui seu prédio, data center e vários servidores. O usuário chega, faz login em sua máquina e tudo funciona corretamente. Agora, em um ambiente de nuvem, é necessário criar os usuários diretamente na nuvem e replicar esses usuários para lá. Quando eles se autenticam, a autenticação acontece na nuvem. Esse processo pode parecer confuso, mas é justamente aí que entra o Entra ID.

O **Entra ID** nada mais é do que a família de produtos relacionados à autenticação da Microsoft. Antes, conhecíamos o **Active Directory** e, até pouco tempo atrás, dentro da plataforma do Azure, existia o **Azure Active Directory**, semelhante a uma floresta de diretórios. A Microsoft evoluiu esse conceito e criou uma suíte de aplicações voltadas para usuários e autenticação. Por exemplo, se existe um cargo de administrador de usuários, não é necessário acessar outros recursos, apenas o próprio Entra ID. Assim, temos uma plataforma exclusiva para essa tecnologia.

Quando trabalhamos com ambientes de nuvem utilizando o Entra ID, temos um conjunto de recursos modernos que ajudam no gerenciamento de acessos e promovem segurança aos serviços e recursos por meio dos usuários. Comparando com o ambiente on-premises, toda autenticação passa por protocolos como **Kerberos** e **NTLM**. Digamos que você trabalha em uma empresa, chega pela manhã, insere usuário e senha, e o servidor local (Windows Server com Active Directory) valida suas credenciais. Esse é o modelo legado de autenticação.

Já na nuvem, o representante das autenticações é o **Microsoft Entra ID**, que utiliza protocolos modernos como **OAuth**, **SAML** e **OpenID Connect**. É como comparar redes sociais de gerações diferentes: o Orkut com o TikTok. Para que ambos coexistam e colaborem, é necessário uma aplicação que traduza essas informações, e veremos nos próximos módulos como isso funciona.

Dentro desse cenário, é possível manter o ambiente on-premises trabalhando com o modelo legado e o Entra ID trabalhando com o modelo moderno. É importante eleger quem será o responsável principal pela autenticação: os usuários podem cair no Entra ID ou no Active Directory. Essa é uma estratégia de adoção e integração na nuvem que precisa ser definida. Em muitos ambientes, o Active Directory on-premises é mantido como principal, e o Entra ID como backup, caso haja perda de comunicação com o ambiente físico. Isso depende muito do cenário.

Entre os benefícios da utilização do Entra ID estão o gerenciamento de aplicativos, autenticação, gerenciamento de dispositivos e identidade híbrida. Uma identidade híbrida é aquela que coexiste tanto no ambiente on-premises quanto na nuvem. As aplicações modernas fazem comunicação via API, algo que não é compatível com ambientes mais antigos. Por isso, utilizar o Entra ID promove usabilidade e integração com plataformas e recursos atualizados.


# Conceitos do Entra ID

Trazendo para um cenário de conceitos, é importante entender algumas coisas. Por exemplo, uma identidade não necessariamente está associada a uma pessoa, mas também pode ser a um dispositivo. A descrição de identidade nos diz que ela é um objeto que pode ser autenticado. Mais adiante veremos que, por exemplo, o computador pode ser autenticado na rede, pois ele passa por um processo de conexão onde esse recurso é autorizado a acessar o ambiente da empresa. Portanto, a identidade é de fato algo ou alguém que pode ser autenticado.

A conta, por sua vez, será uma identidade que possui dados associados a ela. Podemos falar, por exemplo, da conta do **Microsoft Entra ID**, que é uma identidade criada na nuvem. Essa conta pode ser criada por um serviço de nuvem da Microsoft ou até mesmo para uma finalidade específica.

Outro conceito importante é o **locatário** (tenant). Muitas pessoas têm dúvidas quando começam a trabalhar com nuvem, pois possuem uma conta e também um locatário associado. A diferença é que o locatário é a instância dedicada onde os recursos são criados e gerenciados. Essa instância representa a organização. Por exemplo, ao criar uma conta no **Microsoft Azure**, automaticamente é gerado um domínio associado a essa conta. É possível ter diretórios diferentes para separar serviços, e nesses diretórios são associadas assinaturas. Cada assinatura é responsável pelo pagamento dos recursos utilizados.

Imagine que existe uma conta principal e, dentro dela, várias assinaturas. É possível alternar entre essas assinaturas para distribuir serviços, separando-os por modelos de teste, produção ou homologação. Também é possível separar por setores, dependendo da estratégia da empresa. Esse modelo garante organização e flexibilidade na gestão de recursos dentro da nuvem.


# Entra ID vs Active Directory Domain Services (AD DS)

Continuando, é necessário comparar o cenário dos serviços. Quando falamos sobre o **Entra ID** e o **Active Directory Domain Services (AD DS)**, o mais antigo, precisamos entender que o Entra ID está sempre relacionado a soluções mais modernas. Antes de mais nada, ele é uma solução de identidade, centralizando o gerenciamento de usuários, grupos e dispositivos dentro do ambiente.

Um ponto importante é que o Entra ID trabalha em cima de autenticação **HTTP/HTTPS**, pois a maioria das aplicações modernas utiliza o protocolo REST para realizar conexões. Além disso, o Entra ID utiliza protocolos atualizados como **WS-Federation**, **OpenID Connect** e **OAuth** para autenticação e autorização. Já o AD DS não enxerga esses protocolos, pois trabalha com **Kerberos** e **NTLM**, que são modelos legados. Em provas de certificação, por exemplo, pode ser perguntado qual tipo de autenticação é utilizado, e a resposta pode estar relacionada a esses protocolos modernos ou legados.

Outro ponto relevante é a integração com serviços de terceiros, como o próprio Facebook. Imagine que você está criando uma aplicação e não deseja obrigar o usuário a criar uma conta específica para acessá-la. Nesse caso, é possível autorizar o login utilizando uma conta de outro serviço, como o Facebook. Essa estratégia é chamada de **federation**, permitindo autenticação baseada em credenciais externas.

Existe também um detalhe que causa confusão para quem está começando a estudar o assunto. No AD DS, temos uma árvore de domínio com unidades organizacionais (OUs), que funcionam como pastas para separar usuários por setores, permissões e recursos de rede. Já no Entra ID, essa estrutura não existe. Na nuvem, temos uma **estrutura plana**, onde todos os usuários ficam no mesmo nível, sem subdivisões em pastas. Se você criar cinquenta ou cem usuários, todos aparecerão enfileirados no mesmo repositório.

Outro ponto importante são os **objetos de política de grupo (GPOs)**. No AD DS, era comum aplicar GPOs para definir regras nos computadores dos colaboradores, como alterar planos de fundo, restringir acesso ao CMD ou ao Painel de Controle. No Entra ID, isso não funciona da mesma forma. Os ajustes relacionados às máquinas dos colaboradores são feitos diretamente na plataforma **Microsoft 365** e ferramentas associadas. As políticas do Entra ID estão relacionadas a recursos da nuvem, não a configurações locais de dispositivos.

Por exemplo, se uma empresa no Brasil deseja que todos os recursos criados no Azure sejam apenas na região do Brasil, é possível criar uma política que bloqueie a criação de recursos em outras regiões. Essa política será aplicada independentemente de quem esteja tentando criar o recurso, sem considerar cargo ou permissões individuais. As políticas no Azure são voltadas para recursos e assinaturas, e não para pessoas. Essa é uma estratégia totalmente diferente da utilizada no Active Directory tradicional.


# Planos e Preços do Entra ID

Um ponto importante, que inclusive entra no contexto de prova, são os **planos e preços do Entra ID**. Existem quatro modelos: **Gratuito**, **P1**, **P2** e **Governança**. Os planos P1 e P2 são os que mais costumam aparecer em provas, sendo o P2 o mais completo, liberando praticamente todos os recursos. É interessante conhecer os recursos de cada plano e entender a relação com os tipos de licenciamento.

O **logon único e ilimitado** está disponível nos três primeiros modelos. O plano de Governança é utilizado apenas em cenários de auditoria e gestão, não necessariamente para atribuir funcionalidades aos usuários. O logon único significa que, ao desbloquear o computador com usuário e senha, não é necessário reinserir credenciais ao abrir outras aplicações, como Outlook ou sistemas internos. Esse recurso evita múltiplas autenticações, mas também exige atenção à segurança.

A **autenticação na nuvem e federada** também está presente. O modelo federado, embora seguro, já não é tão utilizado, pois era adotado por empresas que começaram a migrar para a nuvem há mais tempo. Hoje, o modelo híbrido é mais comum, com servidores on-premises replicando para a nuvem. O modelo federado é mais caro e complexo de implementar.

O **gerenciamento avançado de grupos** está disponível apenas nos planos P1 e P2. Esse recurso permite criar grupos dinâmicos de usuários e aplicar regras específicas. Já o **portal de gerenciamento de conta de autoatendimento** está presente em todos os modelos, permitindo que usuários gerenciem suas próprias informações.

A **autenticação multifator (MFA)** é outro recurso essencial, presente em todos os planos pagos. Ela adiciona uma segunda camada de segurança, solicitando confirmação via celular ou código adicional. É imprescindível para proteger acessos, não sendo suficiente apenas a senha.

O **acesso condicional** é um recurso disponível nos planos P1 e P2. Ele permite definir regras de acesso, como restringir autenticações vindas de fora do Brasil. No plano P2, existe ainda o **acesso condicional baseado em risco**, que valida o comportamento do usuário e ajusta permissões conforme necessário.

O **provisionamento automático de usuários e grupos** para aplicativos está disponível nos planos P1 e P2, mas não no gratuito. Já o **Privileged Identity Management (PIM)**, muito citado em provas, está presente apenas no P2. O PIM é uma estratégia de segurança que concede acesso privilegiado apenas pelo tempo necessário. Ser administrador não significa ter privilégios o tempo todo. Ao entrar no ambiente, é necessário solicitar elevação de privilégio, que pode ser aprovada ou não por um responsável. Isso garante rastreabilidade, registrando quando o usuário fez login, quando solicitou acesso e por quanto tempo utilizou. Embora possa gerar atrasos caso o aprovador não esteja disponível, é considerado ideal em cenários de segurança, pois evita que contas comprometidas tenham acesso irrestrito.


# Configurar Identidades de Dispositivos

Lembre-se que a identidade não necessariamente está associada a uma pessoa, mas também pode estar associada a dispositivos. Nesse contexto, existem três categorias de configuração de identidade de dispositivos.

A primeira são os **dispositivos registrados**, conhecidos como *Bring Your Own Device (BYOD)*, ou seja, traga o seu próprio dispositivo. Imagine o seguinte cenário: você possui um telefone pessoal, comprado por você, mas trabalha em uma empresa que utiliza Microsoft. Nesse caso, você não recebe um telefone corporativo, mas pode instalar aplicativos da empresa, como Outlook ou Teams, no seu dispositivo pessoal. Surge então a dúvida: será que a empresa tem acesso às minhas fotos, mensagens ou dados pessoais? A resposta é não. A empresa não tem acesso aos seus recursos pessoais, apenas às aplicações corporativas instaladas. Se você for desligado da empresa, o acesso a esses aplicativos pode ser desativado, mesmo que estejam no seu celular. Para login, é utilizada a conta da Microsoft. Esse modelo também é compatível com computadores, especialmente em cenários de trabalho remoto, como ocorreu durante a pandemia. Nesse caso, o dispositivo pessoal é utilizado para acessar recursos corporativos, mas sem que a empresa tenha controle sobre os dados pessoais.

O segundo cenário são os **dispositivos associados**, que funcionam em conexão tanto com ambientes on-premises quanto com a nuvem, mas são focados em organizações que priorizam a nuvem. Aqui, o dispositivo é de propriedade da empresa e está autenticado diretamente no ambiente corporativo. Existe uma conta organizacional vinculada, e políticas de acesso condicional podem ser aplicadas. Esse modelo é suportado apenas em dispositivos com Windows 10 ou superior. É comum em empresas que nasceram na nuvem ou que priorizam autenticação diretamente na nuvem.

O terceiro cenário são os **dispositivos híbridos**, que se comunicam tanto com a nuvem quanto com ambientes on-premises. Esse modelo é utilizado pela maioria das empresas, pois muitas já possuem infraestrutura local consolidada e não podem migrar tudo imediatamente para a nuvem. Além disso, existem aplicações legadas que ainda dependem de protocolos antigos, como Kerberos, e não são compatíveis com autenticações modernas. Muitas dessas aplicações precisam ser reescritas para funcionar na nuvem, mas enquanto isso não acontece, o modelo híbrido é a solução mais viável. Nesse cenário, continuam sendo utilizadas políticas de grupo (GPO) para gerenciar dispositivos finais. É importante destacar que esse modelo é suportado a partir do Windows 7, diferentemente dos dispositivos associados, que exigem Windows 10 ou superior. Isso oferece maior flexibilidade para ambientes que ainda não estão totalmente atualizados.

Esses três modelos — dispositivos registrados, associados e híbridos — representam diferentes estratégias de configuração de identidade de dispositivos, permitindo que empresas escolham a abordagem mais adequada conforme suas necessidades e infraestrutura existente.



# Implementando o SSPR

Agora, não menos importante, temos a implementação do **SSPR (Self-Service Password Reset)**. Imagine o seguinte cenário: você trabalha em uma empresa e chega na segunda-feira pela manhã, desejando apenas paz. Logo cedo, começam as ligações para o departamento de TI: “Bom dia, voltei de férias e não lembro minha senha”, “Perdi o post-it onde estava anotada”, e assim por diante. A quantidade de atendimentos relacionados à troca de senhas esquecidas é enorme. Quanto maior a empresa, maior o número de chamados desse tipo.

O SSPR vem para ajudar nesse processo. Ele permite que a redefinição de senha seja feita pelo próprio usuário, sem precisar acionar o suporte técnico. Afinal, trocar a senha de alguém não torna o técnico mais inteligente, é apenas um trabalho repetitivo e pouco agregador. Com o SSPR, o usuário acessa um portal e altera sua senha sozinho, liberando o time de TI para atividades mais estratégicas.

Para implementar o SSPR, é necessário verificar a compatibilidade do licenciamento, conforme a tabela de planos. Em seguida, definir os métodos de autenticação que serão utilizados. Esses métodos podem incluir envio de código por e-mail, SMS, notificação em aplicativo móvel, telefone comercial ou perguntas de segurança. O usuário precisa configurar previamente suas informações de autenticação para comprovar sua identidade. Uma vez configurado, sempre que precisar redefinir a senha, poderá utilizar esses métodos.

As **perguntas de segurança** são um recurso que pode ser configurado, permitindo cadastrar de três a cinco perguntas. O administrador define quantas devem ser respondidas corretamente. No entanto, esse método gera debates, pois perguntas podem ser ofensivas ou inadequadas. Por exemplo, “Qual o nome da sua mãe?” pode ser problemático para pessoas adotadas, ou “Qual o nome do seu primeiro cachorro?” para quem nunca teve um animal de estimação. Por isso, muitas empresas preferem utilizar SMS ou aplicativos móveis como métodos principais. Ainda assim, em provas de certificação, é importante saber que as perguntas de segurança são uma opção válida.

---

# Planos e Preços do Entra ID

O **Microsoft Entra ID** oferece diferentes opções de licenciamento para atender às necessidades de cada organização:

- **Gratuito (Free):** recursos básicos de gerenciamento de identidade e autenticação.  
- **P1 (Premium 1):** adiciona recursos como Acesso Condicional, grupos dinâmicos e gerenciamento híbrido.  
- **P2 (Premium 2):** inclui todos os recursos do P1, além de Identity Protection e Privileged Identity Management (PIM).  
- **Governança (Microsoft Entra ID Governance):** recursos avançados de governança de identidades, como Access Reviews, Entitlement Management e Lifecycle Workflows.  

O cenário de **dispositivos híbridos** é o mais vantajoso quando a empresa utiliza tanto ambientes on-premises quanto na nuvem, precisando de integração entre ambos.

---

# Entra ID vs Active Directory Domain Services (AD DS)

Qual é a principal diferença entre o **Microsoft Entra ID** e o **Active Directory Domain Services (AD DS)?**  
O Entra ID é uma solução baseada na nuvem, enquanto o AD DS é um serviço local utilizado em ambientes on-premises.

### Explicação

A principal diferença entre os dois está em onde e como eles gerenciam identidades:

**Microsoft Entra ID**  
- Serviço de identidade e gerenciamento de acesso baseado na nuvem.  
- Utilizado para autenticar usuários em aplicativos Microsoft 365, Azure e outros serviços em nuvem.  
- Suporta recursos como Single Sign-On (SSO), Autenticação Multifator (MFA) e Acesso Condicional.  

**Active Directory Domain Services (AD DS)**  
- Serviço de diretório local (on-premises).  
- Gerencia usuários, computadores, grupos e políticas de domínio em redes corporativas.  
- Utiliza protocolos como LDAP, Kerberos e NTLM.  

---

# Objetivo do Microsoft Entra ID

O principal objetivo do **Microsoft Entra ID** dentro do gerenciamento de identidade na nuvem é oferecer uma solução moderna de autenticação e autorização baseada em nuvem, centralizando o gerenciamento de identidades.

O Microsoft Entra ID (antigo Azure Active Directory) é um serviço de gerenciamento de identidade e acesso baseado em nuvem que permite:

- Centralizar a autenticação e autorização de usuários, grupos e aplicativos.  
- Implementar **Single Sign-On (SSO)**.  
- Utilizar **Autenticação Multifator (MFA)**.  
- Aplicar **Acesso Condicional (Conditional Access)**.  
- Integrar aplicações locais (on-premises) e em nuvem.  
- Coexistir com o Active Directory local por meio de sincronização, utilizando o **Microsoft Entra Connect**.  


# Criação da Conta

Primeiro laboratório do **Módulo 1 do curso AZ-104**. Neste laboratório vamos fazer uma visão geral sobre as principais funcionalidades do **Microsoft Entra ID**, antigo Azure Active Directory. Vamos observar que, na prática, apenas o nome mudou, pois as funcionalidades continuam as mesmas. O objetivo será criar duas contas de usuário: uma diretamente no Entra ID e outra como uma conta de computador. Este primeiro laboratório é mais tranquilo, mas já quero deixar um recado importante.

Caso você já tenha uma conta no Azure, sugiro que crie uma conta nova. Sei que dá um pouco de trabalho, mas é recomendável criar um cartão de crédito virtual, uma conta de e-mail nova e até cadastrar um número de telefone diferente, que não tenha sido utilizado antes, para garantir que você consiga ativar a conta de avaliação de 30 dias. Por que isso é necessário? Porque no Entra ID temos uma questão particular relacionada às licenças. Ao criar uma conta nova, ela vem como gratuita (Free), mas é possível adicionar uma licença do modelo **P2**, que permite configurar recursos como o **Self-Service Password Reset (SSPR)**, além de várias outras funcionalidades.

Mesmo sem uma conta paga, o Azure concede créditos para utilizar recursos durante o período de avaliação. No entanto, após os 30 dias, não é possível reativar a licença P2 sem pagamento. Por isso, criar uma conta nova é a melhor estratégia para acompanhar os laboratórios. Se você já possui uma conta antiga, provavelmente ela está no modelo gratuito, e assim não será possível acompanhar alguns exercícios. Minha sugestão é assistir ao vídeo de criação de conta disponível na plataforma e, se necessário, criar uma nova conta de e-mail, configurar um cartão de crédito virtual e utilizar um número de telefone diferente apenas para receber o SMS de confirmação. Dessa forma, você garante que terá acesso completo aos recursos necessários.

Durante o curso, utilizaremos essa conta para realizar todos os laboratórios. Pode haver situações em que algum recurso, como máquinas virtuais, não esteja disponível em determinada região, mas isso é normal e faz parte da prática. O importante é que, com essa conta de avaliação, você conseguirá acompanhar todas as configurações e exercícios propostos. Portanto, se tiver dúvidas sobre como criar a conta, assista ao vídeo explicativo na plataforma e siga o procedimento.  


# Overview (Logs e Reset de Senha)

Como comentei anteriormente, a única coisa que mudou em relação ao antigo **Azure Active Directory** foi basicamente o símbolo e a identidade visual. Agora temos o nome atualizado como **Microsoft Entra ID**, que representa uma suíte de gerenciamento de usuários e identidades. Na prática, as funcionalidades continuam as mesmas, apenas com nomenclatura diferente. Essa mudança impacta mais em representações visuais, como diagramas de arquitetura, do que em funcionalidades reais.

Ao criar uma conta no Microsoft Entra ID, ela vem configurada com um diretório padrão, chamado **Tenant**. Esse tenant é utilizado frequentemente quando criamos recursos em plataformas como Terraform ou ARM templates, pois muitas vezes é necessário informar esse nome. O domínio inicial criado é baseado no e-mail utilizado para registrar a conta, geralmente no formato `nomedousuario.onmicrosoft.com`. Esse domínio é o primeiro ponto que gera dúvidas, pois muitos se perguntam como criar usuários utilizando esse domínio e como manter a personalização. É possível adicionar um domínio customizado, como `minhaempresa.com.br`, para que os usuários façam login com o e-mail corporativo. No entanto, o domínio inicial não deixa de existir, ele permanece como opcional.

Na prática, podemos validar e adicionar nomes customizados ao domínio, mas o domínio padrão sempre estará presente. Esse é um ponto importante que costuma aparecer em provas de certificação.

Dentro do Entra ID, temos diversas funcionalidades. Na parte de **usuários**, inicialmente aparece apenas o usuário proprietário da conta, que é o administrador principal. Esse usuário é membro do ambiente e responde por todos os recursos. Também existe a seção de **auditoria de logs**, que mostra os acessos realizados. Por padrão, os logs exibem os últimos sete dias, mas é possível alterar para intervalos diferentes, como últimas 24 horas ou períodos maiores. É possível aplicar filtros para validar atividades específicas, como acessos de usuários convidados ou serviços utilizados.

Outro recurso importante é a seção de **usuários deletados**. Quando um usuário é excluído, ele não desaparece imediatamente. Existe um período de 30 dias em que é possível restaurar a conta. Após esse prazo, o usuário é permanentemente removido. Esse detalhe é relevante tanto para o dia a dia quanto para provas, pois é necessário saber que existe essa janela de restauração.

Além disso, o Entra ID oferece a funcionalidade de **reset de senha em modo self-service (SSPR)**. Isso significa que o próprio usuário pode redefinir sua senha sem precisar acionar a equipe de TI. Essa autonomia reduz a carga de trabalho do suporte e agiliza o processo para o usuário final. O administrador pode configurar os métodos de autenticação disponíveis, como SMS, e-mail, aplicativo móvel ou perguntas de segurança. Assim, o usuário consegue redefinir sua senha de forma independente.

Outras funcionalidades incluem operações em lote, permitindo gerenciar múltiplos usuários de uma vez, e configurações adicionais de auditoria e segurança. O Entra ID, portanto, centraliza o gerenciamento de identidades, oferecendo recursos modernos de autenticação, autorização e administração de usuários.


# Overview (Grupos, Roles e Acessos)

Existe a parte de **grupos**, lembrando que os grupos aqui são diferentes dos grupos em ambientes on-premises. Ao criar um novo grupo, é possível escolher entre **grupo de segurança** ou **grupo do Microsoft 365**. O grupo do 365 é utilizado quando se deseja ter um espaço de interação, como chats e colaboração entre pessoas, por exemplo, um grupo de tecnologia. Já o grupo de segurança é voltado para atribuição de funções e permissões em recursos. Essa diferença é importante e costuma aparecer em provas de certificação.

Ao configurar um grupo do 365, é necessário inserir nome, descrição e membros. Já no grupo de segurança, além do nome e descrição, é possível definir se ele será atribuído manualmente ou dinamicamente, dependendo da licença disponível. No caso do Microsoft 365, existe ainda a opção de configurar um grupo de e-mail que receberá recursos relacionados. Também é possível definir quem são os donos e membros do grupo. Essa diferença entre grupos de segurança e grupos do 365 é um ponto de atenção.

Outro aspecto é a **identidade externa**, que permite convidar usuários para colaborar no ambiente. É possível configurar self-service para trazer usuários externos, criando contas específicas para colaboração. Além disso, existem as **roles administrativas**, que definem permissões específicas para usuários. Muitas vezes há confusão nesse ponto, pois em ambientes on-premises as permissões são atribuídas de forma diferente. No Entra ID, cada role tem funções bem definidas. Por exemplo, o administrador de helpdesk pode redefinir senhas de usuários e administradores de helpdesk, mas não pode criar grupos. Já o administrador de usuários pode gerenciar todos os aspectos relacionados a usuários e grupos, incluindo redefinição de senhas. É importante entender que essas permissões são limitadas ao escopo definido pela role.

Existe também a funcionalidade de **acesso condicional**, que garante que os usuários só consigam acessar recursos sob determinadas condições. Por exemplo, é possível configurar que o acesso só seja permitido se o IP de origem estiver dentro de uma faixa específica, como acessos realizados apenas do Brasil. No entanto, para criar políticas de acesso condicional é necessário possuir licenças Premium. Recursos como termos de uso, VPN Connect e controles customizados também dependem da versão utilizada.

Outro ponto relevante é o **Access Review**, que ajuda a manter o ambiente organizado. Quanto maior a empresa, maior a necessidade de revisar permissões. O Access Review permite que gestores recebam periodicamente uma lista de usuários e seus acessos, verificando se ainda fazem sentido. Por exemplo, um colaborador que mudou de setor pode continuar com permissões antigas que não são mais necessárias. O gestor pode revisar e solicitar a remoção desses acessos, garantindo que cada usuário tenha apenas o permissionamento adequado. Esse processo é essencial para manter a segurança e a governança do ambiente.

Portanto, os recursos de grupos, roles e acessos no Microsoft Entra ID oferecem flexibilidade e segurança, permitindo organizar usuários, atribuir permissões específicas e garantir que os acessos sejam constantemente revisados e ajustados conforme a necessidade da organização.


# Criando uma Conta de Usuário Nova

Voltando para a parte de usuários, como podemos fazer a criação de uma nova conta? Por enquanto não inserimos outros nomes de domínio, então vamos seguir com o domínio padrão. Primeiramente, é possível criar um novo usuário ou convidar um usuário externo. Vamos fazer as duas coisas, começando pela criação de um novo usuário.

O nome principal dessa pessoa será “Aspira”, nosso estagiário. O domínio utilizado será o padrão, e o nickname deriva do user principal. O display name será “Aspira da TI”. Em seguida, configuramos a senha. Por padrão, o sistema gera automaticamente uma senha inicial. É possível desmarcar essa opção e definir uma senha manual, mas de qualquer forma, no primeiro login o usuário será obrigado a alterar a senha. A prática recomendada é manter a geração automática, copiar a senha inicial e armazená-la em um bloco de notas para repassar ao usuário. Assim, no primeiro acesso ele insere a senha inicial e cria uma nova senha definitiva.

Outro ponto importante é que a conta pode ser criada habilitada ou desabilitada. Isso é útil quando recebemos dados de novos colaboradores que ainda não começaram a trabalhar. Podemos criar as contas antecipadamente, mas deixá-las desabilitadas até a data de início, garantindo segurança e evitando acessos indevidos. Da mesma forma, contas externas podem ser criadas desabilitadas para impedir login até que sejam necessárias.

Na configuração de identidade, o **User Type** será “Member”, e podemos adicionar informações como cargo, empresa e departamento. No caso do Aspira, será estagiário da TI. Existe também a configuração de **User Location**, que define a localidade do usuário. Embora não seja obrigatória, é altamente recomendada. Essa informação é utilizada em regras de segurança, como bloqueio de login por região ou validação de acessos. Por exemplo, se definirmos que usuários só podem acessar do Brasil, o sistema precisa saber a localidade configurada para validar. Além disso, em cenários de licenciamento, a ausência dessa informação pode causar erros na atribuição de licenças. Já houve casos em que a ativação de licenças falhou porque o campo de localidade não estava preenchido. Portanto, sempre configure a localidade corretamente.

Após definir essas informações, é possível adicionar o usuário a grupos, roles e unidades administrativas. No caso do Aspira, não foram atribuídas regras adicionais. Finalizando, basta confirmar a criação e a conta é gerada rapidamente. Assim, temos o novo usuário “Aspira da TI” criado e pronto para ser utilizado.



# Criando um Invite External User

Como havia comentado, também é possível fazer um **invite de usuários externos**. Para isso, utilizamos um e-mail externo e seguimos o processo de criação de um usuário convidado. A primeira etapa é convidar o colaborador externo, inserindo o e-mail da pessoa e definindo o display name. É possível personalizar a mensagem de convite, tornando-a mais amigável, como “Você está sendo convidado a participar e acessar os recursos da organização”.

Após configurar, basta avançar e concluir o convite. O usuário externo será criado como **Guest**, enquanto os usuários internos permanecem como **Members**. No exemplo, temos o usuário interno “Aspira” e o usuário externo “Valéria XP”, que aparece como convidado. O sistema envia um e-mail padrão informando que o usuário foi convidado para acessar aplicativos da organização. Esse e-mail contém o domínio padrão e a mensagem de convite, permitindo que o usuário aceite e passe a ter acesso.

Ao aceitar o convite, o usuário externo consegue acessar o diretório principal e visualizar algumas informações. No entanto, como não possui licenças ou permissões atribuídas, não terá acesso a recursos adicionais. Ele pode ver a estrutura básica, mas não consegue criar novos usuários ou realizar ações administrativas. O acesso é limitado a visualização, até que sejam atribuídas permissões específicas.

Esse processo demonstra como funciona a criação de uma conta externa via invite. É importante lembrar que, sem licenciamento adequado, o usuário convidado terá acesso restrito. Para que ele possa participar de forma mais ativa, será necessário configurar permissões e licenças adicionais. Esse será o próximo passo, pois sem trocar o modelo de licença não será possível avançar em alguns laboratórios. Portanto, é recomendável que você já tenha criado sua conta nova e esteja preparado para os próximos conteúdos, que exigirão acesso mais privilegiado.


# Conta, Usuários e Grupos

Como comentei anteriormente, o fato de termos acesso ao **Active Directory** na nuvem, que agora possui a nomenclatura de **Microsoft Entra ID**, não significa que a criação de contas será feita exclusivamente na nuvem. Muito pelo contrário: se você possui um ambiente físico com data center e servidores dentro da sua empresa, o ideal é que seja feita uma **sincronização das contas**. Dessa forma, os usuários continuam sendo criados no ambiente on-premises e são replicados automaticamente para a nuvem. É assim que funciona na prática.

Ainda assim, é possível criar usuários diretamente na nuvem ou dar acesso a usuários que não existem no ambiente on-premises. Esses casos são específicos e atendem a necessidades pontuais. Na tela de gerenciamento de usuários, percebemos que os nomes de exibição seguem um padrão. Esse padrão, chamado de **UPN (User Principal Name)**, é gerado automaticamente quando criamos a conta no Entra ID. Ele geralmente assume o formato `usuario@onmicrosoft.com`, que pode não ser muito familiar ou amigável. Esse UPN padrão não pode ser alterado, mas é possível adicionar um domínio da empresa para que novos usuários sejam criados com endereços mais adequados, como `usuario@minhaempresa.com`.

Outro ponto importante é que podemos ter **usuários convidados**. Por exemplo, em uma auditoria, uma pessoa externa pode precisar acessar o ambiente por um período específico. Nesse caso, não é necessário criar uma conta permanente para ela. O ideal é convidar esse usuário externo, atribuir as permissões necessárias e, após o término da atividade, encerrar o acesso. Isso evita acúmulo de contas desnecessárias e melhora a gestão de segurança.

Independentemente do tipo de usuário — seja membro, convidado ou replicado do ambiente on-premises — todos precisam ter uma conta registrada para conseguir acessar o portal. Cada conta possui propriedades associadas, como informações de perfil e licenciamento. Essas contas são utilizadas tanto para **autenticação** quanto para **autorização**. A autenticação garante que o usuário e senha estão corretos, enquanto a autorização define o que esse usuário pode ou não fazer dentro do ambiente.

Portanto, a gestão de contas, usuários e grupos no Microsoft Entra ID é fundamental para manter a organização, segurança e eficiência do ambiente de nuvem, integrando-se de forma prática com ambientes locais e permitindo flexibilidade para diferentes cenários.


# Gerenciar Contas de Usuário

No gerenciamento de contas de usuário, é possível criar novos usuários, realizar criação em massa, convidar usuários externos, excluir usuários em massa e até mesmo fazer o download da lista de usuários para validação. Ao criar uma nova conta, podemos optar por criar um usuário da organização ou convidar um usuário externo. Essa última opção é utilizada quando queremos dar acesso a alguém que não faz parte da empresa, como um colaborador temporário ou auditor.

É importante lembrar que, se o ambiente não for 100% na nuvem, a criação de usuários deve ser feita no ambiente on-premises, que então replica para a nuvem. O processo funciona sempre dessa forma: do on-premises para a nuvem, e nunca o inverso. Portanto, se alguém criar um usuário diretamente na nuvem em um ambiente híbrido, esse usuário não aparecerá no ambiente local. Nesse caso, o procedimento correto é excluir o usuário criado na nuvem e refazer a criação no ambiente on-premises, aguardando a replicação.

Outro ponto relevante é o gerenciamento do **MFA (Multi-Factor Authentication)**. Essa configuração determina que, além da senha, o usuário precisa confirmar sua identidade por meio de um segundo fator, como um celular, garantindo maior segurança no acesso ao sistema.

No contexto de administração, quem consegue gerenciar contas de usuário são os administradores com permissões específicas. Existem duas permissões principais: **Administrador Global** e **Administrador de Usuários**. O Administrador Global possui acesso amplo e generalista, não limitado apenas à gestão de contas de usuário, enquanto o Administrador de Usuários tem acesso restrito apenas à gestão de contas. Por questões de segurança, geralmente as empresas preferem atribuir a permissão de Administrador de Usuários, evitando conceder privilégios excessivos.

Também é possível adicionar informações adicionais ao perfil do usuário, como cargo e dados de contato. Embora sejam opcionais, quanto mais informações o usuário tiver registradas, melhor será a gestão. Outro ponto importante são os **usuários excluídos**. Quando uma conta é excluída, existe um período de até 30 dias em que ela pode ser restaurada. Após esse prazo, a conta é permanentemente removida. Esse detalhe é relevante tanto para o dia a dia quanto para provas de certificação, pois é comum aparecer questões relacionadas a esse prazo de restauração.

Além disso, é possível validar **logs de auditoria** relacionados à autenticação. Esses registros são fundamentais para acompanhar acessos realizados pelos colaboradores e identificar comportamentos suspeitos. Por exemplo, se um usuário acessa fora do horário de trabalho, é possível verificar se foi realmente ele ou se a conta foi comprometida. O acesso aos logs de auditoria é essencial tanto para monitoramento interno quanto para segurança do ambiente.

Portanto, o gerenciamento de contas de usuário no Microsoft Entra ID envolve criação, exclusão, replicação, configuração de MFA, atribuição de permissões administrativas e análise de auditoria. Esses processos garantem organização, segurança e eficiência na gestão de identidades dentro da nuvem.


# Execute Atualizações em Massa

Aqui temos um cenário de **atualizações em massa**. Como isso funciona? Imagine que você trabalha em uma empresa multinacional ou de grande porte e precisa, de repente, adicionar uma lista de 30, 50 ou até 100 pessoas. Esses usuários podem ser convidados externos ou novos colaboradores. Também pode ser necessário realizar exclusões em massa dentro do **Active Directory na nuvem (Microsoft Entra ID)**.

É importante lembrar que, se você excluir um usuário em um ambiente sincronizado, essa exclusão deve ser feita no **AD on-premises**, pois ele replica para a nuvem. No entanto, quando falamos de usuários nativos da nuvem ou convidados externos (invites), podemos realizar esse processo diretamente no Entra ID. Esse procedimento é chamado de **bulk operation** quando utilizamos o ambiente em inglês.

No portal, é possível criar novos usuários, fazer download da lista de usuários com suas configurações de perfil e realizar tanto a criação quanto a exclusão em massa. O processo funciona da seguinte forma: baixamos um modelo em formato **CSV** (semelhante a um Excel, mas com parâmetros específicos separados por vírgulas ou ponto e vírgula). Esse arquivo contém a estrutura necessária para que os dados sejam interpretados corretamente. Após substituir as informações no modelo, basta carregar o arquivo no portal e o sistema executa automaticamente a criação ou exclusão dos usuários.

Esse recurso é bastante útil em situações como auditorias. Por exemplo, se a empresa vai receber dez auditores temporários, é possível adicionar todos de uma vez utilizando o modelo CSV. Após o término da auditoria, o mesmo arquivo pode ser utilizado para realizar a exclusão em massa, sem necessidade de excluir cada usuário individualmente. Isso torna o processo muito mais rápido e eficiente.

As atualizações em massa podem ser aplicadas tanto para usuários quanto para membros de grupos. No entanto, é fundamental lembrar que para realizar essas operações é necessário possuir permissões adequadas, como **Administrador Global** ou **Administrador de Usuários**. Somente essas permissões permitem executar esse tipo de gestão. O modelo CSV, baixado diretamente do portal, é a ferramenta que possibilita organizar e executar essas operações de forma prática e segura.


# Criar Contas de Grupo

Com relação às contas de grupo, nós temos dois modelos principais: **grupos de segurança** e **grupos do Microsoft 365**. Esses modelos de contas são bastante utilizados no dia a dia e também são frequentemente cobrados em provas de certificação. É importante lembrar que, diferentemente do **Active Directory local**, no Entra ID não existe hierarquia de unidades organizacionais. Todos os usuários e grupos estão em um mesmo plano, sem subdivisões estruturais.

Os grupos servem para dois estilos de trabalho distintos. Os **grupos de segurança** são utilizados principalmente em cenários de permissões e licenciamentos. Eles permitem atribuir acessos específicos a usuários e dispositivos, garantindo que apenas quem precisa tenha acesso a determinados recursos. Já os **grupos do Microsoft 365** são voltados para colaboração entre setores. Esses grupos permitem criar espaços de interação, como equipes no Microsoft Teams, onde os membros podem se comunicar e compartilhar informações de forma integrada.

Um ponto importante é o modelo de atribuição. Por exemplo, se temos um usuário chamado Valéria, que pertence ao setor de Tecnologia (TI), podemos configurar uma regra dinâmica para que todos os usuários desse setor sejam automaticamente adicionados ao grupo correspondente. Esse é o chamado **modelo dinâmico de atribuições**. Assim, se Valéria mudar de setor, passando para Contabilidade, ela será automaticamente removida dos grupos de TI e adicionada aos grupos de Contabilidade. Esse modelo garante que os grupos estejam sempre atualizados conforme as mudanças de perfil dos usuários.

Existe também o **modelo atribuído**, onde os usuários são adicionados manualmente aos grupos. Esse modelo pode ser utilizado, mas em organizações muito grandes torna-se arriscado, pois é fácil esquecer de adicionar ou remover alguém. O modelo dinâmico, por outro lado, automatiza esse processo com base em regras definidas.

Além disso, é possível utilizar **dispositivos dinâmicos** em grupos de segurança. Como os dispositivos também podem ser autenticados no ambiente, eles podem ser adicionados a grupos de segurança para receber políticas e permissões específicas. No entanto, dispositivos não podem ser adicionados a grupos do Microsoft 365, já que esses grupos são voltados para interação entre pessoas.

Portanto, os grupos no Microsoft Entra ID são ferramentas essenciais para organizar permissões e colaboração. Os grupos de segurança garantem controle de acesso, enquanto os grupos do Microsoft 365 promovem integração entre equipes. A escolha entre atribuição manual ou dinâmica depende do tamanho da organização e da necessidade de automação no gerenciamento de usuários e dispositivos.



# Atribuir Licenças a Usuários e Grupos

No Microsoft Entra ID, temos diferentes modelos de licenciamento. Existe o modelo gratuito, que oferece funcionalidades básicas, e também os modelos **P1** e **P2**, que adicionam recursos mais avançados. Além disso, existem serviços adicionais relacionados, que podem ser exigidos ou não dependendo do tipo de acesso que se deseja conceder.

É possível trabalhar com mais de um modelo de licença relacionado ao Microsoft 365. Por exemplo, algumas pessoas podem receber a licença **E5**, que é a mais completa e inclui todas as funcionalidades, enquanto outras podem receber a licença **E3**, que possui menos recursos. Dessa forma, cada usuário ou grupo recebe a licença adequada conforme a necessidade da organização.

O processo de atribuição de licenças é simples: basta selecionar o usuário ou grupo e definir qual licença será aplicada. Essa flexibilidade permite que diferentes setores ou funções dentro da empresa tenham acesso apenas ao que realmente precisam. Além disso, quando um colaborador é desligado, a licença atribuída a ele pode ser removida e reaproveitada para outro usuário, garantindo melhor gestão dos recursos disponíveis.

Portanto, o gerenciamento de licenças no Entra ID é essencial para controlar custos, otimizar recursos e assegurar que cada usuário tenha acesso às ferramentas necessárias para desempenhar suas funções.


# Criar Unidades Administrativas

As **unidades administrativas** são uma forma de organizar melhor a empresa dentro do Microsoft Entra ID, dependendo da situação e da estrutura da organização. Elas não são equivalentes às unidades organizacionais do Active Directory local, mas cumprem um papel semelhante ao permitir uma gestão mais segmentada.

Imagine uma empresa que atua em todo o território nacional, com sede em cada capital do Brasil. Cada estado organiza seus acessos e faz a gestão de seus próprios usuários. Por exemplo, o setor de TI do Rio Grande do Sul atende apenas os colaboradores daquela localidade, sem necessidade de gerenciar usuários de outros estados. Nesse caso, é possível criar uma unidade administrativa específica para o Rio Grande do Sul, atribuindo a ela os usuários e grupos correspondentes, além de definir o escopo de permissões. Assim, o setor de TI daquela região terá autonomia para gerenciar apenas os usuários locais.

Esse modelo é o mais próximo que conseguimos chegar da estrutura tradicional do Active Directory, ainda que não seja exatamente igual. Ele permite que a gestão seja descentralizada, mas organizada, garantindo que cada equipe de TI cuide apenas da sua área de responsabilidade. Para implementar unidades administrativas, é necessário ter uma licença **P1 ou P2** do Microsoft Entra ID, além de privilégios administrativos, como o acesso de **Administrador Global**, para criar e configurar o ambiente.

É importante destacar que essa funcionalidade faz sentido principalmente em empresas de grande porte, com operações distribuídas em diferentes regiões ou países. Se a empresa possui apenas um setor de TI que atende todos os usuários, a criação de unidades administrativas não será necessária. No entanto, em cenários onde há separação por localidades ou regiões, elas são fundamentais para manter a organização e garantir que cada equipe atenda apenas os usuários sob sua responsabilidade.

Em provas de certificação, é comum aparecer questões relacionadas a esse tema. Por exemplo, pode ser apresentado um cenário em que a empresa possui operações em várias regiões e cada área de TI atende apenas sua localidade. Nesse caso, a resposta correta seria a utilização de **unidades administrativas**, pois elas permitem segmentar a gestão sem alterar a estrutura geral do ambiente.

Portanto, as unidades administrativas são uma ferramenta poderosa para empresas que precisam dividir responsabilidades de gestão de usuários e grupos por regiões ou setores, mantendo a organização e a eficiência no gerenciamento de identidades dentro da nuvem.


# Monitoramento

Iniciando administração de monitoramento. Já percorremos diversos recursos e configurações dentro do Microsoft Azure e agora vamos falar sobre ferramentas de monitoramento, análise e coleta de logs. O conteúdo é dividido em três tópicos: configuração do Azure Monitor, alertas do Azure Monitor e análise de logs. Embora seja um módulo mais curto, representa cerca de 10 a 15% da prova, portanto é essencial manter a atenção.

---

## Recursos e Componentes do Azure Monitor

Monitorar é uma necessidade em qualquer ambiente de TI. Não importa se os recursos estão na nuvem ou on-premises, eles podem sofrer indisponibilidade, lentidão ou erros de configuração. O **Azure Monitor** é a ferramenta que oferece visibilidade sobre métricas, integridade e desempenho dos recursos. Ele permite configurar alertas, coletar métricas, logs de atividades e diagnósticos, além de integrar com aplicações externas como Grafana ou Zabbix.

Entre os componentes do Azure Monitor estão:
- **Métricas**: valores numéricos que indicam o estado de um recurso.
- **Logs**: registros detalhados de eventos e atividades.
- **Insights**: visão detalhada de aplicações, redes, máquinas virtuais e containers.
- **Alertas**: notificações configuradas para eventos críticos.
- **Integrações**: possibilidade de exportar dados para hubs de eventos, aplicações externas ou armazenamentos.

O Azure Monitor coleta dados de diferentes fontes, como aplicativos, infraestrutura e plataforma, permitindo análises avançadas e respostas rápidas a incidentes.

---

## Diferença entre Métricas e Logs

É importante entender que **métricas e logs não são a mesma coisa**.

- **Métricas**: são valores numéricos que descrevem aspectos de um sistema em determinado tempo. Por exemplo, um disco com 95% de uso ou uma máquina desligada há três minutos. São dados leves, quase em tempo real, que mostram desempenho e disponibilidade.
  
- **Logs**: são registros detalhados de eventos, como autenticações, exclusões de recursos ou falhas de conexão. Contêm propriedades diversas e permitem análises mais profundas. Logs podem ser consultados no **Log Analytics**, exportados para armazenamento ou integrados com ferramentas como Power BI.

As métricas mostram números objetivos, enquanto os logs trazem mensagens e detalhes de eventos. Ambos são complementares: métricas ajudam a identificar rapidamente o estado de um recurso, e logs permitem investigar o que aconteceu em determinado momento.

---

## Exemplos de Uso

- **Métricas**: número de conexões recebidas em um e-commerce, percentual de uso de CPU ou memória de uma máquina virtual.
- **Logs**: registro de quem criou ou excluiu uma rede virtual, horário de login de um usuário, falhas em diagnósticos de aplicativos.

Os logs de atividades são especialmente importantes para auditorias, pois permitem verificar ações realizadas em recursos, identificar responsáveis e validar conformidade. É possível filtrar logs por assinatura, intervalo de tempo, severidade do evento e exportá-los para análise.

O monitoramento no Azure é essencial para garantir disponibilidade, desempenho e segurança dos recursos. Métricas e logs devem ser utilizados em conjunto para oferecer uma visão completa do ambiente. Além disso, é importante configurar alertas e definir estratégias de resposta para incidentes, garantindo que qualquer problema seja identificado e tratado rapidamente.


# Explorando o Azure Monitor na Prática

O **Azure Monitor** é um painel integrado que já está disponível no portal e cabe a nós configurá-lo. No overview, temos a parte de insights de containers, máquinas virtuais, redes e aplicações, além de informações sobre alertas e logs. É possível integrar o monitoramento com ferramentas externas como Grafana ou Prometheus, ampliando a visibilidade do ambiente. Para habilitar o monitoramento de uma máquina virtual, por exemplo, é necessário criar um workspace, que funciona como um repositório para armazenar métricas e logs. A partir daí, conseguimos coletar e analisar informações de desempenho e disponibilidade.

Além das máquinas virtuais, o Azure Monitor também permite acompanhar contas de armazenamento, containers e redes. Os **logs de atividades** registram tudo o que acontece na conta, desde criação de recursos até falhas. Outro recurso importante é o **Service Health**, que informa indisponibilidades ou manutenções planejadas nos serviços da Microsoft. Antes de alterar configurações ou assumir que o problema é interno, é essencial validar se existe algum incidente declarado no Service Health. Isso evita diagnósticos equivocados e garante maior segurança na administração.

---

# Alertas do Azure Monitor

Os alertas no Azure Monitor são baseados em métricas e logs coletados dos recursos. Eles permitem que eventos críticos sejam sinalizados para os administradores. É fundamental configurar regras de alerta para cada recurso, pois sem isso os problemas podem passar despercebidos. Por exemplo, se uma máquina virtual atingir 80% de uso de CPU ou disco, é necessário que alguém seja avisado. Caso contrário, a informação ficará apenas registrada nos logs, sem notificação.

A criação de alertas deve fazer parte de um checklist de administração, assim como backups e permissões. É preciso definir o escopo (máquina, banco de dados, rede), as condições (percentual de uso, falhas de conexão, latência) e a criticidade (informativo, warning, erro ou crítico). A partir daí, configuramos um **grupo de ações**, que determina como os responsáveis serão notificados. As notificações podem ser enviadas por e-mail, SMS, push, Teams ou até integradas com sistemas de abertura de chamados.

---

# Regras de Alerta e Grupos de Ação

As **regras de alerta** combinam recursos, sinais e condições para disparar notificações. É possível criar regras prontas para uso, como monitoramento de CPU, disco ou memória, ou configurar regras personalizadas para cenários específicos. Cada regra precisa ter um nome, escopo, condição e severidade definida. Também é possível desabilitar regras que não façam mais sentido para o ambiente.

Os **grupos de ação** são responsáveis por enviar notificações quando uma regra é acionada. É possível configurar até cinco grupos de ação por regra, permitindo que diferentes canais sejam utilizados simultaneamente. Por exemplo, um alerta pode abrir automaticamente um ticket em uma ferramenta de atendimento, enviar uma mensagem no Teams e disparar um SMS para o time de plantão. Essa flexibilidade garante que os problemas sejam comunicados rapidamente e tratados com urgência.

O monitoramento no Azure não é ativado automaticamente. É responsabilidade do administrador habilitar os recursos, configurar métricas, logs, alertas e grupos de ação. Essa prática garante que problemas sejam identificados e resolvidos antes de impactarem os usuários. Métricas e logs têm objetivos diferentes, mas complementares: métricas mostram números de desempenho, enquanto logs registram eventos detalhados. Juntos, eles oferecem uma visão completa do ambiente.

Portanto, como administradores do Azure, precisamos assumir essa responsabilidade e garantir que o monitoramento esteja ativo e configurado corretamente. Essa é uma das etapas fundamentais para manter a disponibilidade, segurança e eficiência dos recursos na nuvem.

# Criação do Log Analytics

Iniciando a parte de monitoramento, sabemos que precisamos reunir informações que podem disparar alertas com base em regras previamente determinadas. No entanto, existem situações em que é necessário analisar esses dados de forma mais minuciosa, e é aqui que entra o **Log Analytics**. Conforme os dados vão sendo armazenados, é fundamental que façamos algo com eles, evitando apenas acumular informações que consomem espaço e geram custos sem trazer valor.

O Log Analytics é um ambiente que permite consultas utilizando a linguagem **KQL (Kusto Query Language)**. Essa linguagem é utilizada para recuperar e analisar informações armazenadas no ambiente. O serviço coleta e organiza dados gerados pelos recursos e ambientes, tanto na nuvem quanto on-premises. É possível descrever consultas específicas, direcionadas a usuários, IPs ou eventos, permitindo análises detalhadas de login, atualizações de sistema, incidentes operacionais e muito mais.

Para utilizar o Log Analytics, o primeiro passo é criar um **workspace**, que funciona como um repositório de dados. Esse workspace é configurado com assinatura, grupo de recursos, nome e região. A partir dele, os dados são coletados e ficam disponíveis para consultas. É possível ter múltiplos workspaces por assinatura, conforme a necessidade da organização. Esse recurso é essencial para ferramentas de segurança como o Microsoft Sentinel, que dependem de workspaces para avaliar a segurança do ambiente.

Com o Log Analytics, é possível realizar consultas avançadas, exportar resultados para Power BI ou Excel, e até automatizar alertas com base nas análises. Exemplos incluem eventos de login do Windows, syslog do Linux, informações de agentes, vlogs personalizados e regras de alerta. A linguagem KQL é um ponto importante em provas de certificação, sendo necessário conhecer sua função e aplicação, mesmo que não seja exigido escrever consultas completas.

---

# Explorando Análise de Logs na Prática

No laboratório do módulo 11, trabalhamos com a administração de monitoramento dentro do Microsoft Azure, focando na análise de logs com o Log Analytics. Após criar o workspace, é possível acessar o serviço pelo Azure Monitor, onde encontramos logs de atividades, alertas, métricas e registros consolidados da assinatura.

O Log Analytics funciona como um container que armazena dados coletados de diferentes fontes. As consultas são feitas em **KQL**, permitindo recuperar e consolidar informações de forma rápida e precisa. Existem consultas prontas disponíveis no ambiente, mas também é possível criar consultas personalizadas para atender necessidades específicas. Isso é especialmente útil em cenários de segurança, auditoria e monitoramento de desempenho.

As consultas podem ser configuradas para rodar automaticamente, integradas a alertas, ou exportadas para ferramentas como Power BI e Excel. Exemplos de consultas incluem auditoria de monitoramento, análise de recursos, desktops virtuais, containers, bancos de dados, segurança, máquinas virtuais e workloads. É possível verificar discos livres, eventos aguardando processamento, serviços do Windows parados, entre outros.

A linguagem KQL é essencial para explorar o Log Analytics. Com ela, administradores podem buscar informações específicas, como falhas de autorização ou eventos críticos, e consolidar dados por usuário, recurso ou período de tempo. Embora algumas consultas já estejam disponíveis, é importante saber como criar novas, adaptando-se às necessidades do ambiente.

Portanto, o Log Analytics é uma ferramenta poderosa para coleta, análise e consulta de dados no Azure. Ele permite que administradores tenham maior controle sobre o ambiente, identifiquem problemas rapidamente e tomem decisões baseadas em informações detalhadas e confiáveis.



