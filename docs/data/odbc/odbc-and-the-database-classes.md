---
title: ODBC ve Veritabanı Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 6511aab9bb048882fe9c3398dd17f769eb16220c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320059"
---
# <a name="odbc-and-the-database-classes"></a>ODBC ve Veritabanı Sınıfları

MFC ODBC veritabanı sınıfları, normalde [CDatabase](../../mfc/reference/cdatabase-class.md) ve [CRecordset](../../mfc/reference/crecordset-class.md) sınıflarının üye işlevlerinde kendinizi yapacağınız ODBC API işlevini kapsüller. Örneğin, karmaşık ODBC çağrı dizileri, döndürülen kayıtların depolama konumlarına bağlanması, hata koşullarının işlenmesi ve diğer işlemler veritabanı sınıfları tarafından sizin için yönetilir. Sonuç olarak, kayıtları kayıt kümesi nesnesi üzerinden işlemek için çok daha basit bir sınıf arabirimi kullanırsınız.

> [!NOTE]
> ODBC veri kaynaklarına, bu konuda açıklandığı gibi MFC ODBC sınıfları veya MFC Veri Erişim Nesnesi (DAO) sınıfları aracılığıyla erişilebilir.

Veritabanı sınıfları ODBC işlevselliğini kapsüllese de, ODBC API işlevlerinin bire bir eşlemesi sağlamaz. Veritabanı sınıfları, Microsoft Access ve Microsoft Visual Basic'te bulunan veri erişim nesnelerinden sonra modellenen daha yüksek bir soyutlama düzeyi sağlar. Daha fazla bilgi için Bkz. [ODBC ve MFC.](../../data/odbc/odbc-and-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)
