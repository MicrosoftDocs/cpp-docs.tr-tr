---
description: 'Daha fazla bilgi edinin: ODBC ve veritabanı sınıfları'
title: ODBC ve Veritabanı Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
ms.openlocfilehash: 146170ddd97dfc2797fd1f755459f370be638ded
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326776"
---
# <a name="odbc-and-the-database-classes"></a>ODBC ve Veritabanı Sınıfları

MFC ODBC veritabanı sınıfları, normalde kendinizi [CDatabase](../../mfc/reference/cdatabase-class.md) ve [CRecordset](../../mfc/reference/crecordset-class.md) SıNıFLARıNıN üye işlevlerinde yaptığınız ODBC API işlev çağrılarını kapsüller. Örneğin, karmaşık ODBC çağrı dizileri, döndürülen kayıtları depolama konumlarına bağlama, hata koşullarını işleme ve diğer işlemler veritabanı sınıfları tarafından yönetilir. Sonuç olarak, kayıtları bir kayıt kümesi nesnesi aracılığıyla işlemek için önemli ölçüde daha basit bir sınıf arabirimi kullanırsınız.

> [!NOTE]
> ODBC veri kaynaklarına, bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla veya MFC veri erişim nesnesi (DAO) sınıfları aracılığıyla erişilebilir.

Veritabanı sınıfları ODBC işlevlerini kapsületse de, ODBC API işlevlerinin bire bir eşlemesini sağlamalardır. Veritabanı sınıfları, Microsoft Access ve Microsoft Visual Basic 'de bulunan veri erişimi nesnelerinden sonra Modellenen daha yüksek bir soyutlama düzeyi sağlar. Daha fazla bilgi için bkz. [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[ODBC temelleri](../../data/odbc/odbc-basics.md)
