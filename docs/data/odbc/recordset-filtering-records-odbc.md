---
description: 'Şu konuda daha fazla bilgi edinin: kayıt kümesi: kayıtları filtreleme (ODBC)'
title: 'Kayıt Kümesi: Kayıtları Filtreleme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
ms.openlocfilehash: 15cf191f7a5a037c032726bc4f16a5774fb2857b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322344"
---
# <a name="recordset-filtering-records-odbc"></a>Kayıt Kümesi: Kayıtları Filtreleme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu başlığı altında, kullanılabilir kayıtların yalnızca belirli bir alt kümesini seçecek şekilde bir kayıt kümesinin nasıl filtreleneceği açıklanmaktadır. Örneğin, MATH101 gibi belirli bir kurs için yalnızca sınıf bölümleri seçmek isteyebilirsiniz. Filtre, bir SQL **WHERE** yan tümcesinin içeriğiyle tanımlanan bir arama durumudur. Framework onu kayıt kümesinin SQL ifadesine eklerse **WHERE** yan tümcesi seçimi kısıtlar.

Nesnesini oluşturduktan sonra, ancak üye işlevini çağırmadan önce bir kayıt kümesi nesnesinin filtresini oluşturmanız gerekir `Open` (veya üye işlevi `Requery` daha önce çağrılan mevcut bir kayıt kümesi nesnesi için üye işlevini çağırmadan önce `Open` ).

#### <a name="to-specify-a-filter-for-a-recordset-object"></a>Bir kayıt kümesi nesnesi için filtre belirtmek için

1. Yeni bir kayıt kümesi nesnesi oluşturun (veya `Requery` varolan bir nesne için çağrıya hazırlanın).

1. Nesnenin [m_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) veri üyesinin değerini ayarlayın.

   Filtre, SQL **WHERE** yan tümcesinin içeriğini içeren, ancak **WHERE** anahtar sözcüğünü içermeyen null ile sonlandırılmış bir dizedir. Örneğin, aşağıdakileri kullanın:

    ```
    m_pSet->m_strFilter = "CourseID = 'MATH101'";
    ```

   not

    ```
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";
    ```

    > [!NOTE]
    >  "MATH101" değişmez dize, yukarıdaki tek tırnak işaretleriyle birlikte gösterilir. ODBC SQL belirtiminde, tek tırnak işareti bir karakter dizesi sabit değerini göstermek için kullanılır. Bu durumda DBMS 'nizin tırnak içine alma gereksinimleri için ODBC sürücüsü belgelerinize bakın. Bu söz dizimi Ayrıca bu konunun sonunda daha da ele alınmıştır.

1. Sıralama düzeni, kilitleme modu veya parametreler gibi, ihtiyacınız olan diğer seçenekleri ayarlayın. Bir parametre belirtilmesi özellikle yararlıdır. Filtrenizi parametreleştiriyor hakkında daha fazla bilgi için bkz. [Recordset: bir kayıt kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

1. `Open`Yeni nesne için çağrı yapın (veya `Requery` daha önce açılmış bir nesne için).

> [!TIP]
> Filtreinizdeki parametrelerin kullanılması, kayıtları almak için büyük olasılıkla en verimli yöntemdir.

> [!TIP]
> Kayıt kümesi filtreleri, tabloları [birleştirmek](../../data/odbc/recordset-performing-a-join-odbc.md) ve çalışma zamanında alınan veya hesaplanan bilgilere göre [parametreleri](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) kullanmak için faydalıdır.

Kayıt kümesi yalnızca belirttiğiniz arama koşulunu karşılayan kayıtları seçer. Örneğin, yukarıda açıklanan kurs filtresini belirtmek için (örneğin `strCourseID` , şu anda ayarlanmış bir değişken varsayıldığında, örneğin, "MATH101" olarak) şunları yapın:

```
// Using the recordset pointed to by m_pSet

// Set the filter
m_pSet->m_strFilter = "CourseID = " + strCourseID;

// Run the query with the filter in place
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )

// Use the recordset
```

Kayıt kümesi, MATH101 için tüm sınıf bölümlerine ait kayıtları içerir.

Yukarıdaki örnekte, bir dize değişkeni kullanılarak Filtre dizesinin nasıl ayarlandığı hakkında dikkat edin. Bu, tipik kullanımdır. Ancak kurs KIMLIĞI için 100 sabit değerini belirtmek istediğinizi varsayalım. Aşağıdaki kod, bir değişmez değerle Filtre dizesinin doğru şekilde nasıl ayarlanacağını gösterir:

```
m_strFilter = "StudentID = '100'";   // correct
```

Tek tırnak karakterlerinin kullanımını aklınızda kullanın; Filtre dizesini doğrudan ayarlarsanız, filtre dizesi şu **değildir**:

```
m_strFilter = "StudentID = 100";   // incorrect for some drivers
```

Yukarıda gösterilen tırnak işareti ODBC belirtimine uyar, ancak bazı DBMS 'ler başka tırnak karakterleri gerektirebilir. Daha fazla bilgi için bkz. [SQL: kayıt KÜMENIZIN SQL Ifadesini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

> [!NOTE]
> Kendi SQL dizenizi ' a geçirerek kayıt kümesinin varsayılan SQL dizesini geçersiz kılmayı seçerseniz `Open` , özel dizeniz **WHERE** yan tümcesi varsa bir filtre ayarlanmamalıdır. Varsayılan SQL 'i geçersiz kılma hakkında daha fazla bilgi için bkz. [SQL: kayıt KÜMENIZIN SQL Ifadesini özelleştirme (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)<br/>
[Kayıt kümesi: kayıt kümelerinin kayıtları seçme biçimi (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)<br/>
[Kayıt kümesi: kayıt kümelerinin kayıtları Güncelleştirmesi (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)<br/>
[Kayıt kümesi: kayıtları kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
