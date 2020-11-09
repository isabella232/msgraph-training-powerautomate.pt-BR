---
ms.openlocfilehash: 90462157024c529a1cf183230298fbf80813b8c9
ms.sourcegitcommit: 64947f11d367ffbebbafb700fdfdc20617275f35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48829623"
---
<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="ea653-101">Neste exercício, você criará um novo conector personalizado que pode ser usado no Microsoft Power Automate ou nos aplicativos de lógica do Azure.</span><span class="sxs-lookup"><span data-stu-id="ea653-101">In this exercise, you will create a new custom connector which can be used in Microsoft Power Automate or in Azure Logic Apps.</span></span> <span data-ttu-id="ea653-102">O arquivo de definição OpenAPI é criado com o caminho correto para o ponto de extremidade do Microsoft Graph `$batch` e configurações adicionais para habilitar a importação simples.</span><span class="sxs-lookup"><span data-stu-id="ea653-102">The OpenAPI definition file is prebuilt with the correct path for the Microsoft Graph `$batch` endpoint and additional settings to enable simple import.</span></span>

<span data-ttu-id="ea653-103">Há duas opções para criar um conector personalizado para o Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="ea653-103">There are two options to create a custom connector for Microsoft Graph:</span></span>

- <span data-ttu-id="ea653-104">Criar de em branco</span><span class="sxs-lookup"><span data-stu-id="ea653-104">Create from blank</span></span>
- <span data-ttu-id="ea653-105">Importar um arquivo do OpenAPI</span><span class="sxs-lookup"><span data-stu-id="ea653-105">Import an OpenAPI file</span></span>

## <a name="option-1-create-custom-connector-from-blank-template"></a><span data-ttu-id="ea653-106">Opção 1: criar um conector personalizado do modelo em branco</span><span class="sxs-lookup"><span data-stu-id="ea653-106">Option 1: Create custom connector from blank template</span></span>

