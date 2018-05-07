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
ms.openlocfilehash: 55b95c5dd48631f9c724aebd163ce948c3469850
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API İşlevlerini Doğrudan Çağırma
Veritabanı sınıfları için basit bir arabirim sağlayan bir [veri kaynağı](../../data/odbc/data-source-odbc.md) ODBC daha. Sonuç olarak, sınıflar tüm ODBC API'larını değil. Sınıfların yeteneklerini dışında kalan herhangi bir işlevsellik için ODBC API işlevlerini doğrudan çağırmanız gerekir. Örneğin, ODBC katalog işlevlerini çağırmanız gerekir (**:: sütunu**, **:: SQLProcedures**, **:: SQLTables**ve diğerleri) doğrudan.  
  
> [!NOTE]
>  ODBC veri kaynakları, MFC veri erişim nesnesi (DAO) sınıfları veya bu konu başlığı altında açıklandığı gibi MFC ODBC sınıfları üzerinden erişilebilir.  
  
 Doğrudan ODBC API işlev çağrısı için framework olmadan çağrı yapıyorsanız götürecek aynı adımlar atmanız gerekir. Bunlar adımlardır:  
  
-   Depolama çağrı döndürdüğü herhangi bir sonuç için ayırın.  
  
-   Bir ODBC geçirmek **HDBC** veya **HSTMT** , işlev parametre imzası bağlı olarak işler. Kullanım [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv) makrosu ODBC tanıtıcısı alınamadı.  
  
     Üye değişkenleri **CDatabase::m_hdbc** ve **CRecordset::m_hstmt** ayırın ve bu kendiniz başlatma gerekmez böylece kullanılabilir.  
  
-   Belki de hazırlayın veya ana aramayı izleme için ek ODBC işlevlerini çağırın.  
  
-   Tamamladığınızda, depolama alanı ayırması.  
  
 Bu adımlar hakkında daha fazla bilgi için bkz: [açık veritabanı bağlantısı (ODBC)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) MSDN belgelerine SDK'da.  
  
 Bu adımları yanı sıra işlevi dönüş değerleri denetleyin, programınızı bir zaman uyumsuz çağrı bitirmek ve benzeri beklenmiyor sağlamak için ek adımlar gerekir. Son olarak bu adımları kullanarak basitleştirebilirsiniz `AFX_SQL_ASYNC` ve `AFX_SQL_SYNC` makroları. Daha fazla bilgi için bkz: [makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md) içinde *MFC başvurusu*.  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC Temelleri](../../data/odbc/odbc-basics.md)
