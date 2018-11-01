---
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
ms.openlocfilehash: b7bb0ffe169fd9b4167e6af4b772df23acf02212
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575532"
---
# <a name="connecting-to-a-data-source"></a>Veri Kaynağına Bağlanma

ODBC veri kaynağında verileri, verilerin yanı sıra, bir veri kaynağı adını kullanarak açıklanan veri kaynağının konumu erişmek için gereken bilgileri belirli bir kümesidir. Programınızın açısından bakıldığında, verileri, DBMS, ağ (varsa) ve ODBC veri kaynağını içerir.

Bir veri kaynağı tarafından sağlanan verilere erişmek için programınızı ilk veri kaynağı bağlantısı oluşturmanız gerekir. Tüm veri erişimi, bu bağlantı üzerinden yönetilir.

Veri kaynağı bağlantıları sınıfı tarafından Kapsüllenen [CDatabase](../../mfc/reference/cdatabase-class.md). Olduğunda bir `CDatabase` nesnesi, bir veri kaynağına bağlı olduğundan, aşağıdakileri yapabilirsiniz:

- Oluşturmak [kayıt kümeleri](../../mfc/reference/crecordset-class.md), tablolar veya sorguların kayıtları seçin.

- Yönetme [işlemleri](../../data/odbc/transaction-odbc.md), toplu güncelleştirmeler tüm veri kaynağına teslim tek seferde (veya veri kaynağına geri değişmeden, bu nedenle tüm işlem alınır) — veri kaynağı işlemleri gerekli düzeyi destekliyorsa.

- Doğrudan yürütme [SQL](../../data/odbc/sql.md) deyimleri.

Veri kaynağı bağlantısı ile çalışmayı bitirdiğinizde, siz kapatana `CDatabase` nesne ve onu yok veya yeniden kullanmak için yeni bir bağlantı. Veri kaynağı bağlantıları hakkında daha fazla bilgi için bkz. [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)