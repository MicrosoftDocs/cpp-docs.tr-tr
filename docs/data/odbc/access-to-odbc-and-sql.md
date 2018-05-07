---
title: ODBC'ye ve SQL'e erişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4fb5daa988614e7e9cb058fce183c6af5b50dd30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="access-to-odbc-and-sql"></a>ODBC'ye ve SQL'e Erişim
Microsoft Foundation Class Kitaplığı birçok Windows API çağrıları yalıtır ve hala doğrudan herhangi bir Windows API işlev çağrısı olanak tanır. Veritabanı sınıfları ODBC API ile aynı esneklik sağlar. Veritabanı sınıfları ODBC karmaşıklığını çoğunu sizden korurken, ODBC API işlevlerini doğrudan yerden çağırabilirsiniz programınızdaki.  
  
 Benzer şekilde, veritabanı sınıfları, ile çalışmak zorunda kalmaktan kalkanı [SQL](../../data/odbc/sql.md), ancak isterseniz, SQL'i doğrudan kullanabilirsiniz. Özel bir SQL deyimi (veya varsayılan deyimini ayarı bölümlerini) geçirerek kayıt kümesi nesneleri özelleştirebilirsiniz kayıt açtığınızda. Kullanarak doğrudan SQL çağrıları de yapabilirsiniz [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) sınıfının üye işlevini [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Daha fazla bilgi için bkz: [ODBC: çağırma ODBC API işlevlerini doğrudan](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) ve [SQL: yapmadan doğrudan SQL çağrıları (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)