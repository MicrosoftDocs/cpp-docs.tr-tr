---
title: ODBC'ye ve SQL'e Erişim
ms.date: 11/04/2016
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
ms.openlocfilehash: 7a539d911bbf4f4d9582da0ebedaeffaa0d8fa7b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030160"
---
# <a name="access-to-odbc-and-sql"></a>ODBC'ye ve SQL'e Erişim

Microsoft Foundation Class Kitaplığı çok sayıda Windows API çağrıları kapsüller ve yine de herhangi bir Windows API işlevini doğrudan çağrı olanak tanır. Veritabanı sınıfları, ODBC API onaylamaz aynı esnekliğini sunar. Veritabanı sınıfları, ODBC karmaşıklığını çoğunu korurken, ODBC API işlevlerini doğrudan yerden çağırabilirsiniz programınızdaki.

Benzer şekilde, veritabanı sınıfları, ile çalışmak zorunda kalmaktan kalkanı [SQL](../../data/odbc/sql.md), ancak isterseniz SQL doğrudan kullanabilirsiniz. Kayıt kümesi nesneleri özel bir SQL deyimi (veya varsayılan deyim ayarı bölümlerini) geçirerek özelleştirebileceğiniz kayıt kümesini açtığınızda. Ayrıca kullanarak doğrudan SQL çağrıları yapabileceğiniz [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) sınıfının üye işlevinde [CDatabase](../../mfc/reference/cdatabase-class.md).

Daha fazla bilgi için [ODBC: Arama ODBC API işlevlerini doğrudan](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) ve [SQL: Doğrudan SQL çağrıları yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)