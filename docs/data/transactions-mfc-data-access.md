---
title: İşlemler (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- transactions [C++], support for
- transactions [C++]
- databases [C++], transactions
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
ms.openlocfilehash: e3dc5b9319a8745ddb446ae7dbe895bfcd446c37
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037613"
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

## <a name="see-also"></a>Ayrıca bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)