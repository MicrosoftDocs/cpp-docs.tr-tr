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
ms.openlocfilehash: f7ba3e7b64a8c65678830593098ef658b3495c75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104704"
---
# <a name="schema--mfc-data-access"></a>Şema (MFC veri erişimi)
Bir veritabanı şeması tabloları ve veritabanı görünümleri veritabanında geçerli yapısını tanımlar. Genel olarak, sihirbaz tarafından oluşturulan kod şema, tablo veya bir kayıt kümesi tarafından erişilen tablolarda değişmez, ancak veritabanı sınıfları ekleme, yeniden sıralama veya ilişkisiz sütunları silme gibi bazı şema değişikliklerle ilgilenir varsayar. Bir tablo değişirse gerekir el ile tablosu için kayıt kümesi güncelleştirin ve ardından uygulamanızı yeniden derleyin.  
  
 Ayrıca, şema derleme zamanında tamamen bilinmeyen bir veritabanı uğraşmanız sihirbaz tarafından oluşturulan kodu destekleyebilirsiniz. Daha fazla bilgi için bkz: [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri erişimi (MFC/ATL) programlama](../data/data-access-programming-mfc-atl.md)   
 [SQL](../data/odbc/sql.md)   
 [Kayıt Kümesi (ODBC)](../data/odbc/recordset-odbc.md)