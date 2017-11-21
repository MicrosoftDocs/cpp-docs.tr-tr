---
title: "Kayıt defteri girdileri (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 013a5827af630e8190e622940c1fd3872a46a5d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="registry-entries"></a>Kayıt defteri girdileri
DCOM kavramı, uygulama, kayıt defteri merkezi bir konumda içine bir veya daha fazla DCOM nesneleri için yapılandırma seçenekleri grup kimlikleri (uygulama) kullanıma sunmuştur. Adlı değer nesnesinin CLSID altında AppID değeriyle belirterek bir AppID belirtin.  
  
 ATL oluşturulan hizmet varsayılan olarak, kendi AppID için kendi CLSID GUID olarak kullanır. Altında `HKEY_CLASSES_ROOT\AppID`, DCOM özgü girişleri belirtebilirsiniz. Başlangıçta, iki giriş mevcuttur:  
  
-   `LocalService`, hizmet adına eşit bir değere sahip. Bu değeri varsa, bu yerine kullanıldığı `LocalServer32` CLSID altında anahtar.  
  
-   `ServiceParameters`, eşit bir değer ile `-Service`. Bu değer, başlatıldığında, hizmete geçirilecek parametreleri belirtir. Bu parametreler hizmetin geçirilir Not `ServiceMain` çalışmaz, `WinMain`.  
  
 Herhangi bir DCOM hizmeti de altında başka bir anahtar oluşturmak gereken `HKEY_CLASSES_ROOT\AppID`. Bu anahtar EXE adına eşit olan ve bir çapraz başvuru AppID girişlere işaret eden bir AppID değeri içeriyor gibi davranır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)

