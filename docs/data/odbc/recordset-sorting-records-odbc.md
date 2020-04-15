---
title: 'Kayıt Kümesi: Kayıtları Sıralama (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: 8b4deea1d8cbd4abe01ccc7a4114131378abe463
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366919"
---
# <a name="recordset-sorting-records-odbc"></a>Kayıt Kümesi: Kayıtları Sıralama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, kayıt setinizin nasıl sıralanır olduğunu açıklar. Sıralamayı temel almak için bir veya daha fazla sütun belirtebilir ve artan veya azalan sırayı **(ASC** veya **DESC;** **ASC** varsayılan) belirtilen her sütun için. Örneğin, iki sütun belirtirseniz, kayıtlar önce ilk sütunda, sonra da ikinci sütunda sıralanır. SQL **ORDER BY** yan tümcesi bir sıralama tanımlar. Çerçeve, recordset'in SQL sorgusuna **ORDER BY** yan tümcesini ekladığında, yan tümce seçimin sırasını denetler.

Nesneyi oluşturduktan sonra ancak `Open` üye işlevini çağırmadan önce (veya `Requery` `Open` üye işlevi daha önce çağrılan varolan bir kayıt kümesi nesnesi için üye işlevi çağırmadan önce) bir kayıt kümesisıralama sırası oluşturmanız gerekir.

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Kayıt kümesi nesnesi için sıralama sırası belirtmek için

1. Yeni bir kayıt kümesi nesnesi `Requery` oluşturma (veya varolan bir nesneiçin aramaya hazırlanın).

1. Nesnenin [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesinin değerini ayarlayın.

   Sıralama, null-terminatedli bir dizedir. **Order BY** yan tümcesinin içeriğini içerir, ancak ANAHTAR SÖZCÜK **SİPARİş BY'yi**içermez. Örneğin, aşağıdakileri kullanın:

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. Filtre, kilitleme modu veya parametreler gibi ihtiyacınız olan diğer seçenekleri ayarlayın.

1. Yeni `Open` nesneyi (veya `Requery` varolan bir nesneyi) arayın.

Seçili kayıtlar belirtildiği gibi sıralanır. Örneğin, öğrenci kayıtları kümesini azalan sırada soyadına, sonra da ilk ada göre sıralamak için aşağıdakileri yapın:

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

Kayıt kümesi, azalan sırada (Z'den A'ya) soyadına, sonra da adadıyla sıralanan tüm öğrenci kayıtlarını içerir.

> [!NOTE]
> Kendi SQL dizenizi geçerek kayıt setinin varsayılan SQL `Open`dizesini geçersiz kılmayı seçerseniz, özel dizenizde **ORDER BY** yan tümcesi varsa bir sıralama ayarlamayın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
