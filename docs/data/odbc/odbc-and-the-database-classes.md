---
title: ODBC ve veritabanı sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9e179bf7570ba2ce53369d59c836e8accf91e8de
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057954"
---
# <a name="odbc-and-the-database-classes"></a>ODBC ve Veritabanı Sınıfları

MFC ODBC veritabanı sınıfları normalde yaptığınız kendiniz üye işlevlerini ODBC API işlev çağrılarını kapsülleyen [CDatabase](../../mfc/reference/cdatabase-class.md) ve [CRecordset](../../mfc/reference/crecordset-class.md) sınıfları. Örneğin, karmaşık ODBC çağrı dizileri, depolama konumları, hata koşullarını işleme ve diğer işlemleri için döndürülen kayıtları bağlamasının sizin için veritabanı sınıfları tarafından yönetilir. Sonuç olarak, bir kayıt kümesi nesnesi kayıtlarını işlemek için daha basit bir sınıf arabirimi kullanın.

> [!NOTE]
>  ODBC veri kaynakları, veri erişim nesnesi (DAO) MFC sınıfları veya bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla erişilebilir.

Veritabanı sınıfları ODBC işlevi kapsülleyen olsa da, bire bir eşleme ODBC API işlevleri sağlamaz. Veritabanı sınıfları daha yüksek düzeyde soyutlama, veri erişim nesneleri Microsoft Access ve Microsoft Visual Basic'te bulunduktan sonra modellenmiş sağlar. Daha fazla bilgi için [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)