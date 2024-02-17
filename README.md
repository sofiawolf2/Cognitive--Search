# Cognitive-Search :mag_right::open_file_folder:
Nesse arquivo mostrarei as etapas passo a passo para configurar uma pesquisa usando a pesquisa cognitiva do Azure (Azure Cognitive Search). 

## Introdução :rocket:

O Azure Cognitive Search é uma plataforma de mineração de conhecimento alimentada por IA do azure que é feita seguindo 3 principais pilares essenciais: 

1. **Ingestão de dados:**
   Podem ser usados para efetuar a ingestão de dados recursos como: Azure Blob Storage Containers, que reconhece qualquer tipo de arquivo; Azure Data Lake Store Gen 2, que é um repositório de dados; Azure Table Storage, que são as tabelas. 

3. **Enriquecimento e índice de IA:**
Esta parte é importantíssima pois traz mais dados úteis para fins de pesquisa, permite uma compreensão mais profunda e detalhada. Aqui usamos o processamento de linguagem natural ao fazer o reconhecimento de entidades no texto, traduzir textos e avaliar sentimentos. Além disso, a indexação vai tornar o conteúdo pesquisável. 

4. **Explorar:**
Consiste de fato na pesquisa, pesquisas em índices, dentro de aplicativos etc.

## Passo a Passo :jigsaw:

### Passo 1: Entender situação problema
Imagine que uma determinada empresa com muitos feedbacks dos seus produtos tem como dono alguém que quer saber do que se trata os feedbacks. Ele quer identificar quais são os pontos fortes da empresa e quais precisam de melhorias, porém são tantos que se torna difícil para ele ler todos e administrar.

### Passo 2: Decisão sobre Serviço utilizados
Visto o problema, pode-se usar uma IA search para ajudar a entender quais são as informações, reclamações, elogios e aconselhamentos existentes nos feedbacks.
Para esse tipo de aplicação de IA é necessário pensar em alguns tópicos antes de iniciar como: Quais recursos serão utilizados? Como extrair dados? Como enriquecer a IA etc. Vamos ver os resultados dessas perguntas no decorrer do passo a passo. 

### Passo 3: Identificar quais são os recursos utilizados

Usaremos esses 3 principais recursos da Microsoft Azure: 
1. Azure AI Search, que será o mecanismo de busca;
2. Azure AI Services, que é o recurso de inteligência artificial em si;
3. Storage Account, que será responsável por fazer o armazenamento dos dados (feedbacks).

### Passo 4: Por em prática

Seguindo a ordem dos recursos utilizados, primeiro vamos criar o mecanismo de busca através do Azure AI Search. Dentro da plataforma Azure é possível ver os diversos recursos que ela fornece, ao criar um recurso AI Search, dar um nome único para ele e efetivar tudo, já pode seguir para a próxima etapa. 

Agora temos um recurso de IA Search, que é onde futuramente será feito a pesquisa, vamos criar um recurso de IA: Azure AI Services. O processo também é muito simples, basta preencher os campos de informações corretamente e seguir para a prox etapa.

Já temos um mecanismo de pesquisa e já temos um recurso de IA. Para iniciar as pesquisas falta apenas os dados que serão pesquisados. Ou seja, falta a etapa responsável pelo armazenamento de dados: Storage Account. Nesses recursos existem modelos pré estabelecidos de replicação de dados, no qual estaremos usando a mais simples e de menor custo, e após criar uma conta de armazenamento seguindo um desses modelos teremos que alterar uma coisa. Precisamos mudar as configurações de segurança para que seja permitido que os blobs se tornem legíveis anonimamente. Dessa forma é possível adicionar os dados a um container que iremos utilizar futuramente. 

Após criar um container, que tradução literal seria "recipiente", podemos adicionar os arquivos a ele e depois fazer a conexão final para isso funcionar. No mecanismo de busca que foi criado é possível importar dados de um container. Após fazer a linkagem da ferramenta de pesquisa com os dados usando IA. Agora está tudo pronto e podemos iniciar os testes.

## Finalização :dart:

Dentro do AI Search que foi criado, há uma opção chamada "Search Explorer". Explorar. O 3 pilar para efetivar uma pesquisa cognitiva do azure, chegamos na parte final. Ao clicar nessa opção, será levado para uma área onde faremos as devidas pesquisas propostas para usar na situação problema. 

Se for pesquisado uma localização por exemplo (search=locations:'NomedaCidade'), vai retornar todas as informações relacionadas a feedbacks feitos nessa cidade ou de pessoas que moram nessa região. É possível ver horários, feedbacks em si, avaliações, se foram comentários negativos ou positivos. Lembrando que quando se trata de um método que trabalha com o uso do processamento de linguagem natural, ele é capaz inclusive de analisar os sentimentos de quem escreveu aquilo e entender se é um feedback ruim ou bom. Outro exemplo seria pesquisar a respeito de sentimentos positivos (search=sentiment:'positive') ou negativos (search=sentiment:'negative') ele vai retornar as avaliações que batem com esse sentimento. Assim se torna mais prático e simples para quem estiver administrando os feedbacks ver o que tem de mais importante ou que deseja procurar para fazer algo a respeito. 
