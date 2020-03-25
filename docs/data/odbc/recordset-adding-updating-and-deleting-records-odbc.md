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
ms.openlocfilehash: 14fc26709541135e80a2e0fe4de872cc75221874
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213011"
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

> [!NOTE]
>  Artık kayıtları toplu olarak daha verimli bir şekilde ekleyebilirsiniz. Daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu ekleme (ODBC)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).

> [!NOTE]
>  Bu konu, toplu satır yakalamanın uygulanmadığı `CRecordset` türetilen nesneler için geçerlidir. Toplu satır getirme kullanıyorsanız, bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Güncelleştirilebilir anlık görüntüler ve dinamik kümeler kayıtları eklemenize, düzenlemenize (güncelleştirmenize) ve silmesine izin verir. Bu konuda aşağıdakiler açıklanmaktadır:

- [Kayıt kümenizin güncelleştirilebilir olup olmadığını belirleme](#_core_determining_whether_your_recordset_is_updatable).

- [Yeni bir kayıt nasıl eklenir](#_core_adding_a_record_to_a_recordset).

- [Mevcut bir kaydı düzenleme](#_core_editing_a_record_in_a_recordset).

- [Bir kaydı silme](#_core_deleting_a_record_from_a_recordset).

Güncelleştirmelerin nasıl gerçekleştirildiği ve güncelleştirmelerin diğer kullanıcılara nasıl göründüğü hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md). Normal olarak, bir kaydı eklediğinizde, düzenlediğinizde veya sildiğinizde, kayıt kümesi veri kaynağını hemen değiştirir. Bunun yerine, ilgili güncelleştirmelerin toplu işlem gruplarını işlemlere aktarabilirsiniz. Devam eden bir işlem varsa, işlem tamamlanana kadar güncelleştirme son olmaz. Bu sayede değişiklikleri geri alabilir veya geri alabilirsiniz. İşlemler hakkında bilgi için bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

Aşağıdaki tabloda, farklı güncelleştirme özelliklerine sahip kayıt kümeleri için kullanılabilen seçenekler özetlenmektedir.

### <a name="recordset-readupdate-options"></a>Kayıt kümesi okuma/güncelleştirme seçenekleri

|Tür|Okuma|Kaydı Düzenle|Kaydı Sil|Yeni Ekle (Ekle)|
|----------|----------|-----------------|-------------------|------------------------|
|salt okunurdur|E|N|N|N|
|Yalnızca Append|E|N|N|E|
|Tamamen güncelleştirilebilir|E|E|E|E|

##  <a name="determining-whether-your-recordset-is-updateable"></a><a name="_core_determining_whether_your_recordset_is_updatable"></a>Kayıt kümenizin güncelleştirilebilir olup olmadığını belirleme

Veri kaynağı güncelleştirilebilirse ve kayıt kümesini güncelleştirilebilir olarak açtıysanız bir kayıt kümesi nesnesi güncelleştirilebilir. Güncelleştirme özelliği, kullandığınız SQL ifadesine, ODBC sürücünüzün özelliklerine ve ODBC Imleç kitaplığının bellekte olup olmamasına bağlıdır. Salt tanımlı bir kayıt kümesini veya veri kaynağını güncelleştiremezsiniz.

#### <a name="to-determine-whether-your-recordset-is-updatable"></a>Kayıt kümenizin güncelleştirilebilir olup olmadığını belirleme

1. Kayıt kümesi nesnesinin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevini çağırın.

   kayıt kümesi güncelleştirilebilirse `CanUpdate` sıfır dışında bir değer döndürür.

Varsayılan olarak, kayıt kümeleri tamamen güncelleştirilebilir (`AddNew`, `Edit`ve `Delete` işlemleri gerçekleştirebilirsiniz). Ancak, güncelleştirilebilir kayıt kümelerini açmak için [AppendOnly](../../mfc/reference/crecordset-class.md#open) seçeneğini de kullanabilirsiniz. Bu şekilde açılan bir kayıt kümesi, `AddNew`ile yalnızca yeni kayıtların eklenmesine izin verir. Mevcut kayıtları düzenleyemez veya silemezsiniz. [CanAppend](../../mfc/reference/crecordset-class.md#canappend) üye işlevini çağırarak bir kayıt kümesinin yalnızca ekleme için açık olup olmadığını test edebilirsiniz. `CanAppend`, kayıt kümesi tamamen güncelleştirilebilir veya yalnızca ekleme için açıksa sıfır dışında bir değer döndürür.

Aşağıdaki kod, `rsStudentSet`adlı bir kayıt kümesi nesnesi için `CanUpdate` nasıl kullanabileceğinizi gösterir:

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
>  `Update`çağırarak bir kayıt kümesini güncelleştirmeye hazırlarken, kayıt kümenizin tablonun birincil anahtarını (veya tablodaki tüm benzersiz dizin sütunlarının tüm sütunlarını) oluşturan tüm sütunları içerdiğinden emin olmalısınız. Bazı durumlarda Framework, tablonuzdaki hangi kaydın güncelleşdii belirlemek için yalnızca kayıt kümenizde seçilen sütunları kullanabilir. Tüm gerekli sütunlar olmadan, tabloda birden çok kayıt güncelleştirilemeyebilir, bu da tablonun bilgi tutarlılığını zararlı olabilir. Bu durumda, `Update`çağırdığınızda çerçeve özel durumlar oluşturur.

##  <a name="adding-a-record-to-a-recordset"></a><a name="_core_adding_a_record_to_a_recordset"></a>Kayıt kümesine kayıt ekleme

[CanAppend](../../mfc/reference/crecordset-class.md#canappend) üye işlevi sıfır dışında bir değer döndürürse bir kayıt kümesine yeni kayıtlar ekleyebilirsiniz.

#### <a name="to-add-a-new-record-to-a-recordset"></a>Bir kayıt kümesine yeni bir kayıt eklemek için

1. Kayıt kümesinin appdable olduğundan emin olun.

1. Kayıt kümesi nesnesinin [AddNew](../../mfc/reference/crecordset-class.md#addnew) üye işlevini çağırın.

   `AddNew`, kayıt kümesini düzenleme arabelleği olarak davranacak şekilde hazırlar. Tüm alan veri üyeleri, null değer olarak ayarlanır ve değiştirilmemiş olarak işaretlenir, ancak [Güncelleştir](../../mfc/reference/crecordset-class.md#update)' i çağırdığınızda yalnızca değiştirilen (kirli) değerler veri kaynağına yazılır.

1. Yeni kaydın alan veri üyelerinin değerlerini ayarlayın.

   Alan veri üyelerine değerler atayın. Atamalanlar veri kaynağına yazılmaz.

1. Kayıt kümesi nesnesinin `Update` üye işlevini çağırın.

   `Update`, yeni kaydı veri kaynağına yazarak ekleme işlemini tamamlar. `Update`çağıramadığında meydana gelir hakkında bilgi için bkz. [Recordset: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

Kayıtların nasıl çalıştığı ve kayıt kümenizde eklenen kayıtlar görünür olduğu hakkında bilgi için bkz. [kayıt kümesi: AddNew, Edit ve DELETE Work (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md).

Aşağıdaki örnek, nasıl yeni bir kayıt ekleneceğini göstermektedir:

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
>  Bir `AddNew` veya `Edit` çağrısını iptal etmek için `AddNew` veya `Edit` başka bir çağrı yapmanız veya *`Move` parametresiyle AFX_MOVE_REFRESH* çağırmanız yeterlidir. Veri üyeleri önceki değerlerine sıfırlanır ve hala `Edit` veya `Add` moddadır.

##  <a name="editing-a-record-in-a-recordset"></a><a name="_core_editing_a_record_in_a_recordset"></a>Kayıt kümesindeki bir kaydı Düzenle

Kayıt kümenizin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işleviniz sıfır dışında bir değer döndürürse var olan kayıtları düzenleyebilirsiniz.

#### <a name="to-edit-an-existing-record-in-a-recordset"></a>Bir kayıt kümesindeki mevcut bir kaydı düzenlemek için

1. Kayıt kümesinin güncelleştirilebilir olduğundan emin olun.

1. Güncelleştirmek istediğiniz kayda gidin.

1. Kayıt kümesi nesnesinin üye [düzenleme](../../mfc/reference/crecordset-class.md#edit) işlevini çağırın.

   `Edit`, kayıt kümesini düzenleme arabelleği olarak davranacak şekilde hazırlar. Tüm alan veri üyeleri, kayıt kümesinin daha sonra değiştirilip değiştirilmediğini bildirebilmesi için işaretlenir. [Güncelleştirme](../../mfc/reference/crecordset-class.md#update)çağırdığınızda değiştirilen alan veri üyelerinin yeni değerleri veri kaynağına yazılır.

1. Yeni kaydın alan veri üyelerinin değerlerini ayarlayın.

   Alan veri üyelerine değerler atayın. Değer atamazsınız değişmeden kalır.

1. Kayıt kümesi nesnesinin `Update` üye işlevini çağırın.

   `Update`, değiştirilen kaydı veri kaynağına yazarak düzenlemeyi tamamlar. `Update`çağıramadığında meydana gelir hakkında bilgi için bkz. [Recordset: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

Bir kaydı düzenledikten sonra, düzenlenen kayıt geçerli kayıt kalır.

Aşağıdaki örnek bir `Edit` işlemini gösterir. Kullanıcının düzenlemek istediği bir kayda taşındığını varsayar.

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
> Bir `AddNew` veya `Edit` çağrısını iptal etmek için `AddNew` veya `Edit` başka bir çağrı yapmanız veya *`Move` parametresiyle AFX_MOVE_REFRESH* çağırmanız yeterlidir. Veri üyeleri önceki değerlerine sıfırlanır ve hala `Edit` veya `Add` moddadır.

##  <a name="deleting-a-record-from-a-recordset"></a><a name="_core_deleting_a_record_from_a_recordset"></a>Kayıt kümesinden kayıt silme

Kayıt kümenizin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işleviniz sıfır dışında bir değer döndürürse kayıtları silebilirsiniz.

#### <a name="to-delete-a-record"></a>Bir kaydı silmek için

1. Kayıt kümesinin güncelleştirilebilir olduğundan emin olun.

1. Güncelleştirmek istediğiniz kayda gidin.

1. Kayıt kümesi nesnesinin üye [silme](../../mfc/reference/crecordset-class.md#delete) işlevini çağırın.

   `Delete` kaydı, hem kayıt kümesinde hem de veri kaynağında silinmiş olarak hemen işaretler.

   `AddNew` ve `Edit`aksine `Delete` karşılık gelen `Update` çağrısı yoktur.

1. Başka bir kayda kaydırın.

   > [!NOTE]
   >  Kayıt kümesini taşırken, silinen kayıtlar atlanmayabilir. Daha fazla bilgi için [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) üye işlevine bakın.

Aşağıdaki örnek bir `Delete` işlemini gösterir. Kullanıcının silmek istediği bir kayda taşındığını varsayar. `Delete` çağrıldıktan sonra yeni bir kayda geçiş yapmak önemlidir.

```
rsStudent.Delete( );
rsStudent.MoveNext( );
```

`AddNew`, `Edit`ve `Delete` üye işlevlerinin etkileri hakkında daha fazla bilgi için bkz. [Recordset: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
