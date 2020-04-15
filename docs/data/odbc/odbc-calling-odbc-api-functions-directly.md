---
title: 'ODBC: ODBC API İşlevlerini Doğrudan Çağırma'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
ms.openlocfilehash: 208749438f40eef746a638dd12373397c426d454
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368662"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API İşlevlerini Doğrudan Çağırma

Veritabanı sınıfları, veri [kaynağına](../../data/odbc/data-source-odbc.md) ODBC'den daha basit bir arabirim sağlar. Sonuç olarak, sınıflar tüm ODBC API kapsüllemek yok. Sınıfların yeteneklerinin dışına düşen herhangi bir işlevsellik için, Doğrudan ODBC API işlevlerini aramanız gerekir. Örneğin, ODBC katalog işlevlerini`::SQLColumns`(, `::SQLProcedures` `::SQLTables`, , ve diğerleri) doğrudan aramanız gerekir.

> [!NOTE]
> ODBC veri kaynaklarına, bu konuda açıklandığı gibi MFC ODBC sınıfları veya MFC Veri Erişim Nesnesi (DAO) sınıfları aracılığıyla erişilebilir.

Bir ODBC API işlevini doğrudan aramak için, çağrıları çerçeve olmadan yapıyorsanız, aynı adımları atmanız gerekir. Bunlar şunlardır:

- Aramanın iade edilen tüm sonuçlar için depolama alanı ayırın.

- İşlevin parametre imzasını bağlı olarak bir ODBC `HDBC` veya `HSTMT` tutamacı geçirin. ODBC tutamacını almak için [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) makroyu kullanın.

   Üye `CDatabase::m_hdbc` değişkenleri `CRecordset::m_hstmt` ve bunları kendiniz ayırmanız ve başlatmanız gerekmesin diye kullanılabilir.

- Belki de ana çağrıya hazırlanmak veya takip etmek için ek ODBC işlevlerini arayın.

- İşlem bittiğinde depolama alanını bulun.

Bu adımlar hakkında daha fazla bilgi için MSDN belgelerindeki [Açık Veritabanı Bağlantısı (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) SDK'ya bakın.

Bu adımlara ek olarak, işlev iade değerlerini denetlemek için ek adımlar atmanız, programınızın bitiş için asynchronous arama beklemediğinden emin olmanız ve söz leri s makrolar ve AFX_SQL_SYNC AFX_SQL_ASYNC kullanarak bu son adımları basitleştirebilirsiniz. Daha fazla bilgi için *MFC Başvurusu'ndaki* [Makrolar ve Genel Bilgiler'e](../../mfc/reference/mfc-macros-and-globals.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[ODBC Temelleri](../../data/odbc/odbc-basics.md)
