---
ms.openlocfilehash: d628ef3ffff3655bbb15115b6f17726e55185b5b
ms.sourcegitcommit: 64947f11d367ffbebbafb700fdfdc20617275f35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48829603"
---
<!-- markdownlint-disable MD002 MD041 -->

Há mais de 230 conectores de caixa de saída para automatização da Microsoft. Muitos desses conectores usam o Microsoft Graph para se comunicar com pontos de extremidade específicos de produtos da Microsoft. Além disso, há outros cenários em que pode ser necessário chamar o Microsoft Graph diretamente da automatização de energia usando blocos de construção básicos do serviço, já que não há conectores que se comunicam diretamente com o Microsoft Graph para cobrir toda a API.

Além de abordar cenários para chamar o Microsoft Graph diretamente, vários pontos de extremidade da API do Microsoft Graph só dão suporte a [permissões delegadas](https://docs.microsoft.com/graph/permissions-reference). O conector HTTP no Microsoft Power Automate permite integrações muito flexíveis, incluindo chamar o Microsoft Graph. No entanto, o conector HTTP não tem a capacidade de armazenar em cache as credenciais de um usuário para habilitar cenários de permissão delegada específicos. Nesses casos, um conector personalizado pode ser criado para fornecer um invólucro em torno da API do Microsoft Graph e habilitar o consumo da API com permissões delegadas.

Este laboratório aborda os dois cenários acima. Primeiro, você criará um conector personalizado para habilitar as integrações com o Microsoft Graph, que exigem [permissões delegadas](https://docs.microsoft.com/graph/permissions-reference). Em segundo lugar, você usará o [ponto de extremidade de solicitação $batch](https://docs.microsoft.com/graph/json-batching), para fornecer acesso a todo o poder do Microsoft Graph enquanto usa as permissões delegadas que exigem que um aplicativo tenha um usuário "conectado".

> [!NOTE]
> Este é um tutorial sobre como criar um conector personalizado para uso nos aplicativos do Microsoft Power Automate e do Azure Logic. Este tutorial pressupõe que você tenha lido a [visão geral do conector personalizado](https://docs.microsoft.com/connectors/custom-connectors/) para entender o processo.

## <a name="prerequisites"></a>Pré-requisitos

Para concluir este exercício nesta postagem, você precisará do seguinte:

- Acesso de administrador a uma locação do Office 365. Se você não tiver um, visite o [programa para desenvolvedores do Office 365](https://developer.microsoft.com/office/dev-program) para se inscrever de um locatário de desenvolvedor gratuito.
- Acesso à [Microsoft Power Automated](https://flow.microsoft.com/).

## <a name="feedback"></a>Comentários

Forneça comentários sobre este tutorial no [repositório do GitHub](https://github.com/microsoftgraph/msgraph-training-powerautomate).
