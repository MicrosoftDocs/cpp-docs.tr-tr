---
title: 'Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- records [C++], updating
- record editing [C++], in recordsets
- recordsets [C++], adding records
- records [C++], adding
- ODBC recordsets [C++], adding records
- recordsets [C++], editing records
- recordsets [C++], updating
- records [C++], deleting
- AddNew method
- ODBC recordsets [C++], deleting records
- data in recordsets [C++]
- record editing [C++]
- recordsets [C++], deleting records
- ODBC recordsets [C++], editing records
- records [C++], editing
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
ms.openlocfilehash: 628ffb2feee385a4114b0dbea074f81678c529d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367103"
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

> [!NOTE]
> Artık kayıtları toplu olarak daha verimli bir şekilde ekleyebilirsiniz. Daha fazla bilgi için [bkz: Kayıt Kümesi: Toplu Olarak Kayıt Ekleme (ODBC)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı türetilen nesneler için geçerlidir. Toplu satır alma kullanıyorsanız, [bkz.](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

Güncelleştirilebilir anlık görüntüler ve dinamitler, kayıtları eklemenize, düzenlemenize (güncelleştirmenize) ve silmenize olanak sağlar. Bu konu açıklar:

- [Kayıt setinizin güncellenip güncelolmadığını belirleme.](#_core_determining_whether_your_recordset_is_updatable)

- [Nasıl yeni bir kayıt eklemek için](#_core_adding_a_record_to_a_recordset).

- [Varolan bir kaydın nasıl dolduğunu.](#_core_editing_a_record_in_a_recordset)

- [Bir kayıt nasıl silinir.](#_core_deleting_a_record_from_a_recordset)

Güncelleştirmelerin nasıl gerçekleştirildiği ve güncelleştirmelerinizin diğer kullanıcılara nasıl göründüğü hakkında daha fazla bilgi için [Kayıt Kümesi: Kayıtları Nasıl Güncelleştirdiğini (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)görün. Normalde, bir kayıt eklediğinizde, düzenlediğinizde veya sildiğinizde, kayıt kümesi veri kaynağını hemen değiştirir. Bunun yerine, ilgili güncelleştirmegruplarını hareketlere toplu olarak ekleyebilirsiniz. Bir hareket devam ediyorsa, siz hareketi gerçekleştirene kadar güncelleştirme son uçsuz burdamaz. Bu, değişiklikleri geri almanızı veya geri almanızı sağlar. İşlemler hakkında bilgi için [Bkz. Hareket (ODBC)](../../data/odbc/transaction-odbc.md).

Aşağıdaki tablo, farklı güncelleştirme özelliklerine sahip kayıt kümeleri için kullanılabilir seçenekleri özetleyilmiştir.

### <a name="recordset-readupdate-options"></a>Recordset Okuma/Güncelleme Seçenekleri

|Tür|Okuma|Kayıt düzenleme|Kaydı silme|Yeni ekleme (ek)|
|----------|----------|-----------------|-------------------|------------------------|
|Salt okunur|E|N|N|N|
|Yalnızca ek|E|N|N|E|
|Tamamen güncel|E|E|E|E|

## <a name="determining-whether-your-recordset-is-updateable"></a><a name="_core_determining_whether_your_recordset_is_updatable"></a>Kayıt Setinizin Güncellenebilir Olup Olmadığını Belirleme

Veri kaynağı güncelleştirilebilirse ve kayıt kümesini güncelleştirilebilir olarak açtıysanız, kayıt kümesi nesnesi güncelleştirilebilir. Güncellenebilirliği ayrıca kullandığınız SQL deyimine, ODBC sürücünüzün yeteneklerine ve ODBC İmleç Kitaplığı'nın bellekte olup olmadığına bağlıdır. Salt okunur kayıt kümesini veya veri kaynağını güncelleştiremezsiniz.

#### <a name="to-determine-whether-your-recordset-is-updatable"></a>Kayıt setinizin güncellenip güncelolmadığını belirlemek için

1. Recordset nesnesinin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevini arayın.

   `CanUpdate`kayıt kümesi güncelleştirilebilirse sıfır olmayan bir değer döndürür.

Varsayılan olarak, kayıt kümeleri tamamen güncelleştirilebilir `Edit`(, ve `Delete` işlemleri gerçekleştirebilirsiniz). `AddNew` Ancak güncelleştirilebilir kayıt kümelerini açmak için [appendOnly](../../mfc/reference/crecordset-class.md#open) seçeneğini de kullanabilirsiniz. Bu şekilde açılan bir kayıt kümesi, yalnızca `AddNew`yeni kayıtların eklenmesine izin verir. Varolan kayıtları düzenleyemez veya silemezsiniz. Bir kayıt setinin yalnızca Ek olarak açık olup olmadığını [CanAppend](../../mfc/reference/crecordset-class.md#canappend) üye işlevini arayarak test edebilirsiniz. `CanAppend`kayıt kümesi tamamen güncellenebilir veya yalnızca ek olarak açıksa sıfır olmayan bir değer döndürür.

Aşağıdaki kod, aşağıdaki adlı `CanUpdate` `rsStudentSet`bir kayıt kümesi nesnesi için nasıl kullanabileceğinizi gösterir:

```cpp
if( !rsStudentSet.Open( ) )
    return FALSE;
if( !rsStudentSet.CanUpdate( ) )
{
    AfxMessageBox( "Unable to update the Student recordset." );
    return;
}
```

> [!CAUTION]
> Bir kayıt kümesini arayarak `Update`güncelleştirmeye hazırlanırken, kayıt setinizin tablonun birincil anahtarını oluşturan tüm sütunları (veya tablodaki benzersiz dizinin tüm sütunlarını) içerdiğine dikkat edin. Bazı durumlarda, çerçeve yalnızca kayıt setinizde seçilen sütunları kullanarak tablonuzdaki hangi kaydın güncelleştirilemesini belirleyebilir. Gerekli tüm sütunlar olmadan, tabloda birden çok kayıt güncelleştirilebilir ve bu da tablonun başvuru bütünlüğüne zarar verebilir. Bu durumda, çerçeve çağırdığınızda `Update`özel durumlar atar.

## <a name="adding-a-record-to-a-recordset"></a><a name="_core_adding_a_record_to_a_recordset"></a>Kayıt Kümesine Kayıt Ekleme

[CanAppend](../../mfc/reference/crecordset-class.md#canappend) üye işlevi sıfır olmayan bir değer döndürürse, kayıt kümesine yeni kayıtlar ekleyebilirsiniz.

#### <a name="to-add-a-new-record-to-a-recordset"></a>Kayıt kümesine yeni bir kayıt eklemek için

1. Kayıt kümesinin eklenebilir olduğundan emin olun.

1. Recordset nesnesinin [AddNew](../../mfc/reference/crecordset-class.md#addnew) üye işlevini arayın.

   `AddNew`bir edit arabelleği olarak hareket etmek için kayıt kümesini hazırlar. Tüm alan verileri üyeleri özel değer Null olarak ayarlanır ve değişmeden olarak işaretlenir, böylece [yalnızca](../../mfc/reference/crecordset-class.md#update)değiştirilen (kirli) değerler veri kaynağına güncelleştirmeyi aradığınızda yazılır.

1. Yeni kaydın alan veri üyelerinin değerlerini ayarlayın.

   Alan veri üyelerine değer atayın. Atamadığınız kişiler veri kaynağına yazılmaz.

1. Recordset nesnesinin `Update` üye işlevini arayın.

   `Update`yeni kaydı veri kaynağına yazarak eklemeyi tamamlar. Aramazsanız `Update`hakkında bilgi için, [bkz.](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

Kayıt eklemenin nasıl çalıştığı ve eklenen kayıtların kayıt setinizde ne zaman görünür olduğu hakkında bilgi için [bkz.](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)

Aşağıdaki örnekte, yeni bir kaydın nasıl ekleneniz gösterilmektedir:

```cpp
if( !rsStudent.Open( ) )
    return FALSE;
if( !rsStudent.CanAppend( ) )
    return FALSE;                      // no field values were set
rsStudent.AddNew( );
rsStudent.m_strName = strName;
rsStudent.m_strCity = strCity;
rsStudent.m_strStreet = strStreet;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not added; no field values were set." );
    return FALSE;
}
```

> [!TIP]
> Bir aramayı `AddNew` `Edit` veya aramayı iptal etmek `AddNew` `Edit` *için, AFX_MOVE_REFRESH* parametresini başka bir arama veya arama `Move` yapmanız yeterlidir. Veri üyeleri önceki değerlerine sıfırlanır ve `Edit` siz `Add` hala moddasınız.

## <a name="editing-a-record-in-a-recordset"></a><a name="_core_editing_a_record_in_a_recordset"></a>Kayıt Kümesinde Kayıt Düzenleme

Kayıt setinizin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevinin sıfır olmayan bir değer döndürürse varolan kayıtları güncelleyebilirsiniz.

#### <a name="to-edit-an-existing-record-in-a-recordset"></a>Varolan bir kaydı kayıt kümesinde ayarlamak için

1. Kayıt kümesinin güncelleştirilediğinden emin olun.

1. Güncelleştirmek istediğiniz kayda gidin.

1. Recordset nesnesinin [Edit](../../mfc/reference/crecordset-class.md#edit) üye işlevini arayın.

   `Edit`bir edit arabelleği olarak hareket etmek için kayıt kümesini hazırlar. Tüm alan veri üyeleri, kayıt kümesinin değiştirilip değiştirilmediğini daha sonra anlayabilmesi için işaretlenir. Değiştirilen alan veri üyeleri için yeni [değerler, Güncelleştirme'yi](../../mfc/reference/crecordset-class.md#update)aradığınızda veri kaynağına yazılır.

1. Yeni kaydın alan veri üyelerinin değerlerini ayarlayın.

   Alan veri üyelerine değer atayın. Değer atamadığınız değerler değişmeden kalır.

1. Recordset nesnesinin `Update` üye işlevini arayın.

   `Update`değiştirilen kaydı veri kaynağına yazarak düzenlemeyi tamamlar. Aramazsanız `Update`hakkında bilgi için, [bkz.](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

Bir kaydı düzenledikten sonra, düzenlenen kayıt geçerli kayıt olarak kalır.

Aşağıdaki örnekte `Edit` bir işlem gösterilmektedir. Kullanıcının, onu ve redelemek istediği bir kayda geçtiğini varsayar.

```cpp
rsStudent.Edit( );
rsStudent.m_strStreet = strNewStreet;
rsStudent.m_strCity = strNewCity;
rsStudent.m_strState = strNewState;
rsStudent.m_strPostalCode = strNewPostalCode;
if( !rsStudent.Update( ) )
{
    AfxMessageBox( "Record not updated; no field values were set." );
    return FALSE;
}
```

> [!TIP]
> Bir aramayı `AddNew` `Edit` veya aramayı iptal etmek `AddNew` `Edit` *için, AFX_MOVE_REFRESH* parametresini başka bir arama veya arama `Move` yapmanız yeterlidir. Veri üyeleri önceki değerlerine sıfırlanır ve `Edit` siz `Add` hala moddasınız.

## <a name="deleting-a-record-from-a-recordset"></a><a name="_core_deleting_a_record_from_a_recordset"></a>Kayıt Kümesinden Kaydı Silme

Kayıt setinizin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevinin sıfır olmayan bir değer döndürürse kayıtları silebilirsiniz.

#### <a name="to-delete-a-record"></a>Bir kaydı silmek için

1. Kayıt kümesinin güncelleştirilediğinden emin olun.

1. Güncelleştirmek istediğiniz kayda gidin.

1. Recordset nesnesinin [Delete](../../mfc/reference/crecordset-class.md#delete) üye işlevini arayın.

   `Delete`kaydı hem kayıt kümesinde hem de veri kaynağında silinmiş olarak hemen işaretler.

   Aksine `AddNew` `Edit`ve, `Delete` karşılık `Update` gelen bir çağrı vardır.

1. Başka bir kayda gidin.

   > [!NOTE]
   >  Kayıt kümesinde hareket ederken, silinen kayıtlar atlanamayabilir. Daha fazla bilgi [için, Silinmiş](../../mfc/reference/crecordset-class.md#isdeleted) üye işlevine bakın.

Aşağıdaki örnekte `Delete` bir işlem gösterilmektedir. Kullanıcının, kullanıcının silmek istediği bir kayda geçtiğini varsayar. Çağrıldıktan sonra, `Delete` yeni bir kayda geçmek önemlidir.

```
rsStudent.Delete( );
rsStudent.MoveNext( );
```

`AddNew`, ve `Edit` `Delete` üye işlevlerin etkileri hakkında daha fazla bilgi için bkz: [Recordset: How Recordsets Update Records (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
