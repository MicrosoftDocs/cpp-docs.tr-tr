---
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
ms.openlocfilehash: 1fb5164b9e744175f60c920a1d92278e9d5213f2
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51264664"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB Kaynak Havuzu ve Hizmetleri

OLE DB havuzu ile veya herhangi bir OLE DB hizmeti ile çalışmak için sağlayıcınıza tüm nesnelerin toplama desteklemesi gerekir. Bu, herhangi bir OLE DB 1.5 veya üzeri sağlayıcısı bir gereksinimdir. Hizmetlerinden yararlanarak için önemlidir. Toplama desteği yok sağlayıcıları havuza ve hiçbir ek hizmetler sağlanır.

Bir havuzda toplanabilir için sağlayıcıları boş iş parçacığı modeli desteklemesi gerekir. Kaynak havuzu sağlayıcının iş parçacığı modeli DBPROP_THREADMODEL özelliği göre belirler.

Sağlayıcı veri kaynağına başlatılmış durumdayken değişebilir bir genel bağlantı durumu varsa, yeni DBPROP_RESETDATASOURCE özelliği desteklemelidir. Bu özellik, bir bağlantı yeniden ve sağlayıcısı durumu sonraki kullanımından önce temizlemek için sürümümüze önce çağrılır. Sağlayıcı bağlantı ile ilişkili bazı durumu temizleyemiyor özelliği DBPROPSTATUS_NOTSETTABLE döndürebilir ve bağlantıyı yeniden kullanılabilir olmaz.

Uzak bir veritabanına bağlanmak ve bu bağlantının kaybolabilir olup olmadığını Algıla sağlayıcılar DBPROP_CONNECTIONSTATUS özelliği desteklemelidir. Bu özellik, OLE DB hizmetleri ölü bağlantıları algılama ve havuza geri döner olmayan emin olanağı sağlar.

Son olarak, otomatik bir işlem kaydı, genellikle havuzu oluşan ve aynı düzeyde uygulanır sürece çalışmaz. Bu liste DBPROP_INIT_OLEDBSERVICES özelliği gösterme ve DBPROPVAL_OS_TXNENLISTMENT kaldırılırsa, kaydı devre dışı bırakma devre dışı bırakma otomatik bir işlem kaydı desteği sağlayıcıları desteklemelidir.

## <a name="see-also"></a>Ayrıca Bkz.

[Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)