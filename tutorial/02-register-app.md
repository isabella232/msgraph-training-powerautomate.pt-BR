---
ms.openlocfilehash: 22c9c7ddd8513d857d96ade608e4b2e4e809dc41
ms.sourcegitcommit: 64947f11d367ffbebbafb700fdfdc20617275f35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48829618"
---
<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="29bf0-101">Neste exercício, você criará um novo aplicativo do Azure Active Directory que será usado para fornecer as permissões delegadas para o conector personalizado.</span><span class="sxs-lookup"><span data-stu-id="29bf0-101">In this exercise, you will create a new Azure Active Directory Application which will be used to provide the delegated permissions for the custom connector.</span></span>

<span data-ttu-id="29bf0-102">Abra um navegador e navegue até o [centro de administração do Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="29bf0-102">Open a browser and navigate to [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="29bf0-103">Escolha o link do **Azure Active Directory** no menu de navegação à esquerda e, em seguida, escolha a entrada de **registros de aplicativos** na seção **gerenciar** da folha do **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="29bf0-103">Choose the **Azure Active Directory** link in the left navigation menu, then choose the **App registrations** entry in the **Manage** section of the **Azure Active Directory** blade.</span></span>

![Uma captura de tela da lâmina do Azure Active Directory no centro de administração do Azure Active Directory](./images/app-registrations.png)

<span data-ttu-id="29bf0-105">Escolha o item de menu **novo registro** na parte superior da folha **registros de aplicativo** .</span><span class="sxs-lookup"><span data-stu-id="29bf0-105">Choose the **New registration** menu item at the top of the **App Registrations** blade.</span></span>

![Uma captura de tela da lâmina de registros de aplicativos no centro de administração do Azure Active Directory](./images/new-registration.png)

<span data-ttu-id="29bf0-107">Insira `MS Graph Batch App` no campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="29bf0-107">Enter `MS Graph Batch App` in the **Name** field.</span></span> <span data-ttu-id="29bf0-108">Na seção **tipos de conta com suporte** , selecione **contas em qualquer diretório organizacional**.</span><span class="sxs-lookup"><span data-stu-id="29bf0-108">In the **Supported account types** section, select **Accounts in any organizational directory**.</span></span> <span data-ttu-id="29bf0-109">Deixe a seção **Redirecionar URI** em branco e escolha **registrar**.</span><span class="sxs-lookup"><span data-stu-id="29bf0-109">Leave the **Redirect URI** section blank and choose **Register**.</span></span>

![Uma captura de tela da folha registrar um aplicativo no centro de administração do Azure Active Directory](./images/register-an-app.png)

<span data-ttu-id="29bf0-111">Na folha do **aplicativo de lote do MS Graph** , copie a **ID do aplicativo (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="29bf0-111">On the **MS Graph Batch App** blade, copy the **Application (client) ID**.</span></span> <span data-ttu-id="29bf0-112">Você precisará disso no próximo exercício.</span><span class="sxs-lookup"><span data-stu-id="29bf0-112">You'll need this in the next exercise.</span></span>

![Uma captura de tela da página de aplicativo registrado](./images/app-id.png)

<span data-ttu-id="29bf0-114">Escolha a entrada de **permissões de API** na seção **gerenciar** da folha do aplicativo de **lote do MS Graph** .</span><span class="sxs-lookup"><span data-stu-id="29bf0-114">Choose the **API permissions** entry in the **Manage** section of the **MS Graph Batch App** blade.</span></span> <span data-ttu-id="29bf0-115">Escolha **Adicionar uma permissão** em **permissões de API**.</span><span class="sxs-lookup"><span data-stu-id="29bf0-115">Choose **Add a permission** under **API permissions**.</span></span>

![Uma captura de tela da lâmina de permissões de API](./images/api-permissions.png)

<span data-ttu-id="29bf0-117">Na folha **solicitar permissões de API** , escolha o **Microsoft Graph** e, em seguida, escolha **permissões delegadas**.</span><span class="sxs-lookup"><span data-stu-id="29bf0-117">In the **Request API permissions** blade, choose the **Microsoft Graph** , then choose **Delegated permissions**.</span></span> <span data-ttu-id="29bf0-118">Procure `group` e selecione a permissão delegada **ler e gravar todos os grupos** .</span><span class="sxs-lookup"><span data-stu-id="29bf0-118">Search for `group`, then select the **Read and write all groups** delegated permission.</span></span> <span data-ttu-id="29bf0-119">Escolha **adicionar permissões** na parte inferior da folha.</span><span class="sxs-lookup"><span data-stu-id="29bf0-119">Choose **Add permissions** at the bottom of the blade.</span></span>

 ![Uma captura de tela da lâmina solicitar permissões de API](./images/select-permissions.png)

<span data-ttu-id="29bf0-121">Escolha a entrada **certificados e segredos** na seção **gerenciar** da folha do **aplicativo de lote do MS Graph** e, em seguida, escolha **novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="29bf0-121">Choose the **Certificates and secrets** entry in the **Manage** section of the **MS Graph Batch App** blade, then choose **New client secret**.</span></span> <span data-ttu-id="29bf0-122">Insira `forever` na **Descrição** e selecione **nunca** em **expirar**.</span><span class="sxs-lookup"><span data-stu-id="29bf0-122">Enter `forever` in the **Description** and select **Never** under **Expires**.</span></span> <span data-ttu-id="29bf0-123">Escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="29bf0-123">Choose **Add**.</span></span>

![Uma captura de tela da folha de certificados e segredos](./images/create-client-secret.png)

<span data-ttu-id="29bf0-125">Copie o valor para o novo segredo.</span><span class="sxs-lookup"><span data-stu-id="29bf0-125">Copy the value for the new secret.</span></span> <span data-ttu-id="29bf0-126">Você precisará disso no próximo exercício.</span><span class="sxs-lookup"><span data-stu-id="29bf0-126">You'll need this in the next exercise.</span></span>

![Uma captura de tela do novo segredo do cliente](./images/copy-client-secret.png)

> [!IMPORTANT]
> <span data-ttu-id="29bf0-128">Esta etapa é crítica, pois o segredo não estará acessível quando você fechar esta folha.</span><span class="sxs-lookup"><span data-stu-id="29bf0-128">This step is critical as the secret will not be accessible once you close this blade.</span></span> <span data-ttu-id="29bf0-129">Salve esse segredo em um editor de texto para usá-lo nos próximos exercícios.</span><span class="sxs-lookup"><span data-stu-id="29bf0-129">Save this secret to a text editor for use in upcoming exercises.</span></span>

<span data-ttu-id="29bf0-130">Para habilitar o gerenciamento de serviços adicionais que podem ser acessados por meio do Microsoft Graph, incluindo as propriedades do Teams, você precisaria selecionar escopos adicionais e apropriados para habilitar o gerenciamento de serviços específicos.</span><span class="sxs-lookup"><span data-stu-id="29bf0-130">To enable management of additional services accessible via the Microsoft Graph, including Teams properties, you would need to select additional, appropriate scopes to enable managing specific services.</span></span> <span data-ttu-id="29bf0-131">Por exemplo, para estender nossa solução para habilitar a criação de blocos de anotações do OneNote ou planos do Planner, Buckets e tarefas, você precisaria adicionar os escopos de permissão necessários para as APIs relevantes.</span><span class="sxs-lookup"><span data-stu-id="29bf0-131">For example, to extend our solution to enable creating OneNote Notebooks or Planner plans, buckets and tasks you would need to add the required permission scopes for the relevant APIs.</span></span>
