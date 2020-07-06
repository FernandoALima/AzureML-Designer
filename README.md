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

Basta clicar em "+ Container", após clicar digite um nome para seu container e click em **"Create"** conforme imagem abaixo:

![img5](/img/createcontainer1.png)  

Após o container ser criado click nele:

![img6](/img/createcontainer2.png)
___

5. Agora é hora de fazer o upload dos dados que você irá utilizar no seu experimentos.

Eu utilizei o Kaggle (https://www.kaggle.com/vjchoudhary7/hr-analytics-case-study) para baixar um dataset para esse experimento. No meu caso eu dei uma "abrasileirada" no dataset e o mesmo está disponível nesse link: 

-