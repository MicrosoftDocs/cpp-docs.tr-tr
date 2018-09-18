---
title: Şema (MFC veri erişimi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7ff1759203593cd556a91cbe17b93388488a2b07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091250"
---
# <a name="schema--mfc-data-access"></a>Şema (MFC veri erişimi)

Veritabanı şeması geçerli veritabanında veritabanı görünümleri ve tabloları yapısını açıklar. Genel olarak, sihirbaz tarafından üretilen kod tablonun veya tabloların bir kayıt kümesi tarafından erişilen için şema değişmeyecek, ancak veritabanı sınıfları ekleme, yeniden sıralama veya bağlı olmayan sütunları silme gibi bazı şema değişikliklerle başa varsayar. Bir tablo değişirse, el ile kayıt tablosu için güncelleştirme, ardından gerekir uygulamanızı derleyin.  
  
Ayrıca, bir veritabanı şeması derleme zamanında tamamen bilinmiyor uğraşmanız sihirbazın ürettiği kod destekleyebilirsiniz. Daha fazla bilgi için [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Kayıt Kümesi (ODBC)](../data/odbc/recordset-odbc.md)