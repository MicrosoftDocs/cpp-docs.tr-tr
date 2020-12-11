---
description: 'Hakkında daha fazla bilgi edinin: programı yerel sunucu olarak çalıştırma'
title: Programı yerel sunucu olarak çalıştırma
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: 1cdf3cef0773769318d68964b28bb60ca66666d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157497"
---
# <a name="running-the-program-as-a-local-server"></a>Programı yerel sunucu olarak çalıştırma

Programı bir hizmet olarak çalıştırırsanız, programın normal bir yerel sunucu olarak çalıştırılması için kayıt defterini geçici olarak değiştirebilirsiniz. `LocalService`Uygulama kimliği altındaki değeri olarak yeniden adlandırmanız yeterlidir `_LocalService` ve `LocalServer32` CLSID 'inizdeki anahtarın doğru şekilde ayarlandığından emin olun. (Uygulamanızın farklı bir bilgisayarda çalıştırılması gerektiğini belirtmek için DCOMCNFG ' ın kullanılması, anahtarınızı olarak yeniden adlandıryacağını unutmayın `LocalServer32` `_LocalServer32` .) Üzerinde yapılan çağrı `StartServiceCtrlDispatcher` `CAtlServiceModuleT::Start` başarısız olmadan önce birkaç saniye sürtiğinden, programınızı yerel sunucu olarak çalıştırmak başlangıçta birkaç saniye sürer.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama Ipuçları](../atl/debugging-tips.md)
