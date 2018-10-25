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
ms.openlocfilehash: 4635d482a08c486c1cf3259ae642fd82eb4bae82
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055950"
---
# <a name="access-to-odbc-and-sql"></a>ODBC'ye ve SQL'e Erişim

Microsoft Foundation Class Kitaplığı çok sayıda Windows API çağrıları kapsüller ve yine de herhangi bir Windows API işlevini doğrudan çağrı olanak tanır. Veritabanı sınıfları, ODBC API onaylamaz aynı esnekliğini sunar. Veritabanı sınıfları, ODBC karmaşıklığını çoğunu korurken, ODBC API işlevlerini doğrudan yerden çağırabilirsiniz programınızdaki.

Benzer şekilde, veritabanı sınıfları, ile çalışmak zorunda kalmaktan kalkanı [SQL](../../data/odbc/sql.md), ancak isterseniz SQL doğrudan kullanabilirsiniz. Kayıt kümesi nesneleri özel bir SQL deyimi (veya varsayılan deyim ayarı bölümlerini) geçirerek özelleştirebileceğiniz kayıt kümesini açtığınızda. Ayrıca kullanarak doğrudan SQL çağrıları yapabileceğiniz [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql) sınıfının üye işlevinde [CDatabase](../../mfc/reference/cdatabase-class.md).

Daha fazla bilgi için [ODBC: çağırma ODBC API işlevlerini doğrudan](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) ve [SQL: yapmadan doğrudan SQL çağrıları (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[ODBC ve MFC](../../data/odbc/odbc-and-mfc.md)