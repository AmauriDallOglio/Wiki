
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



