---
title: OLE DB kaynak havuzu ve Hizmetleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab8c5e5a3e219da7204ef1a1b4942dc70b2f2ad2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111191"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB Kaynak Havuzu ve Hizmetleri
OLE DB havuzu ile iyi veya herhangi bir OLE DB hizmeti ile çalışmak için sağlayıcınız toplama tüm nesnelerin desteklemesi gerekir. Bu, herhangi bir OLE DB 1.5 veya daha sonraki sağlayıcısı gerekli değildir. Hizmetleri yararlanmak için kritik öneme sahiptir. Toplama desteklemeyen sağlayıcılar havuza alınamaz ve herhangi bir ek hizmet sağlanır.  
  
 Havuza için sağlayıcıları boş iş parçacığı modelini desteklemesi gerekir. Kaynak havuzu sağlayıcının iş parçacığı modelini göre belirler **DBPROP_THREADMODEL** özelliği.  
  
 Sağlayıcı veri kaynağı başlatılmış durumdayken değişebilir bir genel bağlantı durumu varsa, yeni desteklemelidir **DBPROP_RESETDATASOURCE** özelliği. Bu özellik, bir bağlantı yeniden kullanılır ve sağlayıcı sonraki kullanımından önce durumu temizleme fırsatı verir önce çağrılır. Sağlayıcı bağlantı ile ilişkili bazı durumunun temizleyemiyor, döndürebilir **DBPROPSTATUS_NOTSETTABLE** için özellik ve bağlantı kullanılmaz.  
  
 Uzak bir veritabanına bağlanan ve bağlantısı kaybolabilir desteklemesi gerekip gerekmediğini algılayabilir sağlayıcıları **DBPROP_CONNECTIONSTATUS** özelliği. Bu özellik, OLE DB hizmetleri ölü bağlantıları algılama ve havuza döndürülmez emin olmak için olanak sağlar.  
  
 Son olarak, havuzu oluşan aynı düzeyde uygulanan sürece otomatik işlem kaydı genellikle çalışmaz. Otomatik işlem kaydı kendilerini desteği sağlayıcıları destek göstererek bu kaydı devre dışı bırakma **DBPROP_INIT_OLEDBSERVICES** özelliği ve kaydı, devre dışı bırakma **DBPROPVAL_OS_ TXNENLISTMENT** seçilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)