## Meus Projetos

### Em 2022-1

<div align="justify">

No primeiro semestre de 2022, desenvolvemos a assistente virtual BETA, que tinha como objetivo ajudar alunos em seus estudos diários com funcionalidades como: modo pomodoro, consulta à Wikipedia, reprodutor de música, gravação de voz, gerenciamento de calendário, anotações, lembretes, calculadora e informações sobre o clima. Seguindo a metodologia Scrum em três sprints, o projeto focou em responder a comandos de voz e operar em múltiplas plataformas. Utilizamos Python, HTML e CSS para desenvolvimento e documentamos todo o processo no GitHub. A interface foi desenhada para ser intuitiva e visualmente atrativa, visando uma interação eficiente do usuário 

![API FATEC - BETA - YouTube - Google Chrome 2024-05-14 20-38-45](https://github.com/larissasouz/Bertoti/assets/102266928/3c0bc2aa-4542-4fdf-8f23-99744b82e65b)

<b>Exemplo:</b> 
O código abaixo é um script em Python que usa reconhecimento de voz e uma API de clima para informar ao usuário a temperatura atual de uma cidade especificada verbalmente

</div>

~~~~java
import speech_recognition as sr
import requests
import pyttsx3
# link do open_weather: https://openweathermap.org/
def clima():
    audio = sr.Recognizer()
    maquina = pyttsx3.init()
    with sr.Microphone() as source:
        maquina.say("Informe a cidade da qual deseja descobrir a temperatura. ")
        maquina.runAndWait()
        print('ouvindo...')
        voz = audio.listen(source)
        cidade = audio.recognize_google(voz, language='pt-BR')
        maquina.say(cidade)
        API_KEY = "00a7922cfcccb7df823f10e7014e2e42"
        link = f"https://api.openweathermap.org/data/2.5/weather?q={cidade}&appid={API_KEY}&lang=pt_br"
        requisicao = requests.get(link)
        requisicao_dic = requisicao.json()  # Faz a requisição
        descricao = requisicao_dic['weather'][0]['description']  # Puxa a descrição de como esta o clima
        temperatura = requisicao_dic['main']['temp'] - 273.15  # Puxa a temperatura atual e faz a conversão
        maquina = pyttsx3.init()
        maquina.say(f'Em {cidade} o céu está {descricao} e está {temperatura:.0f}ºC hoje')
        maquina.runAndWait()
~~~~
Para mais informações: <a href="https://github.com/alanfmorato/BETA/">GIT</a>

<b> Tecnologias Utilizadas </b>
- Python (Back-end)
- Tkinter (Front-end)
- HTML5 (Front-end)
- CSS3 (Front-end)

### Contribuições pessoais

<div align="justify">

Durante minha atuação no projeto, desenvolvi várias funcionalidades importantes, incluindo:

<b> Calculadora: </b> Criei uma função que permite aos usuários realizar operações matemáticas por controle de voz. O usuário insere dois números e escolhe a operação desejada entre as opções de: soma, subtração, multiplicação, divisão e exponenciação. Para utilizar a função, o usuário deve dizer: <i> "Beta, calculadora". </i>.

<b> Clima: </b> Desenvolvi uma função que retorna a temperatura de um município. A assistente virtual pergunta ao usuário qual cidade ele deseja saber a temperatura, e o usuário responde com o nome da cidade. O código consulta a API do <i> OpenWeatherMap </i>, que retorna a temperatura atual e uma descrição do clima, se está nublado ou ensolarado. Para utilizar a função, o usuário deve dizer: <i> "Beta, clima". </i>

Essas funcionalidades foram fundamentais para tornar a BETA uma ferramenta versátil e útil para os alunos, permitindo uma interação natural e eficiente através de comandos de voz. Ao integrar essas capacidades, garanti que a assistente virtual pudesse oferecer suporte significativo e prático no dia a dia dos usuários, contribuindo para a melhoria da gestão do tempo e das tarefas estudantis.

</div>

### Hard Skills
- Python - Tenho a capacidade de desenvolver soluções de programação de maneira independente, com foco em Python como minha principal linguagem.
- HTML5 - Competência em estruturação semântica, como por exemplo, utilização de tags semânticas como header, footer, article, section, etc., para criar uma estrutura lógica e bem definida do conteúdo da página.
- CSS3 - Competência em estilizar de forma autônoma, sendo possível criar animações e transições.

### Soft Skills
- Colaboração - Trabalhei com a equipe para alcançar o objetivo, sempre com foco em compartilhar conhecimentos e resolver problemas juntos, o que melhorou nossa produtividade e criatividade.
- Liderança - Pela experiência que tive, atuei auxiliando na liderança, lidando com adversidades e trabalhando com a gestão de tempo.
- Adaptabilidade - Apesar das dificuldades que surgiram no caminho, consegui, junto à equipe, me adaptar às situações e pensar na melhor forma de lidar com elas.

----

### Em 2022-2

<div align="justify">

No segundo semestre de 2022, desenvolvemos um sistema desktop com o objetivo de gerenciar e acompanhar processos seletivos de candidatos para vagas de emprego. O sistema também é capaz de gerar relatórios e realizar análises de aprovação para o setor de recursos humanos.

![2022-11-27 22-30-07_Trim](https://user-images.githubusercontent.com/101594950/204175322-43f2fbed-53c0-47bf-a3c1-2e69d4255ac8.gif)


<b>Exemplo:</b> 
O código abaixo é código em Java que tem como objetivo realizar algumas validações, como: validação de senha e validação de data.

</div>

~~~java
                    //Validação de senha
                            if (senha.equals(senha2)) {
                                String PASSWORD_REGEX = "^(?=.*[0-9])(?=.*[a-z])(?=.*[A-Z])(?=.*[-._@#$%^&+=])(?=\\S+$).{8,16}$";
                                Pattern PASSWORD_PATTERN = Pattern.compile(PASSWORD_REGEX);
                                if (PASSWORD_PATTERN.matcher(senha).matches()) {
                                    //Validação de email
                                    String EMAIL_REGEX = ".+@.+\\.[a-z]+";
                                    Pattern EMAIL_PATTERN = Pattern.compile(EMAIL_REGEX);
                                    if (EMAIL_PATTERN.matcher(email).matches()) {
                                        //Validação de telefone
                                        String TELEPHONE_REGEX = "\\d{11}";
                                        Pattern TELEPHONE_PATTERN = Pattern.compile(TELEPHONE_REGEX);
                                        if (TELEPHONE_PATTERN.matcher(telefone).matches()) {
                                            //Validação de data
                                            String DATE_REGEX = "^\\d{4}-\\d{2}-\\d{2}$";
                                            Pattern DATE_PATTERN = Pattern.compile(DATE_REGEX);
                                            if (DATE_PATTERN.matcher(data).matches()) {
                                                Candidato candidato = new Candidato();
                                                candidato.setNome(nome);
                                                candidato.setCpf(cpf_long);
                                                candidato.setDataNac(data);
                                                candidato.setEmail(email);
                                                candidato.setSenha(senha);
                                                candidato.setTelefone(telefone_long);

                                                HelloApplication.ChangeScene("candidato2");
~~~

Para mais informações: <a href="https://github.com/B1naryDevs/API">GIT</a>

<b> Tecnologias Utilizadas </b>
- Java (Back-end)
- MySQL (Front-end)
- CSS3 (Front-end)
  

### Contribuições pessoais

<div align="justify">

Durante minha atuação no projeto, desenvolvi várias funcionalidades importantes, incluindo:

<b> Validações: </b> Criei algumas validações que verificam se os os dados inseridos pelo usuário estão corretos, como: Validação de CPF, validação de senha e validação de data.

<b> Ocultar senha: </b> Desenvolvi uma funcionalidade que tinha como objetivo ocultar e mostrar a senha para o usuário, ou seja, no login, o usuário podia optar por visualizar ou não a senha dele.

Além dessas atuações, como Product Owner tive um papel crucial no desenvolvimento do projeto, pois tive a responsábilidade de desenvolver os seguintes itens:

<b> Backlog do produto: </b> Após entender as dores e desenvolver os requisitos do cliente e do projeto, criei o backlog do produto que tinha como objetivo apresentar as atividades e suas respectivas prioridades.

<b> Backlog da sprint: </b> Depois de definido a prioridade das atividades, decidi junto à equipe quando cada atividade seria desenvolvida, sendo criado assim o backlog da sprint. No total, foram 4 sprints de desenvolvimento.

<b> Modelagem do banco de dados: </b> Atuei na modelagem conceitual do banco de dados, definindo como os dados deveriam ser armazenados.

<b> Protótipo de baixa fidelidade: </b> Realizei o design dos protótipos de baixa fidelidade de acordo com as necessidades do cliente.

<b> Readme: </b> Atuei em cima da documentação do Readme.md para que todas as etapas estivessem detalhadas.
</div>

### Hard Skills
- Java - Habilidade em desenvolver soluções de programação de forma independente.
- CSS3 - Capacidade de estilizar autonomamente, incluindo a criação de animações e transições.
- MySQL - Competência em realizar operações CRUD de forma autônoma.

### Soft Skills

- Comunicação - Capacidade de transmitir informações de maneira clara e eficaz a todos os stakeholders, incluindo clientes, equipes de desenvolvimento e outros departamentos.
- Negociação- Habilidade para negociar prioridades, prazos e recursos com diferentes partes interessadas, garantindo que os objetivos do produto sejam atingidos.
- Pensamento crítico: Analisar problemas complexos e tomar decisões informadas com base em dados e feedback, garantindo que as soluções propostas sejam viáveis e eficazes.

---

Em 2023-1

![image](https://github.com/larissasouz/Bertoti/assets/102266928/a40ad081-cf92-4932-8035-a582fa4d0e00)


## DESCRIÇÃO DO PROJETO
O projeto em questão desafia a criação de uma aplicação web com foco no gerenciamento de vendas. A aplicação tem como objetivo principal abranger três áreas cruciais: o histórico do vendedor, o planejamento de vendas e o registro das vendas efetuadas.

Um dos principais recursos da aplicação é a capacidade de comparar esses três conjuntos de dados, permitindo uma análise minuciosa e precisa das informações. Isso significa que os resultados das vendas podem ser avaliados em relação ao histórico dos vendedores e ao planejamento estabelecido.

O diferencial deste projeto é a integração de um algoritmo de Inteligência Artificial já existente. Esse algoritmo será empregado para gerar previsões e insights adicionais, com o objetivo de elevar a precisão e a confiabilidade das análises realizadas pela aplicação.

Em resumo, o desafio consiste em desenvolver uma aplicação web que simplifica o gerenciamento de vendas, proporcionando uma análise detalhada por meio da comparação do histórico dos vendedores, do planejamento e das vendas registradas. Além disso, a aplicação será aprimorada com previsões de IA para aprimorar a tomada de decisões relacionadas às vendas.

## TECNOLOGIAS UTILIZADAS

![image](https://github.com/larissasouz/Bertoti/assets/102266928/27dcc3bc-1708-4d58-97c1-11b31ff9af77)


## CONTRIBUIÇÕES PESSOAIS
No meu papel de desenvolvedora, minha contribuição abrangeu tanto o Front-End quanto o Back-End do projeto. Algumas das atividades que desempenhei incluíram:<br>
<br>
<details> 
<summary><b>Desenvolvimento de Modelagem e Script: </b></summary>

Criei a modelagem de banco de dados e desenvolvi o script para criação das tabelas com suas chaves primárias e atributos. <br>
![image](https://github.com/larissasouz/Bertoti/assets/102266928/6dffb1eb-bafb-4e60-a736-c9afe1dc8e9e)
</details>

<details>
<summary><b>Desenvolvimento de tela de visualização de planejamento: </b></summary><br>
Projetei e implementei uma interface de usuário que permitia a visualização de informações de planejamento. Isso ajudou a organizar e acompanhar o planejamento de atividades ou tarefas relevantes para o sistema.<br>
 
![image](https://github.com/larissasouz/Bertoti/assets/102266928/084af6a5-c709-45cb-a7ac-b2cddf26df76) <br>
O código acima fornece a estrutura básica para exibir informações de planejamento em uma tabela, juntamente com uma imagem e um formulário <br>

![image](https://github.com/larissasouz/Bertoti/assets/102266928/4302cf92-6289-41fb-9c2e-e7aca7733264) <br>
Neste código, um método é mapeado para lidar com solicitações HTTP GET em uma aplicação Spring Boot. Ele busca dados de planejamento de algum serviço, converte esses dados para um formato específico usando um conversor e retorna essa informação como uma resposta HTTP com status 200 e o corpo contendo a lista de objetos convertidos. Este padrão é comum em APIs RESTful, onde a resposta é estruturada de acordo com o modelo de dados desejado para ser consumido pelos clientes.

</details>

<details>
<summary><b> Desenvolvimento do CRUD para administrador: </b></summary><br>
Criei as operações básicas de CRUD (Create, Read, Update e Delete) para gerenciar informações de administradores no sistema. Isso permitiu a criação, leitura, atualização e exclusão de dados relacionados aos administradores.<br>
O código abaixo representa um endpoint de uma API que permite salvar administradores, desde que o e-mail do administrador não esteja em uso. Se o e-mail estiver em uso, ele retornará um erro de conflito (status 409), caso contrário, retornará uma resposta de sucesso (status 201) com o objeto do administrador recém-salvo no corpo da resposta.
 
![image](https://github.com/larissasouz/Bertoti/assets/102266928/b9a812bc-9a7c-4886-9b0e-8670da256d74)

</details>

------------------------------------------------------------------------------------

### Para realizar essas tarefas, utilizei diversas tecnologias, incluindo:

<i>JavaScript:</i> Usei JavaScript para aprimorar a interatividade do Front-End, permitindo aos usuários interagir com os dados e realizar ações nas páginas da web.

<i>Framework Bootstrap:</i> Para aprimorar o design e a aparência das interfaces de usuário, aproveitei o Bootstrap, um framework de CSS e JavaScript amplamente utilizado para criar layouts responsivos e visualmente atraentes.

<i>Java e Spring Boot:</i> Desenvolvi a lógica do Back-End usando Java e o framework Spring Boot. Isso envolveu o processamento de solicitações do cliente, o acesso ao banco de dados SQL e a lógica de negócios para as operações CRUD.

<i>Banco de Dados SQL:</i> Utilizei um banco de dados SQL para armazenar e gerenciar os dados do sistema de maneira estruturada e segura.

Em conjunto, essas tecnologias e atividades contribuíram para o desenvolvimento de um sistema completo e funcional que permitiu o gerenciamento eficiente de administradores, vendas e planejamento dentro da aplicação.

## APRENDIZADOS
Os principais aprendizados da minha experiência trabalhando em projetos que envolvem tanto o Front-End quanto o Back-End: <br>

<b>Domínio de Tecnologias Diversas:</b> Aprendi a usar uma variedade de tecnologias, desde JavaScript e Java até frameworks como Spring Boot e Bootstrap.<br>

<b>Entendimento do Ciclo de Desenvolvimento:</b> Ganhei uma visão completa do ciclo de vida do desenvolvimento de software, desde a criação da interface do usuário até a lógica de negócios e o gerenciamento de dados.<br>

<b>Fluxo de Dados:</b> Compreendi como os dados fluem entre o Front-End e o Back-End em aplicativos web.<br>

-----


### Em 2023-2

<div align="justify">

No 4º semestre,desenvolvemos um sistema web para simplificar a gestão de prestadores de serviço, segmentos e ordens de serviço. Este projeto incluiu a criação de uma landing page intuitiva para facilitar a solicitação de novas ordens de serviço por novos clientes, através de um formulário simples.

Para os clientes existentes, foi disponibilizado uma landing page personalizada, permitindo fácil acesso às ordens de serviço anteriores, a possibilidade de baixar laudos novamente e fornecer feedback valioso, incluindo sugestões e reclamações. Além disso, eles também podem realizar novas solicitações de ordens de serviço diretamente pela plataforma.

![consulta de segmento](https://github.com/B1nary-Devs/JAIA-SOFTWARE/assets/102266928/f3ec5880-c825-4080-a898-0c97a086d3d2)

<b>Exemplo:</b> 
O código abaixo é código em vue que tem como objetivo realizar o update de um prestador de serviço.

</div>

~~~java
    async function atualizarPrestador() {
    // Verifique se uma categoria foi selecionada
    if (categoriaSelecionada.value === null) {
      alert('Selecione uma categoria antes de cadastrar.');
      return;
    }
    // Fazendo a requisição POST com os valores capturados
    try {
        let rota = 'http://localhost:8080/prestador/' + id.value
        console.log(rota);
      await axios.put(rota, {
        prestadorNome: nome.value,
        cnpj: cnpj.value,
        email: email.value,
        senha: senha.value,
        segmentoId: 1 
      });
        alert('Registro atualizado!!');
  
    } catch (error) {
      console.error('Ocorreu um erro ao cadastrar o prestador:', error);
      alert('Erro ao cadastrar o prestador.');
    }
    }
~~~

Para mais informações: <a href="https://github.com/B1nary-Devs/JAIA-SOFTWARE">GIT</a>

<b> Tecnologias Utilizadas </b>

- Java (Back-end)
- Oracle Cloud (Back-end)
- Typescript (Front-end)
- HTML5 (Front-end)
- CSS3 (Front-end)

### Contribuições pessoais

<div align="justify">

Durante minha atuação no projeto, como Product Owner, tive a responsábilidade de desenvolver os seguintes itens:

<b> Backlog do produto: </b> Após entender as dores e desenvolver os requisitos do cliente e do projeto, criei o backlog do produto que tinha como objetivo apresentar as atividades e suas respectivas prioridades.

<b> Backlog da sprint: </b> Depois de definido a prioridade das atividades, decidi junto à equipe quando cada atividade seria desenvolvida, sendo criado assim o backlog da sprint. No total, foram 4 sprints de desenvolvimento.

<b> Modelagem do banco de dados: </b> Atuei na modelagem conceitual do banco de dados, definindo como os dados deveriam ser armazenados.

<b> Protótipo de baixa fidelidade: </b> Realizei o design dos protótipos de baixa fidelidade de acordo com as necessidades do cliente.

<b> Jornada do usuário: </b> Desenvolvi a jornada de usuário utilizando Miro, onde foi apresentado todo o fluxo do sistema e como ele deveria se comportar em algumas situações.

<b> Readme: </b> Atuei em cima da documentação do Readme.md para que todas as etapas estivessem detalhadas.

Além dessas atuações, também desenvolvi algumas funcionalidades importantes para o projeto, como:

<b> CRUD de ordem de serviço: </b> Trabalhei em cima de todo o crud da ordem de serviço, para que o usuário final pudesse criar, consultar, atualizar e apagar conforme sua necessidade.

<b> Modal de ordem de serviço: </b> Criei um modal para que as informações fossem apresentadas de forma correta.

<b> Checklist personalizado: </b> Como no projeto havia a opção de "checklist personalizado", desenvolvi essa opção para que o usuário pudesse alterar ou inserir um novo checklist de acordo com sua necessidade dentro daquela ordem de serviço.

<b> Cadastro e Consulta de Segmento: </b> Atuei para que o cadastro e a consulta do segmento fosse realizada corretamente no front-end.

</div>

### Hard Skills
- Java - Habilidade em desenvolver soluções de programação de forma independente.
- OracleCloud - Competência em realizar operações CRUD de forma autônoma.
- CSS3 - Capacidade de estilizar autonomamente, incluindo a criação de animações e transições.
- Typescript - Proficiência em desenvolver aplicações web robustas, com tipagem estática que melhora a qualidade do código e a produtividade.

### Soft Skills

- Liderança -  Capacidade em influenciar e motivar a equipe de desenvolvimento.
- Gestão do tempo: Priorizar tarefas e gerenciar o tempo de forma eficiente, assegurando que os projetos sejam concluídos dentro dos prazos estabelecidos.
- Visão estratégica: Capacidade de alinhar as atividades com a visão e os objetivos de longo prazo.
- Resolução de problemas: Abordar desafios de forma proativa e encontrar soluções para obstáculos que surgem durante o desenvolvimento.
