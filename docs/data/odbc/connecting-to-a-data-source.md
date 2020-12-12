---
description: 'Hakkında daha fazla bilgi edinin: bir veri kaynağına bağlanma'
title: Veri Kaynağına Bağlanma
ms.date: 11/04/2016
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
ms.openlocfilehash: 3bc5436a678d39682b89d82dd7f3ab90eb6f5bb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295126"
---
# <a name="connecting-to-a-data-source"></a>Veri Kaynağına Bağlanma

ODBC veri kaynağı, belirli bir veri kümesidir, bu verilere erişmek için gereken bilgiler ve veri kaynağının konumu veri kaynağı adı kullanılarak açıklanabilir. Programınızın bakış noktasından veri kaynağı, verileri, DBMS 'yi, ağı (varsa) ve ODBC 'yi içerir.

Bir veri kaynağı tarafından sunulan verilere erişmek için, programınızın öncelikle veri kaynağıyla bağlantı kurması gerekir. Tüm veri erişimleri Bu bağlantı üzerinden yönetilir.

Veri kaynağı bağlantıları, [CDatabase](../../mfc/reference/cdatabase-class.md)sınıfına göre kapsüllenir. Bir `CDatabase` nesne bir veri kaynağına bağlandığında şunları yapabilirsiniz:

- Tablolardan veya sorgulardan kayıtları seçmek için [kayıt kümeleri](../../mfc/reference/crecordset-class.md)oluşturun.

- [İşlemleri](../../data/odbc/transaction-odbc.md)yönetin, tüm güncelleştirmeler toplu olarak veri kaynağına uygulanır. veri kaynağı gerekli işlem düzeyini destekliyorsa, tüm işlem, veri kaynağı değiştirilmeden geri alınır.

- Doğrudan [SQL](../../data/odbc/sql.md) deyimlerini yürütün.

Bir veri kaynağı bağlantısıyla çalışmayı bitirdiğinizde `CDatabase` nesneyi kapatır ve bunu yok edin ya da yeni bir bağlantı için yeniden kullanın. Veri kaynağı bağlantıları hakkında daha fazla bilgi için bkz. [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)
