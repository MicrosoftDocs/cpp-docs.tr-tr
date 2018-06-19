---
title: Programı yerel bir sunucusu olarak çalışan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2b8a79978528493e02ac5a272dafe8da6fdc1d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360449"
---
# <a name="running-the-program-as-a-local-server"></a>Programı yerel bir sunucusu olarak çalışan
Program hizmet olarak çalışan kullanışsız ise, programın normal yerel sunucusu olarak çalışabilmesi kayıt geçici olarak değiştirebilirsiniz. Yalnızca yeniden adlandırmak `LocalService` , AppID altındaki değeri `_LocalService` ve olun `LocalServer32` , CLSID altında anahtarı doğru olarak ayarlayın. (Uygulamanızın farklı bir bilgisayarda çalıştırılması gerektiğini belirtmek için DCOMCNFG kullanarak adlandırır olduğunu unutmayın, `LocalServer32` anahtarını `_LocalServer32`.) Yerel bir sunucuya birkaç saniye daha başlangıçta çünkü yararlanırken, programı çalıştıran çağrısı **StartServiceCtrlDispatcher** içinde `CAtlServiceModuleT::Start` başarısız önce birkaç saniye sürer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama İpuçları](../atl/debugging-tips.md)

