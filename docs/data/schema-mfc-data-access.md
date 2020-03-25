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
ms.openlocfilehash: 0eac4f47c3d00c34c1aadaef18202a95f831ad82
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209099"
---
# <a name="schema--mfc-data-access"></a>Şema (MFC veri erişimi)

Veritabanı şeması veritabanındaki tabloların ve veritabanı görünümlerinin geçerli yapısını açıklar. Genel olarak, sihirbaz tarafından oluşturulan kod, bir kayıt kümesi tarafından erişilen tablo veya tablolar şemasının değişmeyeceğini, ancak veritabanı sınıflarının ilişkisiz sütunları ekleme, yeniden düzenleme veya silme gibi bazı şema değişiklikleriyle ilgilendiğini varsayar. Bir tablo değişirse, tablo için kayıt kümesini el ile güncelleştirmeniz ve ardından uygulamanızı yeniden derlemeniz gerekir.

Ayrıca, derleme zamanında şeması tam olarak bilinmeyen bir veritabanıyla başa çıkmak için sihirbaz tarafından oluşturulan kodu da kullanabilirsiniz. Daha fazla bilgi için bkz. [kayıt kümesi: dinamik olarak veri sütunlarını bağlama (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri erişim programlama (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[Kayıt Kümesi (ODBC)](../data/odbc/recordset-odbc.md)
