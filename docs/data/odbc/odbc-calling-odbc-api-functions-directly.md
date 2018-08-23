---
title: 'ODBC: ODBC API çağırma işlevleri doğrudan | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0bd8ade91e2e543e8ccf1c0a9b04525b8d81b43
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465919"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API İşlevlerini Doğrudan Çağırma
Veritabanı sınıfları için basit bir arabirim sağlayan bir [veri kaynağı](../../data/odbc/data-source-odbc.md) ODBC gerçekleşti. Sonuç olarak, sınıfları ODBC API'larını içermez. Denk sınıfların yeteneklerini dışında herhangi bir işlevsellik için ODBC API işlevlerini doğrudan çağırmanız gerekir. Örneğin, ODBC katalog işlevleri çağırmanız gerekir (`::SQLColumns`, `::SQLProcedures`, `::SQLTables`ve diğerleri) doğrudan.  
  
> [!NOTE]
>  ODBC veri kaynakları, veri erişim nesnesi (DAO) MFC sınıfları veya bu konuda açıklandığı gibi MFC ODBC sınıfları aracılığıyla erişilebilir.  
  
 Doğrudan ODBC API işlevini çağırmak için çağrıları framework olmadan yapıyorsanız götürecek aynı adımları atmanız gerekir. Bunlar adımlar şunlardır:  
  
-   Çağrı döndürdüğü herhangi bir sonuç için depolamayı ayırır.  
  
-   Bir ODBC geçirmek `HDBC` veya `HSTMT` işlemek, işlevin parametre imzasına bağlı olarak. Kullanım [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) makrosu ODBC tanıtıcısı alınamadı.  
  
     Üye değişkenleri `CDatabase::m_hdbc` ve `CRecordset::m_hstmt` ayırın ve bunları kendiniz başlatın gerekmez, kullanılabilir.  
  
-   Belki de hazırlama veya ana aramayı izleme için ek ODBC işlevlerini çağırın.  
  
-   İşiniz bittiğinde, depolama serbest bırakın.  
  
 Bu adımlar hakkında daha fazla bilgi için bkz. [açık veritabanı bağlantısı (ODBC)](/previous-versions/windows/desktop/ms710252\(v=vs.85\)) SDK'sı MSDN belgelerinde.  
  
 Bu adımlar ek olarak, işlev dönüş değerlerini denetlemek, programınızı bitirmek ve benzeri zaman uyumsuz bir çağrı için beklenmiyor emin olmak için ek adımlar uygulaması gerekir. Son adımları AFX_SQL_ASYNC ve AFX_SQL_SYNC makroları kullanarak basitleştirebilirsiniz. Daha fazla bilgi için [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *MFC başvurusu*.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC Temelleri](../../data/odbc/odbc-basics.md)
