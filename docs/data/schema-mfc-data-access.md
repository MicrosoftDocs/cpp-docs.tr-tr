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
ms.openlocfilehash: cc333ee987ed0c6cba6cb11730d8f940e49d525d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039039"
---
# <a name="schema--mfc-data-access"></a>Şema (MFC veri erişimi)

Veritabanı şeması geçerli veritabanında veritabanı görünümleri ve tabloları yapısını açıklar. Genel olarak, sihirbaz tarafından üretilen kod tablonun veya tabloların bir kayıt kümesi tarafından erişilen için şema değişmeyecek, ancak veritabanı sınıfları ekleme, yeniden sıralama veya bağlı olmayan sütunları silme gibi bazı şema değişikliklerle başa varsayar. Bir tablo değişirse, el ile kayıt tablosu için güncelleştirme, ardından gerekir uygulamanızı derleyin.

Ayrıca, bir veritabanı şeması derleme zamanında tamamen bilinmiyor uğraşmanız sihirbazın ürettiği kod destekleyebilirsiniz. Daha fazla bilgi için [kayıt kümesi: (ODBC) veri sütunlarını dinamik olarak bağlama](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Kayıt Kümesi (ODBC)](../data/odbc/recordset-odbc.md)