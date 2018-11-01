---
title: Şema (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
ms.openlocfilehash: 2dcfb5d22cf84fed7313686c943fbbd7c7ce1c84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512495"
---
# <a name="schema--mfc-data-access"></a>Şema (MFC veri erişimi)

Veritabanı şeması geçerli veritabanında veritabanı görünümleri ve tabloları yapısını açıklar. Genel olarak, sihirbaz tarafından üretilen kod tablonun veya tabloların bir kayıt kümesi tarafından erişilen için şema değişmeyecek, ancak veritabanı sınıfları ekleme, yeniden sıralama veya bağlı olmayan sütunları silme gibi bazı şema değişikliklerle başa varsayar. Bir tablo değişirse, el ile kayıt tablosu için güncelleştirme, ardından gerekir uygulamanızı derleyin.

Ayrıca, bir veritabanı şeması derleme zamanında tamamen bilinmiyor uğraşmanız sihirbazın ürettiği kod destekleyebilirsiniz. Daha fazla bilgi için [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Kayıt Kümesi (ODBC)](../data/odbc/recordset-odbc.md)