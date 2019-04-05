---
title: 'Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)'
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
ms.openlocfilehash: 28c885119816c1df662cc0b941e02cb3cf747f3d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024614"
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

> [!NOTE]
>  Artık kayıtları toplu olarak daha verimli bir şekilde ekleyebilirsiniz. Daha fazla bilgi için [kayıt kümesi: Kayıtları toplu yakalama (ODBC) içinde ekleme](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).

> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Eklemeyi, güncelleştirilebilir anlık görüntüler ve dinamik kümeler (güncelleştirme) Düzenle ve kayıtlarını silin. Bu konu şunları açıklar:

- [Kümenizin güncelleştirilebilir olup olmadığını belirlemek nasıl](#_core_determining_whether_your_recordset_is_updatable).

- [Yeni kayıt ekleme](#_core_adding_a_record_to_a_recordset).

- [Varolan bir kaydı düzenlemek nasıl](#_core_editing_a_record_in_a_recordset).

- [Bir kaydı silmek nasıl](#_core_deleting_a_record_from_a_recordset).

Güncelleştirmelerin nasıl yapıldığı hakkında daha fazla bilgi için çıkış ve güncelleştirmelerinizi diğer kullanıcılara gösterilme görmek [kayıt kümesi: Kümelerinin kayıtları Güncelleştirmesi (ODBC) kayıtları](../../data/odbc/recordset-how-recordsets-update-records-odbc.md). Normalde, eklemek, düzenlemek veya kayıt silme, veri kaynağı hemen kayıt kümesini değiştirir. Bunun yerine işlemleri toplu ilgili güncelleştirmeler grupları. Bir işlem devam ediyor, işlemin yürütene kadar güncelleştirme son olmaz. Bu, geri alabilir veya değişiklikleri geri alma sağlar. İşlemler hakkında daha fazla bilgi için bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

Aşağıdaki tabloda, farklı güncelleştirme özellikleri olan kayıt kümeleri için kullanılabilen seçenekler özetlenmektedir.

### <a name="recordset-readupdate-options"></a>Kayıt kümesi okuma/güncelleştirme seçenekleri

|Tür|Oku|Kaydı düzenleme|Kaydı Sil|Yeni Ekle (Ekle)|
|----------|----------|-----------------|-------------------|------------------------|
|salt okunur|Y|N|N|N|
|Yalnızca ekleme|Y|N|N|Y|
|Tam olarak güncelleştirilebilir|Y|Y|Y|Y|

##  <a name="_core_determining_whether_your_recordset_is_updatable"></a> Güncelleştirilebilir belirleme olmadığını kümenizin olduğu

Veri kaynağı güncelleştirilebilir ve güncelleştirilebilir olarak kayıt kümesi açıldı bir kayıt kümesi nesnesi güncelleştirilebilir. Kendi güncellenebilirliğini kullanacağınız SQL deyimi üzerinde ODBC sürücünüz yeteneklerini de bağlıdır ve ODBC imleç kitaplığı bellekte olup. Salt okunur bir kayıt veya veri kaynağı güncelleştirilemiyor.

#### <a name="to-determine-whether-your-recordset-is-updatable"></a>Kümenizin güncelleştirilebilir olup olmadığını belirlemek için

1. Kayıt kümesi nesnenin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevi.

   `CanUpdate` kayıt kümesi güncelleştirilebilir ise sıfır olmayan bir değer döndürür.

Kayıt kümeleri varsayılan olarak, tam olarak güncelleştirilebilir (gerçekleştirebileceğiniz `AddNew`, `Edit`, ve `Delete` işlemleri). Ancak ayrıca [appendOnly](../../mfc/reference/crecordset-class.md#open) güncelleştirilebilir kayıt kümeleri açmak için seçeneği. Bu şekilde açılan bir kayıt kümesi yalnızca yeni kayıtları eklenmesine olanak veren `AddNew`. Düzenleyemez veya mevcut kayıtları silin. Bir kayıt kümesi yalnızca çağırarak ekleme için açık olup olmadığını test edebilirsiniz [CanAppend](../../mfc/reference/crecordset-class.md#canappend) üye işlevi. `CanAppend` kayıt kümesi tamamen güncelleştirilebilir veya yalnızca ekleme için açık ise sıfır olmayan bir değer döndürür.

Aşağıdaki kod nasıl kullanabileceğinizi gösterir `CanUpdate` için bir kayıt kümesi nesnesi olarak adlandırılan `rsStudentSet`:

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
>  Bir kayıt kümesi çağırarak güncelleştirmek hazırlama zaman `Update`, kümenizin tabloyu (veya tüm benzersiz bir dizin tablosundaki sütunları) birincil anahtar ayarlama yapma tüm sütunları içeren ilgileniriz. Bazı durumlarda, framework kümenize Seçili sütunları güncelleştirmek için tablodaki hangi kaydı tanımlamak için kullanabilirsiniz. Tüm gerekli sütunları, büyük olasılıkla tutarlılığını tablonun zarar tablosunda birden çok kayıt güncelleştirilebilir. Bu durumda, framework istisnalar fırlatıyorsa çağırdığınızda `Update`.

##  <a name="_core_adding_a_record_to_a_recordset"></a> Bir kayıt kümesine kayıt ekleme

Yeni kayıtlar, kayıt kümesine ekleyebilirsiniz, [CanAppend](../../mfc/reference/crecordset-class.md#canappend) üye işlevi, sıfır olmayan bir değer döndürür.

#### <a name="to-add-a-new-record-to-a-recordset"></a>Bir kayıt kümesine yeni bir kayıt eklemek için

1. Kayıt kümesi eklenebilir olduğundan emin olun.

1. Kayıt kümesi nesnenin [AddNew](../../mfc/reference/crecordset-class.md#addnew) üye işlevi.

   `AddNew` bir düzen arabellek olarak görev yapacak kayıt hazırlar. Tüm alan veri üyeleri özel Null değere ayarlayın ve çağırdığınızda yalnızca (kirli) değiştirilmiş değerleri veri kaynağına yazılır şekilde değişmemiş olarak işaretlenmiş [güncelleştirme](../../mfc/reference/crecordset-class.md#update).

1. Yeni kayıttaki alan veri üyelerinin değerlerini ayarlayın.

   Değerler alan veri üyeleri atayın. Bu atama, veri kaynağına yazılmaz.

1. Kayıt kümesi nesnenin `Update` üye işlevi.

   `Update` Ayrıca, veri kaynağına yeni kayıt yazarak tamamlar. Hakkında bilgi çağırmak başarısız olur için `Update`, bkz: [kayıt kümesi: Kümelerinin kayıtları Güncelleştirmesi (ODBC) kayıtları](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

Kayıt eklemeler nasıl çalışır ve eklenen kayıtlar kümenizde görünür olduğunda hakkında bilgi için bkz [kayıt kümesi: Nasıl AddNew, düzenleme ve silme (ODBC) iş](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md).

Aşağıdaki örnek, yeni bir kayıt eklemek gösterilmektedir:

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
>  İptal etmek için bir `AddNew` veya `Edit` çağrı, yalnızca başka bir çağrı yapmak `AddNew` veya `Edit` veya çağrı `Move` ile *AFX_MOVE_REFRESH* parametresi. Veri üyeleri, önceki değerlerine sıfırlanır ve hala olduğunuz `Edit` veya `Add` modu.

##  <a name="_core_editing_a_record_in_a_recordset"></a> Bir kayıt kümesindeki bir kaydı düzenleme

Var olan kayıtların düzenleyebilirsiniz kümenizin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevi, sıfır olmayan bir değer döndürür.

#### <a name="to-edit-an-existing-record-in-a-recordset"></a>Bir kayıt kümesinde varolan bir kaydı düzenlemek için

1. Kayıt kümesi güncelleştirilebilir olduğundan emin olun.

1. Güncelleştirmek istediğiniz kayda ilerleyin.

1. Kayıt kümesi nesnenin [Düzenle](../../mfc/reference/crecordset-class.md#edit) üye işlevi.

   `Edit` bir düzen arabellek olarak görev yapacak kayıt hazırlar. Tüm alan veri üyeleri, böylece kayıt, daha sonra bunlar değiştirilen satırların olup olmadığını söyleyebilir işaretlenir. Değiştirilen alan veri üyeleri için yeni değerler çağırdığınızda veri kaynağına yazılır [güncelleştirme](../../mfc/reference/crecordset-class.md#update).

1. Yeni kayıttaki alan veri üyelerinin değerlerini ayarlayın.

   Değerler alan veri üyeleri atayın. Bu değerleri atamayın değişmeden kalır.

1. Kayıt kümesi nesnenin `Update` üye işlevi.

   `Update` Düzen, veri kaynağına değiştirilmiş kayıt yazarak tamamlar. Hakkında bilgi çağırmak başarısız olur için `Update`, bkz: [kayıt kümesi: Kümelerinin kayıtları Güncelleştirmesi (ODBC) kayıtları](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

Bir kayıt düzenledikten sonra geçerli kayıt düzenlenmiş kayıt kalır.

Aşağıdaki örnekte gösterildiği bir `Edit` işlemi. Bu, kullanıcının bir kayda düzenlemek isteyebilir taşındığını varsayar.

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
> İptal etmek için bir `AddNew` veya `Edit` çağrı, yalnızca başka bir çağrı yapmak `AddNew` veya `Edit` veya çağrı `Move` ile *AFX_MOVE_REFRESH* parametresi. Veri üyeleri, önceki değerlerine sıfırlanır ve hala olduğunuz `Edit` veya `Add` modu.

##  <a name="_core_deleting_a_record_from_a_recordset"></a> Bir kayıt kümesinden bir kaydı siliniyor

Kayıtlar geri silebilirsiniz kümenizin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevi, sıfır olmayan bir değer döndürür.

#### <a name="to-delete-a-record"></a>Bir kaydı silmek için

1. Kayıt kümesi güncelleştirilebilir olduğundan emin olun.

1. Güncelleştirmek istediğiniz kayda ilerleyin.

1. Kayıt kümesi nesnenin [Sil](../../mfc/reference/crecordset-class.md#delete) üye işlevi.

   `Delete` hemen kaydı, kayıt ve veri kaynağı silinmiş olarak işaretler.

   Farklı `AddNew` ve `Edit`, `Delete` karşılık gelen bir yok `Update` çağırın.

1. Başka bir kayda ilerleyin.

   > [!NOTE]
   >  Kayıt kümesi içinde taşırken, silinen kayıtlar atlandı değildir. Daha fazla bilgi için [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) üye işlevi.

Aşağıdaki örnekte gösterildiği bir `Delete` işlemi. Bu kullanıcıyı silmek için kullanıcının istediği bir kayda taşındı varsayar. Sonra `Delete` olduğundan adlı yeni bir kayda önemlidir.

```
rsStudent.Delete( );
rsStudent.MoveNext( );
```

Etkileri hakkında daha fazla bilgi için `AddNew`, `Edit`, ve `Delete` üye işlevleri [kayıt kümesi: Kümelerinin kayıtları Güncelleştirmesi (ODBC) kayıtları](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)