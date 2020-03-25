---
title: 'Kayıt Kümesi: Kayıtları Sıralama (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
ms.openlocfilehash: 4bbe635cdda9152be6ba178b863147db93b7c706
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212751"
---
# <a name="recordset-sorting-records-odbc"></a>Kayıt Kümesi: Kayıtları Sıralama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda, kayıt kümenizin nasıl sıralanacağını açıklanmaktadır. Sıralamayı temel alan bir veya daha fazla sütun belirtebilir ve artan veya azalan sıra (**ASC** veya **DESC**) belirtebilirsiniz. Her belirtilen sütun için **ASC** varsayılandır). Örneğin, iki sütun belirtirseniz, kayıtlar önce adlı ilk sütunda, sonra adlı ikinci sütunda sıralanır. Bir SQL **order by** yan tümcesi sıralamayı tanımlar. Framework **order by** yan tümcesini kayıt kümesinin SQL sorgusuna eklerse, yan tümce seçimin sıralamasını denetler.

Nesnesini oluşturduktan sonra, ancak `Open` üye işlevini çağırmadan önce bir kayıt kümesinin sıralama düzeni oluşturmanız gerekir (ya da daha önce `Open` üye işlevi çağrılan mevcut bir kayıt kümesi nesnesi için `Requery` üye işlevini çağırmadan önce).

#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Bir kayıt kümesi nesnesi için sıralama düzeni belirtmek için

1. Yeni bir kayıt kümesi nesnesi oluşturun (veya var olan bir kayıt için `Requery` çağırmayı hazırlayın).

1. Nesnenin [m_strSort](../../mfc/reference/crecordset-class.md#m_strsort) veri üyesinin değerini ayarlayın.

   Sıralama, null ile sonlandırılmış bir dizedir. **Order by** yan tümcesinin içeriğini içerir, ancak tarafından anahtar sözcük **sıralaması**değildir. Örneğin, aşağıdakileri kullanın:

    ```
    recordset.m_strSort = "LastName DESC, FirstName DESC";
    ```

   not

    ```
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";
    ```

1. Filtre, kilitleme modu veya parametreler gibi, ihtiyacınız olan diğer seçenekleri ayarlayın.

1. Yeni nesne için `Open` çağırın (veya varolan bir nesne için `Requery`).

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
>  Kendi SQL dizenizi `Open`geçirerek, kayıt kümesinin varsayılan SQL dizesini geçersiz kılmayı tercih ediyorsanız, özel dizinizde **order by** yan tümcesi varsa sıralama ayarlamayın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Bir Kayıt Kümesini Parametreleştirme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)
