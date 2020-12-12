---
description: 'Şu konuda daha fazla bilgi edinin: kayıt kümesi: kayıtları sıralama (ODBC)'
title: 'Kayıt Kümesi: Kayıtları Sıralama (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: fbf2ef3c42061bac9b41550a0c44a20f68c099b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204426"
---
# <a name="recordset-sorting-records-odbc"></a>Kayıt Kümesi: Kayıtları Sıralama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda, kayıt kümenizin nasıl sıralanacağını açıklanmaktadır. Sıralamayı temel alan bir veya daha fazla sütun belirtebilir ve artan veya azalan sıra (**ASC** veya **DESC**) belirtebilirsiniz. Her belirtilen sütun için **ASC** varsayılandır). Örneğin, iki sütun belirtirseniz, kayıtlar önce adlı ilk sütunda, sonra adlı ikinci sütunda sıralanır. Bir SQL **order by** yan tümcesi sıralamayı tanımlar. Framework **order by** yan tümcesini kayıt kümesinin SQL sorgusuna eklerse, yan tümce seçimin sıralamasını denetler.

Nesnesini oluşturduktan sonra, ancak üye işlevini çağırmadan önce `Open` (veya üye `Requery` `Open` işlevi daha önce çağrılan mevcut bir kayıt kümesi nesnesi için üye işlevini çağırmadan önce) bir kayıt kümesinin sıralama düzenini oluşturmanız gerekir.

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Bir kayıt kümesi nesnesi için sıralama düzeni belirtmek için

1. Yeni bir kayıt kümesi nesnesi oluşturun (veya var olan bir kayıt kümesini çağırmaya hazırlayın `Requery` ).

1. Nesnenin [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesinin değerini ayarlayın.

   Sıralama, null ile sonlandırılmış bir dizedir. **Order by** yan tümcesinin içeriğini içerir, ancak tarafından anahtar sözcük **sıralaması** değildir. Örneğin, aşağıdakileri kullanın:

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. Filtre, kilitleme modu veya parametreler gibi, ihtiyacınız olan diğer seçenekleri ayarlayın.

1. `Open`Yeni nesne (veya `Requery` varolan bir nesne için) çağrısı.

Seçilen kayıtlar belirtilen şekilde sıralanır. Örneğin, bir öğrenci kayıtları kümesini son ada göre azalan sırada sıralamak için, ardından adı ' nı yapın:

```cpp
// Construct the recordset
CStudentSet rsStudent( NULL );
// Set the sort
rsStudent.m_strSort = "LastName DESC, FirstName DESC";
// Run the query with the sort in place
rsStudent.Open( );
```

Kayıt kümesi tüm öğrenci kayıtlarını, son ada göre (Z-A) ve ardından ada göre sıralanmış bir şekilde içerir.

> [!NOTE]
> Kendi SQL dizenizi ' a geçirerek kayıt kümesinin varsayılan SQL dizesini geçersiz kılmayı seçerseniz `Open` , özel dizinizde **order by** yan tümcesi varsa sıralama ayarlamayın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: bir kayıt kümesini Parametreleştirirken (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
