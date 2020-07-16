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
ms.openlocfilehash: e1cb5df4a93fc642ccf4d500a5eb93690b0b3d75
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403834"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API İşlevlerini Doğrudan Çağırma

Veritabanı sınıfları, ODBC 'den farklı bir [veri kaynağına](../../data/odbc/data-source-odbc.md) daha basit bir arabirim sağlar. Sonuç olarak, sınıflar tüm ODBC API 'leri kapsületmez. Sınıfların yeteneklerini aşacak olan tüm işlevler için doğrudan ODBC API işlevlerini çağırmanız gerekir. Örneğin, ODBC katalog işlevlerini (,, `::SQLColumns` `::SQLProcedures` `::SQLTables` , ve diğerleri) doğrudan çağırmanız gerekir.

> [!NOTE]
> ODBC veri kaynaklarına, bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla veya MFC veri erişim nesnesi (DAO) sınıfları aracılığıyla erişilebilir.

Bir ODBC API işlevini doğrudan çağırmak için, çerçeve olmadan çağrılar yaparken gerçekleştirebileceğiniz adımların aynısını uygulamanız gerekir. Adımlar şunlardır:

- Çağrının döndürdüğü tüm sonuçlar için depolama alanı ayırın.

- `HDBC` `HSTMT` İşlevin parametre imzasına bağlı olarak bir ODBC veya tanıtıcı geçirin. ODBC tanıtıcısını almak için [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) makrosunu kullanın.

   Üye değişkenleri `CDatabase::m_hdbc` ve `CRecordset::m_hstmt` bunları kendiniz ayırmanız ve başlatmak zorunda değilsiniz.

- Büyük olasılıkla ana çağrıyı hazırlamak veya izlemek için ek ODBC işlevleri çağırabilir.

- Bitirdiğinizde depolamayı serbest bırakın.

Bu adımlar hakkında daha fazla bilgi için bkz. [ODBC Programcı başvurusu](/sql/odbc/reference/odbc-programmer-s-reference).

Bu adımlara ek olarak, işlev dönüş değerlerini denetlemek için ek adımlar gerçekleştirmeniz, programınızın zaman uyumsuz bir çağrının bitmesini beklemediğinden emin olmak ve bu şekilde devam etmeniz gerekir. AFX_SQL_ASYNC ve AFX_SQL_SYNC makrolarını kullanarak bu son adımları kolaylaştırabilirsiniz. Daha fazla bilgi için bkz. [MFC makroları ve genel](../../mfc/reference/mfc-macros-and-globals.md)öğeleri.

## <a name="see-also"></a>Ayrıca bkz.

[ODBC temelleri](../../data/odbc/odbc-basics.md)
