---
title: İşlemler (MFC veri erişimi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a646d48be5128da701409cb0279612e9c049e518
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080812"
---
# <a name="transactions--mfc-data-access"></a>İşlemler (MFC veri erişimi)

Bir işlemin kavramı, sonuç durumu veritabanının üzerinde bir dizi işlem toplam başarılı olduğu durumlarda işlemek için geliştirilmiştir. Art arda işlemlerin önceki işlemlerinin sonuçlarını değiştirebilirsiniz çünkü bu gelebilir. Herhangi bir işlem başarısız olursa, bu gibi durumlarda, sonuç durumu belirsiz olabilir.

Bu sorunu çözmek için işlemleri gibi işlemlerde bir dizi Grup nihai sonucu bütünlüğünü garanti bir yol. Tüm işlemler başarısız ve ardından (veritabanına yazılan) kaydedilmiş veya tüm işlemi başarısız olur. İşlem iptaline bir geri alma olarak adlandırılır. Geri alma değişikliklere karşı bir kurtarma sağlar ve veritabanı işlem öncesi durumuna döndürülür.

Örneğin, bir otomatik bankacılık işlemde B hesabına bir hesaptan para aktarırsanız, hem mevcut Fonu doğru şekilde işlemek için bir ve havale hesabından b başarılı olması gerekir veya tüm işlemin başarısız olması.

Bir işlem, aşağıdakiler için bekleme ACID özelliklerini sahip olmanız gerekir:

- **Kararlılık** bir işlem atomik bir iş birimidir ve tam bir kez yürütülür; tüm iş yapılır ya da hiçbiri.

- **Tutarlılık** bir işlem başka bir tutarlı duruma verilerin tutarlı bir duruma veri dönüştürme veri tutarlılığını korur. Veri bağımlı bir işlem tarafından anlamsal olarak korunmalıdır.

- **Yalıtım** bir işlem yalıtım birimidir ve her ayrı olarak ve eş zamanlı işlem bağımsız olarak gerçekleşir. Bir işlem, hiçbir zaman başka bir işlem Ara aşamalarını görmeniz gerekir.

- **Dayanıklılık** kurtarma birimi bir işlemdir. İşlem başarılı olursa, sistem kilitlenme veya kapatılır olsa bile, güncelleştirmeleri kalıcı. Bir işlem başarısız olursa, sistem işlemi yapmadan durumunda kalır.

OLE DB'de işlemleri destekleyebilir (bkz [OLE DB'de işlemleri destekleme](../data/oledb/supporting-transactions-in-ole-db.md)) ya da ODBC'yi (bkz [işlem (ODBC)](../data/odbc/transaction-odbc.md)).

Dağıtılmış işlem dağıtılmış veriler, diğer bir deyişle, birden fazla ağa bağlı bilgisayar sistemi verileri güncelleştiren bir işlemdir. Dağıtılmış bir sistemde işlemleri desteklemek istiyorsanız, OLE DB transaction desteği yerine ADO.NET kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)