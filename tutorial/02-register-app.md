---
ms.openlocfilehash: 22c9c7ddd8513d857d96ade608e4b2e4e809dc41
ms.sourcegitcommit: 64947f11d367ffbebbafb700fdfdc20617275f35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48829618"
---
<!-- markdownlint-disable MD002 MD041 -->

Neste exercício, você criará um novo aplicativo do Azure Active Directory que será usado para fornecer as permissões delegadas para o conector personalizado.

Abra um navegador e navegue até o [centro de administração do Azure Active Directory](https://aad.portal.azure.com). Escolha o link do **Azure Active Directory** no menu de navegação à esquerda e, em seguida, escolha a entrada de **registros de aplicativos** na seção **gerenciar** da folha do **Azure Active Directory** .

![Uma captura de tela da lâmina do Azure Active Directory no centro de administração do Azure Active Directory](./images/app-registrations.png)

Escolha o item de menu **novo registro** na parte superior da folha **registros de aplicativo** .

![Uma captura de tela da lâmina de registros de aplicativos no centro de administração do Azure Active Directory](./images/new-registration.png)

Insira `MS Graph Batch App` no campo **nome** . Na seção **tipos de conta com suporte** , selecione **contas em qualquer diretório organizacional**. Deixe a seção **Redirecionar URI** em branco e escolha **registrar**.

![Uma captura de tela da folha registrar um aplicativo no centro de administração do Azure Active Directory](./images/register-an-app.png)

Na folha do **aplicativo de lote do MS Graph** , copie a **ID do aplicativo (cliente)**. Você precisará disso no próximo exercício.

![Uma captura de tela da página de aplicativo registrado](./images/app-id.png)

Escolha a entrada de **permissões de API** na seção **gerenciar** da folha do aplicativo de **lote do MS Graph** . Escolha **Adicionar uma permissão** em **permissões de API**.

![Uma captura de tela da lâmina de permissões de API](./images/api-permissions.png)

Na folha **solicitar permissões de API** , escolha o **Microsoft Graph** e, em seguida, escolha **permissões delegadas**. Procure `group` e selecione a permissão delegada **ler e gravar todos os grupos** . Escolha **adicionar permissões** na parte inferior da folha.

 ![Uma captura de tela da lâmina solicitar permissões de API](./images/select-permissions.png)

Escolha a entrada **certificados e segredos** na seção **gerenciar** da folha do **aplicativo de lote do MS Graph** e, em seguida, escolha **novo segredo do cliente**. Insira `forever` na **Descrição** e selecione **nunca** em **expirar**. Escolha **Adicionar**.

![Uma captura de tela da folha de certificados e segredos](./images/create-client-secret.png)

Copie o valor para o novo segredo. Você precisará disso no próximo exercício.

![Uma captura de tela do novo segredo do cliente](./images/copy-client-secret.png)

> [!IMPORTANT]
> Esta etapa é crítica, pois o segredo não estará acessível quando você fechar esta folha. Salve esse segredo em um editor de texto para usá-lo nos próximos exercícios.

Para habilitar o gerenciamento de serviços adicionais que podem ser acessados por meio do Microsoft Graph, incluindo as propriedades do Teams, você precisaria selecionar escopos adicionais e apropriados para habilitar o gerenciamento de serviços específicos. Por exemplo, para estender nossa solução para habilitar a criação de blocos de anotações do OneNote ou planos do Planner, Buckets e tarefas, você precisaria adicionar os escopos de permissão necessários para as APIs relevantes.