<span data-ttu-id="ea653-107">Abra um navegador e navegue até [Microsoft Power Automate](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ea653-107">Open a browser and navigate to [Microsoft Power Automate](https://flow.microsoft.com).</span></span> <span data-ttu-id="ea653-108">Entre com sua conta de administrador de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea653-108">Sign in with your Office 365 tenant administrator account.</span></span> <span data-ttu-id="ea653-109">Escolha **dados** no menu do lado esquerdo e selecione o item **conectores personalizados** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="ea653-109">Choose **Data** on the left-hand side menu, and select the **Custom Connectors** item in the drop-down menu.</span></span>

![Uma captura de tela do menu suspenso na Microsoft Power Automate](./images/custom-connectors.png)

<span data-ttu-id="ea653-111">Na página **conectores personalizados** , escolha o link **novo conector personalizado** no canto superior direito e, em seguida, selecione o item **criar em branco** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="ea653-111">On the **Custom Connectors** page choose the **New custom connector** link in the top right, then select the **Create from blank** item in the drop-down menu.</span></span>

![Uma captura de tela do novo menu suspenso do conector personalizado na Microsoft Power Automate](./images/new-connector.png)

<span data-ttu-id="ea653-113">Insira `MS Graph Batch Connector` na caixa de texto **nome do conector** .</span><span class="sxs-lookup"><span data-stu-id="ea653-113">Enter `MS Graph Batch Connector` in the **Connector name** text box.</span></span> <span data-ttu-id="ea653-114">Choose **Continue**.</span><span class="sxs-lookup"><span data-stu-id="ea653-114">Choose **Continue**.</span></span>

<span data-ttu-id="ea653-115">Na página configuração do conector **geral** , preencha os campos da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="ea653-115">On the connector configuration **General** page, fill in the fields as follows.</span></span>

- <span data-ttu-id="ea653-116">**Esquema** : https</span><span class="sxs-lookup"><span data-stu-id="ea653-116">**Scheme** : HTTPS</span></span>
- <span data-ttu-id="ea653-117">**Host** : `graph.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="ea653-117">**Host** : `graph.microsoft.com`</span></span>
- <span data-ttu-id="ea653-118">**URL base** : `/`</span><span class="sxs-lookup"><span data-stu-id="ea653-118">**Base URL** : `/`</span></span>

<span data-ttu-id="ea653-119">Escolha o botão de **segurança** para continuar.</span><span class="sxs-lookup"><span data-stu-id="ea653-119">Choose **Security** button to continue.</span></span>

![Uma captura de tela da guia Geral na configuração do conector](./images/general-tab.png)

<span data-ttu-id="ea653-121">Na página **segurança** , preencha os campos da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="ea653-121">On the **Security** page, fill in the fields as follows.</span></span>

- <span data-ttu-id="ea653-122">**Escolha qual autenticação é implementada por sua API** : `OAuth 2.0`</span><span class="sxs-lookup"><span data-stu-id="ea653-122">**Choose what authentication is implemented by your API** : `OAuth 2.0`</span></span>
- <span data-ttu-id="ea653-123">**Provedor de identidade** : `Azure Active Directory`</span><span class="sxs-lookup"><span data-stu-id="ea653-123">**Identity Provider** : `Azure Active Directory`</span></span>
- <span data-ttu-id="ea653-124">**ID do cliente** : a ID do aplicativo que você criou no exercício anterior</span><span class="sxs-lookup"><span data-stu-id="ea653-124">**Client id** : the application ID you created in the previous exercise</span></span>
- <span data-ttu-id="ea653-125">**Segredo do cliente** : a chave que você criou no exercício anterior</span><span class="sxs-lookup"><span data-stu-id="ea653-125">**Client secret** : the key you created in the previous exercise</span></span>
- <span data-ttu-id="ea653-126">**URL de logon** : `https://login.windows.net`</span><span class="sxs-lookup"><span data-stu-id="ea653-126">**Login url** : `https://login.windows.net`</span></span>
- <span data-ttu-id="ea653-127">**ID do locatário** : `common`</span><span class="sxs-lookup"><span data-stu-id="ea653-127">**Tenant ID** : `common`</span></span>
- <span data-ttu-id="ea653-128">**URL do recurso** : `https://graph.microsoft.com` (sem à direita/)</span><span class="sxs-lookup"><span data-stu-id="ea653-128">**Resource URL** : `https://graph.microsoft.com` (no trailing /)</span></span>
- <span data-ttu-id="ea653-129">**Escopo** : deixar em branco</span><span class="sxs-lookup"><span data-stu-id="ea653-129">**Scope** : Leave blank</span></span>

<span data-ttu-id="ea653-130">Escolha o botão de **definição** para continuar.</span><span class="sxs-lookup"><span data-stu-id="ea653-130">Choose **Definition** button to continue.</span></span>

![Uma captura de tela da guia Segurança na configuração do conector](./images/security-tab.png)

<span data-ttu-id="ea653-132">Na página **definição** , selecione **nova ação** e preencha os campos da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="ea653-132">On the **Definition** page, select **New Action** and fill in the fields as follows.</span></span>

- <span data-ttu-id="ea653-133">**Resumo** : `Batch`</span><span class="sxs-lookup"><span data-stu-id="ea653-133">**Summary** : `Batch`</span></span>
- <span data-ttu-id="ea653-134">**Descrição** : `Execute Batch with Delegate Permission`</span><span class="sxs-lookup"><span data-stu-id="ea653-134">**Description** : `Execute Batch with Delegate Permission`</span></span>
- <span data-ttu-id="ea653-135">**ID da operação** : `Batch`</span><span class="sxs-lookup"><span data-stu-id="ea653-135">**Operation ID** : `Batch`</span></span>
- <span data-ttu-id="ea653-136">**Visibilidade** : `important`</span><span class="sxs-lookup"><span data-stu-id="ea653-136">**Visibility** : `important`</span></span>

![Uma captura de tela da guia definição na configuração do conector](./images/definition-tab.png)

<span data-ttu-id="ea653-138">Crie uma **solicitação** selecionando **importar de exemplo** e preencha os campos da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="ea653-138">Create **Request** by selecting **Import from Sample** and fill in the fields as follows.</span></span>

- <span data-ttu-id="ea653-139">**Verbo** : `POST`</span><span class="sxs-lookup"><span data-stu-id="ea653-139">**Verb** : `POST`</span></span>
- <span data-ttu-id="ea653-140">**URL** : `https://graph.microsoft.com/v1.0/$batch`</span><span class="sxs-lookup"><span data-stu-id="ea653-140">**URL** : `https://graph.microsoft.com/v1.0/$batch`</span></span>
- <span data-ttu-id="ea653-141">**Cabeçalhos** : deixar em branco</span><span class="sxs-lookup"><span data-stu-id="ea653-141">**Headers** : Leave blank</span></span>
- <span data-ttu-id="ea653-142">**Corpo** : `{}`</span><span class="sxs-lookup"><span data-stu-id="ea653-142">**Body** : `{}`</span></span>

<span data-ttu-id="ea653-143">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="ea653-143">Select **Import**.</span></span>

![Uma captura de tela da caixa de diálogo Importar de exemplo na configuração do conector](./images/import-sample.png)

<span data-ttu-id="ea653-145">Escolha **criar conector** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="ea653-145">Choose **Create Connector** on the top-right.</span></span> <span data-ttu-id="ea653-146">Após a criação do conector, copie a URL de **redirecionamento** gerado da página **segurança** .</span><span class="sxs-lookup"><span data-stu-id="ea653-146">After the connector has been created, copy the generated **Redirect URL** from **Security** page.</span></span>

![Uma captura de tela da URL de redirecionamento gerada](./images/redirect-url.png)

<span data-ttu-id="ea653-148">Volte para o aplicativo registrado no [portal do Azure](https://aad.portal.azure.com) que você criou no exercício anterior.</span><span class="sxs-lookup"><span data-stu-id="ea653-148">Go back to the registered application in the [Azure Portal](https://aad.portal.azure.com) you created in the previous exercise.</span></span> <span data-ttu-id="ea653-149">Selecione **autenticação** no menu do lado esquerdo.</span><span class="sxs-lookup"><span data-stu-id="ea653-149">Select **Authentication** on the left-hand side menu.</span></span> <span data-ttu-id="ea653-150">Selecione **Adicionar uma plataforma** e, em seguida, selecione **Web**.</span><span class="sxs-lookup"><span data-stu-id="ea653-150">Select **Add a platform** , then select **Web**.</span></span> <span data-ttu-id="ea653-151">Insira a URL de redirecionamento copiada da etapa anterior nos **URIs de redirecionamento** e, em seguida, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="ea653-151">Enter the redirect URL copied from the previous step in the **Redirect URIs** , then select **Configure**.</span></span>

![Uma captura de tela da lâmina URLs de resposta no portal do Azure](./images/update-app-reg.png)

## <a name="option-2-create-custom-connector-by-importing-openapi-file"></a><span data-ttu-id="ea653-153">Opção 2: criar um conector personalizado importando o arquivo OpenAPI</span><span class="sxs-lookup"><span data-stu-id="ea653-153">Option 2: Create custom connector by importing OpenAPI file</span></span>

<span data-ttu-id="ea653-154">Usando um editor de texto, crie um novo arquivo vazio chamado `MSGraph-Delegate-Batch.swagger.json` e adicione o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="ea653-154">Using a text editor, create a new empty file named `MSGraph-Delegate-Batch.swagger.json` and add the following code.</span></span>

[!code-json[](../LabFiles/MSGraph-Delegate-Batch.swagger.json)]

<span data-ttu-id="ea653-155">Abra um navegador e navegue até [Microsoft Power Automate](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ea653-155">Open a browser and navigate to [Microsoft Power Automate](https://flow.microsoft.com).</span></span> <span data-ttu-id="ea653-156">Entre com sua conta de administrador de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea653-156">Sign in with your Office 365 tenant administrator account.</span></span> <span data-ttu-id="ea653-157">Escolha **dados** no menu do lado esquerdo e selecione o item **conectores personalizados** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="ea653-157">Choose **Data** on the left-hand side menu, and select the **Custom Connectors** item in the drop-down menu.</span></span>

<span data-ttu-id="ea653-158">Na página **conectores personalizados** , escolha o link **novo conector personalizado** no canto superior direito e, em seguida, selecione o item **importar um arquivo do openapi** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="ea653-158">On the **Custom Connectors** page choose the **New custom connector** link in the top right, then select the **Import an OpenAPI file** item in the drop-down menu.</span></span>

<span data-ttu-id="ea653-159">Insira `MS Graph Batch Connector` na caixa de texto **nome do conector** .</span><span class="sxs-lookup"><span data-stu-id="ea653-159">Enter `MS Graph Batch Connector` in the **Connector name** text box.</span></span> <span data-ttu-id="ea653-160">Escolha o ícone de pasta para carregar o arquivo OpenAPI.</span><span class="sxs-lookup"><span data-stu-id="ea653-160">Choose the folder icon to upload the OpenAPI file.</span></span> <span data-ttu-id="ea653-161">Navegue até o `MSGraph-Delegate-Batch.swagger.json` arquivo que você criou.</span><span class="sxs-lookup"><span data-stu-id="ea653-161">Browse to the `MSGraph-Delegate-Batch.swagger.json` file you created.</span></span> <span data-ttu-id="ea653-162">Escolha **continuar** para carregar o arquivo openapi.</span><span class="sxs-lookup"><span data-stu-id="ea653-162">Choose **Continue** to upload the OpenAPI file.</span></span>

<span data-ttu-id="ea653-163">Na página configuração do conector, escolha o link **segurança** no menu de navegação.</span><span class="sxs-lookup"><span data-stu-id="ea653-163">On the connector configuration page, choose the **Security** link in the navigation menu.</span></span> <span data-ttu-id="ea653-164">Preencha os campos da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="ea653-164">Fill in the fields as follows.</span></span>

- <span data-ttu-id="ea653-165">**Escolha qual autenticação é implementada por sua API** : `OAuth 2.0`</span><span class="sxs-lookup"><span data-stu-id="ea653-165">**Choose what authentication is implemented by your API** : `OAuth 2.0`</span></span>
- <span data-ttu-id="ea653-166">**Provedor de identidade** : `Azure Active Directory`</span><span class="sxs-lookup"><span data-stu-id="ea653-166">**Identity Provider** : `Azure Active Directory`</span></span>
- <span data-ttu-id="ea653-167">**ID do cliente** : a ID do aplicativo que você criou no exercício anterior</span><span class="sxs-lookup"><span data-stu-id="ea653-167">**Client id** : the application ID you created in the previous exercise</span></span>
- <span data-ttu-id="ea653-168">**Segredo do cliente** : a chave que você criou no exercício anterior</span><span class="sxs-lookup"><span data-stu-id="ea653-168">**Client secret** : the key you created in the previous exercise</span></span>
- <span data-ttu-id="ea653-169">**URL de logon** : `https://login.windows.net`</span><span class="sxs-lookup"><span data-stu-id="ea653-169">**Login url** : `https://login.windows.net`</span></span>
- <span data-ttu-id="ea653-170">**ID do locatário** : `common`</span><span class="sxs-lookup"><span data-stu-id="ea653-170">**Tenant ID** : `common`</span></span>
- <span data-ttu-id="ea653-171">**URL do recurso** : `https://graph.microsoft.com` (sem à direita/)</span><span class="sxs-lookup"><span data-stu-id="ea653-171">**Resource URL** : `https://graph.microsoft.com` (no trailing /)</span></span>
- <span data-ttu-id="ea653-172">**Escopo** : deixar em branco</span><span class="sxs-lookup"><span data-stu-id="ea653-172">**Scope** : Leave blank</span></span>

<span data-ttu-id="ea653-173">Escolha **criar conector** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="ea653-173">Choose **Create Connector** on the top-right.</span></span> <span data-ttu-id="ea653-174">Após a criação do conector, copie a URL de **redirecionamento** gerada.</span><span class="sxs-lookup"><span data-stu-id="ea653-174">After the connector has been created, copy the generated **Redirect URL**.</span></span>

![Uma captura de tela da URL de redirecionamento gerada](./images/redirect-url.png)

<span data-ttu-id="ea653-176">Volte para o aplicativo registrado no [portal do Azure](https://aad.portal.azure.com) que você criou no exercício anterior.</span><span class="sxs-lookup"><span data-stu-id="ea653-176">Go back to the registered application in the [Azure Portal](https://aad.portal.azure.com) you created in the previous exercise.</span></span> <span data-ttu-id="ea653-177">Selecione **autenticação** no menu do lado esquerdo.</span><span class="sxs-lookup"><span data-stu-id="ea653-177">Select **Authentication** on the left-hand side menu.</span></span> <span data-ttu-id="ea653-178">Selecione **Adicionar uma plataforma** e, em seguida, selecione **Web**.</span><span class="sxs-lookup"><span data-stu-id="ea653-178">Select **Add a platform** , then select **Web**.</span></span> <span data-ttu-id="ea653-179">Insira a URL de redirecionamento copiada da etapa anterior nos **URIs de redirecionamento** e, em seguida, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="ea653-179">Enter the redirect URL copied from the previous step in the **Redirect URIs** , then select **Configure**.</span></span>

![Uma captura de tela da lâmina URLs de resposta no portal do Azure](./images/update-app-reg.png)
