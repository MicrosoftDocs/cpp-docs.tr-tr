---
title: 'Kayıt kümesi: Kayıtları sıralama (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 304911c771be630fd3df867c46f8b01a08ed9d59
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080448"
---
# <a name="recordset-sorting-records-odbc"></a>Kayıt Kümesi: Kayıtları Sıralama (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konuda, kümenizin sıralama açıklanmaktadır. Bir veya daha fazla sütun sıralama temel belirtebilirsiniz ve artan veya azalan belirtebilirsiniz (**ASC** veya **DESC**; **ASC** varsayılandır) belirtilen her sütun için. Örneğin, iki sütun belirtirseniz, kayıtları ilk adlı ilk sütun ve ardından adlı ikinci sütunda sıralanır. Bir SQL **ORDER BY** yan tümcesinin sıralama tanımlar. Ne zaman framework ekler **ORDER BY** yan tümcesine kayıt kümenizin SQL sorgulama, seçimini sıralama yan tümcesi denetimleri.

Bir kayıt kümesinin sıralama düzeni nesneyi oluşturduktan sonra ancak çağırmadan önce oluşturmanız gerekir, `Open` üye işlevi (veya çağırmadan önce `Requery` üye işlevi için var olan bir kayıt kümesi nesnesi `Open` üye işlevi meydana geldi daha önce çağrılır).

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Kayıt kümesi nesnesi için bir sıralama düzeni belirlemek için

1. Yeni bir kayıt kümesi nesnesi oluşturun (veya çağrı hazırlanma `Requery` için mevcut bir).

1. Nesnenin değerini [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesi.

   Sıralama null ile sonlandırılmış bir dizedir. İçeriğini içerdiği **ORDER BY** yan tümcesi ancak anahtar sözcüğünü içermeyen **ORDER BY**. Örneğin, şunu kullanın:

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. Bir filtre, kilitleme modu veya parametreleri gibi gereken diğer seçeneklerini ayarlayın.

1. Çağrı `Open` yeni nesne için (veya `Requery` var olan bir nesne için).

Seçili kayıtların sıralı olarak belirtilen. Örneğin, Soyadı, ardından ad göre azalan düzende Öğrenci kayıt kümesini sıralamak için aşağıdakileri yapın:

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

Kayıt kümesi tüm azalan sırada (Z-A) olarak, ardından adlarına göre sıralanır Öğrenci kayıtları içerir.

> [!NOTE]
>  Kendi SQL dizesi geçirerek kümesinin varsayılan SQL dizesi geçersiz kılmak isterseniz `Open`, özel dizenizi varsa bir sıralama ayarlı değil bir **ORDER BY** yan tümcesi.

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)