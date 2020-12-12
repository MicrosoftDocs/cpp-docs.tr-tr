---
description: 'Daha fazla bilgi edinin: Işlemler (MFC veri erişimi)'
title: İşlemler (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
ms.openlocfilehash: bd04e1c8f1b5ef11e66a3c2c3f1e391f409b4892
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116489"
---
# <a name="transactions--mfc-data-access"></a>İşlemler (MFC veri erişimi)

Bir işlem kavramı, veritabanının elde edilen durumunun, bir dizi işlemin toplam başarısına bağlı olduğu durumları işleyecek şekilde geliştirilmiştir. Ardışık işlemler önceki işlemlerin sonuçlarını değiştirebileceğinden bu durum hakkında bilgi alabilirsiniz. Bu gibi durumlarda, herhangi bir işlem başarısız olursa, ortaya çıkan durum belirsiz olabilir.

Bu sorunu çözmek için, işlemler, nihai sonucun bütünlüğünden emin olmak üzere bir dizi işlemi gruplar. Tüm işlemlerin başarılı olması ve ardından yürütülmesi (veritabanına yazılması) ya da işlemin tamamı başarısız olması gerekir. İşlemin iptaline geri alma denir. Geri alma, değişikliklerden kurtarmaya izin verir ve veritabanını ön işlem durumuna getirir.

Örneğin, bir otomatik bankacılık işleminde, A hesabından hesap B 'ye para aktarırsanız, hem bir A 'nın hem de B 'ye yatırın her ikisi de fonları doğru şekilde işlemek için başarılı olmalıdır veya tüm işlem başarısız olmalıdır.

Bir işlem, şunlar için tek başına ACID özelliklerine sahip olmalıdır:

- **Atomicity** İşlem atomik bir iş birimidir ve tam olarak bir kez yürütülür; Tüm işler bitti veya hiç yok.

- **Tutarlılık** Bir işlem verilerin tutarlılığını korur ve verilerin tutarlı bir durumunu başka bir tutarlı veri durumuna dönüştürür. Bir işlem tarafından verilerin bağlanması anlam olarak korunmalıdır.

- **Yalıtım** Bir işlem, yalıtım birimidir ve her biri ayrı olarak ve eşzamanlı işlemlerden bağımsız olarak gerçekleşir. Bir işlem, başka bir işlemin ara aşamalarını asla görmemelidir.

- **Dayanıklılık** İşlem bir kurtarma birimidir. Bir işlem başarılı olursa, sistem kilitlense veya kapatılmış olsa bile, güncelleştirmeleri kalır. Bir işlem başarısız olursa, sistem işlemi işlemeden önceki durumda kalır.

OLE DB işlemleri destekleyebilirsiniz (bkz. [OLE DB ' de Işlemleri destekleme](../data/oledb/supporting-transactions-in-ole-db.md)) veya ODBC (bkz. [işlem (ODBC)](../data/odbc/transaction-odbc.md)).

Dağıtılmış işlem, dağıtılmış verileri, diğer bir deyişle, birden fazla ağa bağlı bilgisayar sistemindeki verileri güncelleştiren bir işlemdir. Dağıtılmış bir sistem üzerinden işlemleri desteklemek istiyorsanız, OLE DB işlem desteği yerine ADO.NET kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)
