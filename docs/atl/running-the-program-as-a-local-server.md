---
title: "Programı yerel bir sunucusu olarak çalışan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 131bfefb35164b2d1e53f5671016235e5426c096
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="running-the-program-as-a-local-server"></a>Programı yerel bir sunucusu olarak çalışan
Program hizmet olarak çalışan kullanışsız ise, programın normal yerel sunucusu olarak çalışabilmesi kayıt geçici olarak değiştirebilirsiniz. Yalnızca yeniden adlandırmak `LocalService` , AppID altındaki değeri `_LocalService` ve olun `LocalServer32` , CLSID altında anahtarı doğru olarak ayarlayın. (Uygulamanızın farklı bir bilgisayarda çalıştırılması gerektiğini belirtmek için DCOMCNFG kullanarak adlandırır olduğunu unutmayın, `LocalServer32` anahtarını `_LocalServer32`.) Yerel bir sunucuya birkaç saniye daha başlangıçta çünkü yararlanırken, programı çalıştıran çağrısı **StartServiceCtrlDispatcher** içinde `CAtlServiceModuleT::Start` başarısız önce birkaç saniye sürer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama ipuçları](../atl/debugging-tips.md)

