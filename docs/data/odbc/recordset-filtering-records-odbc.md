---
title: 'Kayıt kümesi: Kayıtları filtreleme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
ms.openlocfilehash: 050524df840be28d661da89d04b685a44238f88c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397867"
---
# <a name="recordset-filtering-records-odbc"></a>Kayıt kümesi: Kayıtları filtreleme (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konuda, bir kayıt kümesi filtre, böylece yalnızca bir alt kümesi kullanılabilir kayıtların seçer açıklanmaktadır. Örneğin, yalnızca sınıf MATH101 gibi belirli bir kurs bölümlerini seçin isteyebilirsiniz. Bir SQL içeriğine göre tanımlanan bir arama koşulu bir filtredir **burada** yan tümcesi. İsteğe bağlı olarak framework kayıt kümenizin SQL deyimini ekler, **burada** yan tümcesi seçimi kısıtlar.

Kayıt kümesi nesnesinin filtre nesneyi oluşturduktan sonra ancak çağırmadan önce oluşturmanız gerekir, `Open` üye işlevi (veya çağırmadan önce `Requery` üye işlevi için var olan bir kayıt kümesi nesnesi `Open` üye işleve sahip daha önce çağrılmış).

#### <a name="to-specify-a-filter-for-a-recordset-object"></a>Kayıt kümesi nesnesi için bir filtre belirtmek için

1. Yeni bir kayıt kümesi nesnesi oluşturun (veya çağrı hazırlanma `Requery` var olan bir nesne için).

1. Nesnenin değerini [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesi.

   SQL içeriğini içeren null ile sonlandırılmış bir dize filtredir **burada** yan tümcesi ancak anahtar sözcüğünü içermeyen **nerede**. Örneğin, şunu kullanın:

    ```
    m_pSet->m_strFilter = "CourseID = 'MATH101'";
    ```

   not

    ```
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";
    ```

    > [!NOTE]
    >  "MATH101" sabit dizesini tek tırnak işaretleri ile yukarıdaki gösterilir. ODBC SQL belirtiminde tek tırnak, değişmez bir karakter dizesini belirtmek için kullanılır. Bu durumda teklif gereksinimleri için ODBC sürücü belgelerinize bakın. Bu söz dizimi de ele daha, bu konunun sonuna yakın.

1. Sıralama düzeni, kilitleme modu veya parametreleri gibi gereken diğer seçeneklerini ayarlayın. Parametre belirtmekle özellikle yararlıdır. Filtreniz kümesini parametreleştirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: (ODBC) bir kayıt kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

1. Çağrı `Open` yeni nesne için (veya `Requery` önceden açılmış bir nesne için).

> [!TIP]
>  Filtrenizde parametreleri kullanarak olası kayıtları almak için en verimli yöntemdir.

> [!TIP]
>  Kayıt kümesi filtreleri için yararlı [katılma](../../data/odbc/recordset-performing-a-join-odbc.md) tablolar ve kullanmaya yönelik [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) çalışma zamanında hesaplanan veya alınan bilgilere dayanarak.

Kayıt kümesinin belirtilen arama koşulu karşılayan kayıtları seçer. Örneğin, kurs filtre belirtmek için açıklanan yukarıda (bir değişken varsayılarak `strCourseID` , örneğin, "MATH101" ayarlanmış), aşağıdakileri yapın:

```
// Using the recordset pointed to by m_pSet

// Set the filter
m_pSet->m_strFilter = "CourseID = " + strCourseID;

// Run the query with the filter in place
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )

// Use the recordset
```

Kayıt kümesi için MATH101 tüm sınıf bölümleri kayıtlarını içerir.

Filtre dizesi bir dize değişkeni kullanarak yukarıdaki örnekte nasıl ayarlandığına dikkat edin. Bu tipik bir kullanımdır. Ancak kurs kimliği için değişmez değer olarak 100 belirtmek istediğinizi düşünün. Aşağıdaki kod doğru değişmez değer ile filtre dizesi ayarlama işlemini gösterir:

```
m_strFilter = "StudentID = '100'";   // correct
```

Tek tırnak işareti karakter kullanımına dikkat edin. filtre dizesi doğrudan ayarlarsanız, filtre dizedir **değil**:

```
m_strFilter = "StudentID = 100";   // incorrect for some drivers
```

ODBC belirtimine uygun yukarıda gösterilen Alıntısı, ancak bazı DBMS diğer tırnak karakterleri gerektirebilir. Daha fazla bilgi için [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

> [!NOTE]
>  Kendi SQL dizesi geçirerek kümesinin varsayılan SQL dizesi geçersiz kılmak isterseniz `Open`, özel dizenizi varsa bir filtre ayarlanmamalıdır bir **burada** yan tümcesi. Varsayılan SQL geçersiz kılma hakkında daha fazla bilgi için bkz. [SQL: Kayıt Kümenizin SQL deyimini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Sıralama (OBDC)](../../data/odbc/recordset-sorting-records-odbc.md)<br/>
[Kayıt kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Kayıt kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Kilitleme (OBDC)](../../data/odbc/recordset-locking-records-odbc.md)