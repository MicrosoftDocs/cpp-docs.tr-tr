---
title: OLE DB Kaynak Havuzu ve Hizmetleri
ms.date: 11/04/2016
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
ms.openlocfilehash: 7c57376404b37de95e01be6459b3d57ddcc53fe3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448106"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB Kaynak Havuzu ve Hizmetleri

OLE DB havuzu ile veya herhangi bir OLE DB hizmeti ile çalışmak için sağlayıcınıza tüm nesnelerin toplama desteklemesi gerekir. Bu, herhangi bir OLE DB 1.5 veya üzeri sağlayıcısı bir gereksinimdir. Hizmetlerinden yararlanarak için önemlidir. Toplama desteği yok sağlayıcıları havuza ve hiçbir ek hizmetler sağlanır.

Bir havuzda toplanabilir için sağlayıcıları boş iş parçacığı modeli desteklemesi gerekir. Kaynak havuzu konusunda anlatılan şekilde sağlayıcının iş parçacığı modeli belirler `DBPROP_THREADMODEL` özelliği.

Sağlayıcı veri kaynağına başlatılmış durumdayken değişebilir bir genel bağlantı durumu varsa, yeni desteklemelidir `DBPROP_RESETDATASOURCE` özelliği. Bu özellik, bir bağlantı yeniden ve sağlayıcısı durumu sonraki kullanımından önce temizlemek için sürümümüze önce çağrılır. Sağlayıcı bağlantı ile ilişkili bazı durumu temizleyemiyor verirseniz dönebilirsiniz `DBPROPSTATUS_NOTSETTABLE` için özellik ve bağlantı kullanılmaz.

Uzak bir veritabanına bağlanma ve bağlantıyı kaybolabilir desteklemesi gerekip gerekmediğini algılayabilir sağlayıcıları `DBPROP_CONNECTIONSTATUS` özelliği. Bu özellik, OLE DB hizmetleri ölü bağlantıları algılama ve havuza döndürülmez emin olanağı sağlar.

Son olarak, havuzu oluşan ve aynı düzeyde uygulanır sürece otomatik bir işlem kaydı genellikle işe yaramaz. Otomatik bir işlem kaydı kendilerini destekleyen sağlayıcıları göstererek bu kaydı devre dışı bırakma desteklemelidir `DBPROP_INIT_OLEDBSERVICES` özelliği ve kaydı devre dışı bırakmayı `DBPROPVAL_OS_TXNENLISTMENT` seçilmez.

## <a name="see-also"></a>Ayrıca Bkz.

[Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)