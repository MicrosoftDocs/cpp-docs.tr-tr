---
title: ODBC ve Veritabanı Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 7c69f49cbe233eb0782fdaa9767ea55f4d04203c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213210"
---
# <a name="odbc-and-the-database-classes"></a>ODBC ve Veritabanı Sınıfları

MFC ODBC veritabanı sınıfları, normalde kendinizi [CDatabase](../../mfc/reference/cdatabase-class.md) ve [CRecordset](../../mfc/reference/crecordset-class.md) SıNıFLARıNıN üye işlevlerinde yaptığınız ODBC API işlev çağrılarını kapsüller. Örneğin, karmaşık ODBC çağrı dizileri, döndürülen kayıtları depolama konumlarına bağlama, hata koşullarını işleme ve diğer işlemler veritabanı sınıfları tarafından yönetilir. Sonuç olarak, kayıtları bir kayıt kümesi nesnesi aracılığıyla işlemek için önemli ölçüde daha basit bir sınıf arabirimi kullanırsınız.

> [!NOTE]
>  ODBC veri kaynaklarına, bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla veya MFC veri erişim nesnesi (DAO) sınıfları aracılığıyla erişilebilir.

Veritabanı sınıfları ODBC işlevlerini kapsületse de, ODBC API işlevlerinin bire bir eşlemesini sağlamalardır. Veritabanı sınıfları, Microsoft Access ve Microsoft Visual Basic 'de bulunan veri erişimi nesnelerinden sonra Modellenen daha yüksek bir soyutlama düzeyi sağlar. Daha fazla bilgi için bkz. [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)
