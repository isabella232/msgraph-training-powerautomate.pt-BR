---
ms.openlocfilehash: 24aac7ad8709fd70d87f1a2d0d0ceecf99aed2db
ms.sourcegitcommit: 64947f11d367ffbebbafb700fdfdc20617275f35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48829601"
---
# <a name="microsoft-graph-training-module---create-a-microsoft-graph-json-batch-custom-connector-for-microsoft-power-automate--azure-logic-apps"></a><span data-ttu-id="f94a1-101">Módulo de treinamento do Microsoft Graph-criar um conector personalizado em lote do Microsoft Graph JSON para o Microsoft Power Automate & aplicativos de lógica do Azure</span><span class="sxs-lookup"><span data-stu-id="f94a1-101">Microsoft Graph Training Module - Create a Microsoft Graph JSON Batch Custom Connector for Microsoft Power Automate & Azure Logic Apps</span></span>

<span data-ttu-id="f94a1-102">Este módulo mostrará a você como trabalhar com a API REST de envio em lote do Microsoft Graph para acessar dados no Office 365.</span><span class="sxs-lookup"><span data-stu-id="f94a1-102">This module will introduce you to working with the Microsoft Graph JSON Batching REST API to access data in Office 365.</span></span> <span data-ttu-id="f94a1-103">Você aprenderá a criar e configurar um conector personalizado para automatizar da Microsoft, acessar a API de lote JSON do Microsoft Graph e usar o conector personalizado em um fluxo para criar uma equipe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f94a1-103">You will learn how to create and configure a custom connector for Microsoft Power Automate, access the the Microsoft Graph JSON Batch API, and use the custom connector in a flow to create a Microsoft Team.</span></span>

## <a name="lab---create-a-microsoft-graph-json-batch-custom-connector-for-microsoft-power-automate--azure-logic-apps"></a><span data-ttu-id="f94a1-104">Laboratório-criar um conector personalizado em lote do Microsoft Graph JSON para o Microsoft Power Automate & aplicativos de lógica do Azure</span><span class="sxs-lookup"><span data-stu-id="f94a1-104">Lab - Create a Microsoft Graph JSON Batch Custom Connector for Microsoft Power Automate & Azure Logic Apps</span></span>

<span data-ttu-id="f94a1-105">Neste laboratório, você usará a API REST de envio em lote do Microsoft Graph para criar um conector e um aplicativo de fluxo personalizados.</span><span class="sxs-lookup"><span data-stu-id="f94a1-105">In this lab you will leverage the Microsoft Graph JSON Batching REST API to create a Custom Connector and flow application.</span></span>

