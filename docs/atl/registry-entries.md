---
title: Kayıt defteri girdileri (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac8e202fc2fc3d58e2d57a9fbfa15264d9fd310e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359735"
---
# <a name="registry-entries"></a>Kayıt defteri girdileri
DCOM kavramı, uygulama, kayıt defteri merkezi bir konumda içine bir veya daha fazla DCOM nesneleri için yapılandırma seçenekleri grup kimlikleri (uygulama) kullanıma sunmuştur. Adlı değer nesnesinin CLSID altında AppID değeriyle belirterek bir AppID belirtin.  
  
 ATL oluşturulan hizmet varsayılan olarak, kendi AppID için kendi CLSID GUID olarak kullanır. Altında `HKEY_CLASSES_ROOT\AppID`, DCOM özgü girişleri belirtebilirsiniz. Başlangıçta, iki giriş mevcuttur:  
  
-   `LocalService`, hizmet adına eşit bir değere sahip. Bu değeri varsa, bu yerine kullanıldığı `LocalServer32` CLSID altında anahtar.  
  
-   `ServiceParameters`, eşit bir değer ile `-Service`. Bu değer, başlatıldığında, hizmete geçirilecek parametreleri belirtir. Bu parametreler hizmetin geçirilir Not `ServiceMain` çalışmaz, `WinMain`.  
  
 Herhangi bir DCOM hizmeti de altında başka bir anahtar oluşturmak gereken `HKEY_CLASSES_ROOT\AppID`. Bu anahtar EXE adına eşit olan ve bir çapraz başvuru AppID girişlere işaret eden bir AppID değeri içeriyor gibi davranır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetler](../atl/atl-services.md)

