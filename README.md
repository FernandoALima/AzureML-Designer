# Workshop Azure Machine Learning Designer 
Este workshop contém instruções sobre como criar seu primeiro experimento utilizando o Azure Machine Learning Designer

## Praparar o ambiente ##

> 1. Crie sua conta gratuita no Azure

Basta seguir o passo a passo do link abaixo. Obs: Utilize um email para criar sua conta Microsoft que nunca tenha utilizado para trial do Azure anteriormente.
Link: https://azure.microsoft.com/pt-br/free/
___
   
> 2. Criar um Resource Group

No portal do Azure Portal click em **"Create a resource"** e então digite **Resource Group** . Click em **"Create"** 

- Subscription: Selecione sua subscrição
- Resource group: Digite um nome para o sue resource. Ex: MeuML
- Selecione uma região. Aqui você pode utilizar qualquer região disponível.   

![img1](/img/resourcegroup.png)

___

> 3. Criar o Machine Learning

No portal do Azure Portal click em **"Create a resource"** e então digite **Machine Learning** . Click em **"Create"** e siga as configurações abaixo: 

- Subscription: Selecione sua subscrição
- Resource group: Selecione o resource group criado na etapa anterior
- Workspace name: Digite um nome para seu workspace. eg: Meu-workspace
- Region: Selecione uma região onde será feito o deployment do seu workspace. Recomendo East US 2 por questões de custos.
- Workspace edition: Aqui você deve selecionar "Enterprise".

![img2](/img/MachineLearningWorkspace.png)

___

> 3. Após a criação volte ao resource group que você criou e click no Storage Account que foi criado conforme imagem abaixo:

![img3](/img/resourcegroup_poscriacao.png)

Uma vez dentro do Storage Account click em "Container" conforme imagem abaixo:

![img4](/img/storageaccount_container.png) 
___

> 4. Crie um novo Container

- Basta clicar em "+ Container", após clicar digite um nome para seu container e click em **"Create"** conforme imagem abaixo:

![img5](/img/createcontainer1.png)  

- Após o container ser criado click nele:

![img6](/img/createcontainer2.png)

___

5. Agora é hora de fazer o upload dos dados que você irá utilizar no seu experimentos.