- [<span data-ttu-id="f94a1-106">Tutorial automatizar a automação do Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="f94a1-106">Power Automate Microsoft Graph tutorial</span></span>](https://docs.microsoft.com/graph/tutorials/powerautomate)

## <a name="contributors"></a><span data-ttu-id="f94a1-107">Colaboradores</span><span class="sxs-lookup"><span data-stu-id="f94a1-107">Contributors</span></span>

| <span data-ttu-id="f94a1-108">Funções</span><span class="sxs-lookup"><span data-stu-id="f94a1-108">Roles</span></span>       | <span data-ttu-id="f94a1-109">Autor (es)</span><span class="sxs-lookup"><span data-stu-id="f94a1-109">Author(s)</span></span>                                            |
|-------------|------------------------------------------------------|
| <span data-ttu-id="f94a1-110">Manuais de laboratório</span><span class="sxs-lookup"><span data-stu-id="f94a1-110">Lab Manuals</span></span> | <span data-ttu-id="f94a1-111">John Liu (Microsoft MVP, SharePointGurus) @johnnliu</span><span class="sxs-lookup"><span data-stu-id="f94a1-111">John Liu (Microsoft MVP, SharePointGurus) @johnnliu</span></span>  |
| <span data-ttu-id="f94a1-112">Manuais de laboratório</span><span class="sxs-lookup"><span data-stu-id="f94a1-112">Lab Manuals</span></span> | <span data-ttu-id="f94a1-113">@Pskelly Pete Skelly (ThreeWill)</span><span class="sxs-lookup"><span data-stu-id="f94a1-113">Pete Skelly (ThreeWill) @pskelly</span></span>                     |
| <span data-ttu-id="f94a1-114">Manuais de laboratório</span><span class="sxs-lookup"><span data-stu-id="f94a1-114">Lab Manuals</span></span> | <span data-ttu-id="f94a1-115">Ayca Bas (Microsoft) @aycabas</span><span class="sxs-lookup"><span data-stu-id="f94a1-115">Ayca Bas (Microsoft) @aycabas</span></span>                        |

## <a name="version-history"></a><span data-ttu-id="f94a1-116">Histórico de versão</span><span class="sxs-lookup"><span data-stu-id="f94a1-116">Version history</span></span>

| <span data-ttu-id="f94a1-117">Versão</span><span class="sxs-lookup"><span data-stu-id="f94a1-117">Version</span></span> | <span data-ttu-id="f94a1-118">Data</span><span class="sxs-lookup"><span data-stu-id="f94a1-118">Date</span></span>              | <span data-ttu-id="f94a1-119">Comentários</span><span class="sxs-lookup"><span data-stu-id="f94a1-119">Comments</span></span>                                             |
|---------|-------------------|------------------------------------------------------|
| <span data-ttu-id="f94a1-120">1.3</span><span class="sxs-lookup"><span data-stu-id="f94a1-120">1.3</span></span>     | <span data-ttu-id="f94a1-121">24 de agosto de 2020</span><span class="sxs-lookup"><span data-stu-id="f94a1-121">August 24, 2020</span></span>   | <span data-ttu-id="f94a1-122">Atualizado para automatizar a energia</span><span class="sxs-lookup"><span data-stu-id="f94a1-122">Updated to Power Automate</span></span>                            |
| <span data-ttu-id="f94a1-123">1.2</span><span class="sxs-lookup"><span data-stu-id="f94a1-123">1.2</span></span>     | <span data-ttu-id="f94a1-124">27 de novembro de 2018</span><span class="sxs-lookup"><span data-stu-id="f94a1-124">November 27, 2018</span></span> | <span data-ttu-id="f94a1-125">Integrado ao docs.microsoft.com/graph</span><span class="sxs-lookup"><span data-stu-id="f94a1-125">Onboarded to docs.microsoft.com/graph</span></span>                |
| <span data-ttu-id="f94a1-126">1.1</span><span class="sxs-lookup"><span data-stu-id="f94a1-126">1.1</span></span>     | <span data-ttu-id="f94a1-127">7 de novembro de 2018</span><span class="sxs-lookup"><span data-stu-id="f94a1-127">November 07, 2018</span></span> | <span data-ttu-id="f94a1-128">Adicionou o conteúdo da etapa 6 para chamar várias operações</span><span class="sxs-lookup"><span data-stu-id="f94a1-128">Added step 6 content for calling multiple operations</span></span> |
| <span data-ttu-id="f94a1-129">1.0</span><span class="sxs-lookup"><span data-stu-id="f94a1-129">1.0</span></span>     | <span data-ttu-id="f94a1-130">22 de outubro de 2018</span><span class="sxs-lookup"><span data-stu-id="f94a1-130">October 22, 2018</span></span>  | <span data-ttu-id="f94a1-131">Adicione debates de produtos relacionados ao Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="f94a1-131">Add Microsoft Graph related product breakouts.</span></span>       |

## <a name="disclaimer"></a><span data-ttu-id="f94a1-132">Aviso de isenção</span><span class="sxs-lookup"><span data-stu-id="f94a1-132">Disclaimer</span></span>

<span data-ttu-id="f94a1-133">**Este código é fornecido *como está* sem garantia de qualquer tipo, seja expressa ou implícita, incluindo quaisquer garantias implícitas de ADEQÜAÇÃO para um propósito específico, comercialização ou não-violação.**</span><span class="sxs-lookup"><span data-stu-id="f94a1-133">**THIS CODE IS PROVIDED *AS IS* WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESS OR IMPLIED, INCLUDING ANY IMPLIED WARRANTIES OF FITNESS FOR A PARTICULAR PURPOSE, MERCHANTABILITY, OR NON-INFRINGEMENT.**</span></span>
