---
description: "Hakkında daha fazla bilgi edinin: ODBC ve SQL 'e erişim"
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
ms.openlocfilehash: 507e3a8e2d88c253f193de41be1a28ae0c5cba87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295152"
---
# <a name="access-to-odbc-and-sql"></a>ODBC'ye ve SQL'e Erişim

Microsoft Foundation Class Kitaplığı birçok Windows API çağrısını kapsüller ve yine de herhangi bir Windows API işlevini doğrudan çağırmanıza imkan tanır. Veritabanı sınıfları, ODBC API 'SI ile ilgili olarak size aynı esnekliği sağlar. Veritabanı sınıfları ODBC 'nin karmaşıklığının büyük bir kısmını azaltırken, doğrudan programınızdaki herhangi bir yerden ODBC API işlevlerini çağırabilirsiniz.

Benzer şekilde, veritabanı sınıfları [SQL](../../data/odbc/sql.md)ile çok büyük bir çalışma yapmak zorunda kalmaktan, ancak isterseniz SQL 'i doğrudan kullanabilirsiniz. Kayıt kümesini açtığınızda özel bir SQL ifadesini geçirerek (veya varsayılan deyimin bölümlerini ayarlayarak), kayıt kümesi nesnelerini özelleştirebilirsiniz. Ayrıca, [CDatabase](../../mfc/reference/cdatabase-class.md)sınıfının [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) üye işlevini kullanarak doğrudan SQL çağrısı yapabilirsiniz.

Daha fazla bilgi için bkz. [ODBC: ODBC API Işlevlerini doğrudan çağırma](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) ve [SQL: doğrudan SQL ÇAĞRıLARı yapma (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)