- Eu utilizei o Kaggle (https://www.kaggle.com/vjchoudhary7/hr-analytics-case-study) para baixar um dataset para esse experimento. No meu caso eu dei uma "abrasileirada" no dataset e o mesmo está disponível neste repositório do GitHub. Basta fazer o download do arquivo para depois fazer o upload para o seu Storage Account Container conforme imagem abaixo?

![img7](/img/upload_data.png)

- Após fazer o upload do dataset click no seu Storage Account conforme imagem abaixo:

![img8](/img/storageaccount_key01.png)

- Em seguida click em **"Access Keys"**

![img9](/img/storageaccount_key02.png)

- Agora você deve colocar a Key. No meu exemple copiei a Key1, mas ambas funcionam

![img10](/img/storageaccount_key03.png)

- Você precisa salvar essa chave, pois iremos utilizar ela em uma etapa mais a frente.
___

> 6. Volte ao seu resource group e click em Machine Learning

![img11](/img/marchinelearningclick.png)

Uma vez dentro do recurso click em **"Launch now"**

![img12](/img/ml_launch.png)
___


## Começando nossos experimentos no Azure Machine Learning Studio ##

> 1. Agora você já está dentro do Azure Machine Learning Studio

Click em **"Designer (preview)"** e então click no sinal de + conforme imagens abaixo:

![img13](/img/ml_designer01.png)

![img14](/img/ml_designer02.png)
___

> 2. Preparar nosso experimento

- Primeiro vamos dar um nome e uma descrição para esse pipeline. Do seu lado direito em **"Draft details"** digite um nome e uma descrição para seu experimento

![img15](/img/ml_designername.png)

- Agora precisamos selecionar o **"Compute target"** esses servidores que irão precessar todas as etapas do nosso workflow

    - Click em **"Select compute target"**
    - Em seguida click em **"Create new"**
    - Vamos manter a opção pré-definida de cluster
    - Digite um nome para o seu cluster (são os servidores que irão precessar seu workflow)
    - Click em **"Save"**
    - Click em **"Save"** novamente

![img16](/img/ml_designer03.png)

![img17](/img/ml_designer04.png)

![img18](/img/ml_designer05.png)

- Agora basta clicar novamente em **"Select compute target"** e selecionar o cluster que você acabou de criar

![img19](/img/ml_designer06.png)
___

> 3. Importar os dados

 - Primeiro passo é importar os dados que serão utilizados para esse experimento. Na coluna **"Modules"** ao lado esquedo click em **"Data Input and Output"** selecione **"Import Data"** e arraste para o centro da tela no campo vazio.

![img20](/img/ml_designer07.png)

- Após a etapa anterior irá aparecer uma coluna **"Import Data"** 
    
    - Deixe selecionado **"Datastore"** 
    - Click em **"New datastore"**

    ![img21](/img/ml_designer08.png)

    - Digite um nome para seu datastore
    - Deixe selecionado **"Azure Blob Storage"**
    - Deixe selecionado **"From Azure subscription"**
    - Deixe selecionado sua subscription
    - Selecionar o Storage Account que foi criado anteriormente
    - Selecionar o Container que você criou
    - Deixe selecionado a opção **"No"**
    - Deixe selecionado **"Account Key"**
    - Em Account Key você deve colar a Key copiada na etapa 5 do "Preparar seu ambiente"
    - Em seguida click em **"Create"**

    ![img22](/img/datastore01.png)

    - Uma vez criado no campo Datastore selecione o datastore que você acabou de criar
    - Click em **"Browse path"** e selecione o arquivo que você fez upload na etapa 5 do "Preparar seu ambiente"
    - Click em **"Save"**

    ![img23](/img/datastore02.png)

    - Agora você deve clicar em **"Submit"** para o designer copiar os dados para seu experimento. Em seguida irá aparecer um pop-up com o nome de **"Set up pipeline run"**

        - Selecione **"Create new"**
        - Digite um nome para seu experimento
        - Digite uma descrição para seu experimento
        - Click em **"Submit"**

        ![img24](/img/run_experimento01.png)
___    

> 4. Selecionar as colunas ou features

- Na coluna **"Modules"** ao lado esquedo click em **"Data Transformation"** selecione **"Select Columns in Dataset"** e arraste para o centro da tela no campo vazio.

- Conecte a caixa **"Import Data"** com a caixa **"Select Columns in Dataset"**

- Após a etapa anterior irá aparecer uma coluna **"Select Columns in Dataset"** a sua direita. Click em **"Edit Column"**

    - Selecione **"All columns"** e click no sinal +
    - Selecione **"Exclude"** e aqui você pode selecionar as colunas que você quer excluir do seu experimento utilizando o **"Column names"** 

    ![img25](/img/select_columns.png)
___  

> 5. Limpar linhas que estão sem dados

- Na coluna **"Modules"** ao lado esquedo click em **"Data Transformation"** selecione **"Clean Missing Data"** e arraste para o centro da tela no campo vazio.

- Conecte a caixa **"Select Columns in Dataset"** com a caixa **"Clean Missing Data"**

- Após a etapa anterior irá aparecer uma coluna **"Clean Missing Data"** a sua direita. Click em **"Edit Column"**

    - Selecione **"All columns"**
    - Click em **"Save"**
    - Minimum missing value ratio pode deixar em **"0.0"**
    - Maximum missing value ratio pode deixar em **"1.0"**
    - Em Cleaning mode selecionar **"Remove entire row"**

    ![img26](/img/clean_missingdata01.png)

    ![img26](/img/clean_missingdata02.png)

    

