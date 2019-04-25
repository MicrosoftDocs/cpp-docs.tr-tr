---
title: Programı yerel sunucu olarak çalıştırma
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
ms.openlocfilehash: a412814fc5f3900a248f779501e2720b72287e57
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196528"
---
# <a name="running-the-program-as-a-local-server"></a>Programı yerel sunucu olarak çalıştırma

Program, hizmet olarak çalışan kullanışsız ise, program normal yerel sunucu olarak çalıştırılır, böylece kayıt geçici olarak değiştirebilirsiniz. Yalnızca yeniden adlandırma `LocalService` değeri için AppID altında `_LocalService` olun `LocalServer32` anahtarı altına, düzgün şekilde ayarlandığını. (Uygulamanızın farklı bir bilgisayarda çalışması gerektiğini belirtmek için DCOMCNFG kullanarak adlandırır olduğunu unutmayın, `LocalServer32` anahtarını `_LocalServer32`.) Yerel bir sunucuya çünkü başlangıçta birkaç saniye daha aldığından programınızı çalıştıran çağrısı `StartServiceCtrlDispatcher` içinde `CAtlServiceModuleT::Start` başarısız önce birkaç saniye sürer.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama İpuçları](../atl/debugging-tips.md)
