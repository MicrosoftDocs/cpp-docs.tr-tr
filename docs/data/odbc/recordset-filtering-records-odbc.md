---
title: 'Kayıt Kümesi: Kayıtları Filtreleme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
ms.openlocfilehash: 56b8c4f52ec294f58a760e1309d32aa81286ddec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367011"
---
# <a name="recordset-filtering-records-odbc"></a>Kayıt Kümesi: Kayıtları Filtreleme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, kullanılabilir kayıtların yalnızca belirli bir alt kümesini seçerek bir kayıt kümesinin nasıl filtre uygulandığını açıklar. Örneğin, MATH101 gibi belirli bir kursun yalnızca sınıf bölümlerini seçmek isteyebilirsiniz. Filtre, SQL **WHERE** yan tümcesinin içeriğiyle tanımlanan bir arama koşuludur. Çerçeve, kaydedici nin SQL deyimine eklendiğinde, **WHERE** yan tümcesi seçimi kısıtlar.

Nesneyi oluşturduktan sonra ancak `Open` üye işlevini çağırmadan önce (veya `Requery` `Open` üye işlevi daha önce çağrılan varolan bir kayıt kümesi nesnesi için üye işlevi çağırmadan önce) bir kayıt kümesi nesnesinin filtresini oluşturmanız gerekir.

#### <a name="to-specify-a-filter-for-a-recordset-object"></a>Kayıt kümesi nesnesi için filtre belirtmek için

1. Yeni bir kayıt kümesi nesnesi `Requery` oluşturma (veya varolan bir nesneyi aramaya hazırlanın).

1. Nesnenin [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesinin değerini ayarlayın.

   Filtre, SQL **WHERE** yan tümcesinin içeriğini içeren, ancak **WHERE**anahtar kelimesini içermeyen null-sonlandırılmış bir dizedir. Örneğin, aşağıdakileri kullanın:

    ```
    m_pSet->m_strFilter = "CourseID = 'MATH101'";
    ```

   not

    ```
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";
    ```

    > [!NOTE]
    >  "MATH101" dizeleri yukarıdaki tek tırnak işaretleri ile gösterilir. ODBC SQL belirtiminde, tek tırnak bir karakter dizesini harfiharfini belirtmek için kullanılır. Bu durumda DBMS'nizin teklif gereksinimleri için ODBC sürücü belgelerinizi kontrol edin. Bu sözdizimi de bu konunun sonuna yakın daha fazla ele alınmıştır.

1. Sıralama sırası, kilitleme modu veya parametreler gibi ihtiyacınız olan diğer seçenekleri ayarlayın. Bir parametre belirtme özellikle yararlıdır. Filtrenizi parametreleme hakkında bilgi için bkz: [Kayıt Kümesi: Bir Kayıt Kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

1. Yeni `Open` nesneyi (veya `Requery` daha önce açılmış bir nesne için) arayın.

> [!TIP]
> Filtrenizde parametreleri kullanmak, kayıtları almak için potansiyel olarak en etkili yöntemdir.

> [!TIP]
> Recordset filtreleri [tablolara katılmak](../../data/odbc/recordset-performing-a-join-odbc.md) ve çalışma zamanında elde edilen veya hesaplanan bilgilere dayalı [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) kullanmak için yararlıdır.

Kayıt kümesi yalnızca belirttiğiniz arama koşulunu karşılayan kayıtları seçer. Örneğin, yukarıda açıklanan ders filtresini belirtmek `strCourseID` için (örneğin, "MATH101" için şu anda ayarlanmış bir değişken varsayarak), aşağıdakileri yapın:

```
// Using the recordset pointed to by m_pSet

// Set the filter
m_pSet->m_strFilter = "CourseID = " + strCourseID;

// Run the query with the filter in place
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )

// Use the recordset
```

Kayıt kümesi MATH101 için tüm sınıf bölümleriiçin kayıtları içerir.

Filtre dizesinin bir dize değişkeni kullanarak yukarıdaki örnekte nasıl ayarlandığını öğrenin. Bu tipik bir kullanımdır. Ancak kurs kimliği için 100 değerini belirtmek istediğinizi varsayalım. Aşağıdaki kod, filtre dizesinin gerçek bir değerle nasıl doğru ayarlanır:

```
m_strFilter = "StudentID = '100'";   // correct
```

Tek tırnak karakterlerinin kullanımına dikkat edin; filtre dizesini doğrudan ayarlarsanız, filtre dizesi aşağıdaki gibi **değildir:**

```
m_strFilter = "StudentID = 100";   // incorrect for some drivers
```

Yukarıda gösterilen alıntı ODBC belirtimine uygundur, ancak bazı DBMS'ler başka alıntı karakterleri gerektirebilir. Daha fazla bilgi için [bkz: SQL: Recordset'inizin SQL Ekstresini (ODBC) özelleştirme.](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

> [!NOTE]
> Kendi SQL dizenizi geçerek kayıt kümesinin varsayılan SQL dizesini geçersiz kılmayı `Open`seçerseniz, özel dizenizde **WHERE** yan tümcesi varsa filtre ayarlamamalısınız. Varsayılan SQL'i geçersiz kılma hakkında daha fazla bilgi için [bkz: SQL: Recordset'inizin SQL Ekstresini (ODBC) özelleştirme.](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Seçme Biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Kayıt Kümesi: Kayıt Kümelerinin Kayıtları Güncelleştirmesi (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
