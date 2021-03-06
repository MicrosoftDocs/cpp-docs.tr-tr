---
description: 'Hakkında daha fazla bilgi edinin: OLE DB kaynak havuzu ve Hizmetleri'
title: OLE DB Kaynak Havuzu ve Hizmetleri
ms.date: 10/29/2018
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
ms.openlocfilehash: 1a66a6a616ed67e70fb10fa1bf43dac634051325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286793"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB Kaynak Havuzu ve Hizmetleri

OLE DB havuzlarla veya herhangi bir OLE DB hizmeti ile birlikte çalışmak için, sağlayıcınız tüm nesneleri toplamayı desteklemelidir. Bu, 1,5 veya üzeri bir sağlayıcının OLE DB gereksinimidir. Hizmetlerin yararlanmak için önemlidir. Toplamayı desteklemeyen sağlayıcılar havuza alınamaz ve ek hizmet sağlanmaz.

Havuza almak için, sağlayıcıların ücretsiz iş parçacığı modelini desteklemesi gerekir. Kaynak havuzu, sağlayıcının iş parçacığı modelini DBPROP_THREADMODEL özelliğine göre belirler.

Sağlayıcının veri kaynağı başlatılmış durumdayken değişebilir bir genel bağlantı durumu varsa, yeni DBPROP_RESETDATASOURCE özelliğini desteklemelidir. Bu özellik, bir bağlantı yeniden kullanılmadan önce çağrılır ve sağlayıcıya bir sonraki kullanılmadan önce durumu temizleme fırsatı verir. Sağlayıcı bağlantıyla ilişkili bir durumu temizleyemezse, bu özellik için DBPROPSTATUS_NOTSETTABLE döndürebilir ve bağlantı tekrar kullanılamaz.

Uzak bir veritabanına bağlanan ve bu bağlantının kayıp olup olmadığını tespit eden sağlayıcılar DBPROP_CONNECTIONSTATUS özelliğini desteklemelidir. Bu özellik OLE DB hizmetlerine, ölü bağlantıları algılama ve havuza döndürülmeyen emin olma olanağı sağlar.

Son olarak, otomatik işlem kaydı, havuz oluşturma işleminin gerçekleştiği düzeyde uygulanmadığı takdirde genellikle çalışmaz. Otomatik işlem kaydı destekleyen sağlayıcılar, DBPROP_INIT_OLEDBSERVICES özelliğini ortaya çıkaran ve DBPROPVAL_OS_TXNENLISTMENT seçimi kaldırılırsa kaydı devre dışı bırakarak bu kaydı devre dışı bırakmayı desteklemelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Gelişmiş sağlayıcı teknikleri](../../data/oledb/advanced-provider-techniques.md)
