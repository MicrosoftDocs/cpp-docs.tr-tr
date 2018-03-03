---
title: "Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cad50d25f6b9e2cc619fb19e21c2b6575ababa47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-adding-updating-and-deleting-records-odbc"></a>Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
> [!NOTE]
>  Artık kayıtları toplu olarak daha verimli bir şekilde ekleyebilirsiniz. Daha fazla bilgi için bkz: [kayıt kümesi: kayıtları ekleme (ODBC) toplu](../../data/odbc/recordset-adding-records-in-bulk-odbc.md).  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Eklemek, izin güncelleştirilebilir anlık görüntüler ve dinamik kümeler (güncelleştirme) düzenleyebilir ve kayıtları silebilirsiniz. Bu konuda açıklanmaktadır:  
  
-   [Kümenizin güncelleştirilebilir olup olmadığını belirlemek nasıl](#_core_determining_whether_your_recordset_is_updatable).  
  
-   [Yeni bir kayıt ekleme](#_core_adding_a_record_to_a_recordset).  
  
-   [Var olan bir kaydını düzenlemek nasıl](#_core_editing_a_record_in_a_recordset).  
  
-   [Bir kaydı silmek nasıl](#_core_deleting_a_record_from_a_recordset).  
  
 Güncelleştirmelerin nasıl yapıldığı hakkında daha fazla bilgi için out ve diğer kullanıcılara, güncelleştirmelerinin görünmesini bkz [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md). Normalde, eklemek, düzenlemek veya kayıt silme, veri kaynağı kayıt hemen değiştirir. Bunun yerine ilgili güncelleştirmelere yönelik grupları işlemlere toplu. Bir işlem devam ediyor, işlemin kaydedene kadar güncelleştirme son olmaz. Bu, geri almanıza veya değişiklikleri geri alma olanak sağlar. İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
 Aşağıdaki tabloda, farklı güncelleştirme özellikleri olan kayıt kümeleri için kullanılabilir seçenekleri özetler.  
  
### <a name="recordset-readupdate-options"></a>Kayıt kümesi okuma/güncelleştirme seçenekleri  
  
|Tür|Oku|Kayıt düzenleme|Kaydını sil|Yeni Ekle (Ekle)|  
|----------|----------|-----------------|-------------------|------------------------|  
|Salt okunur|Y|N|N|N|  
|Yalnızca ekleme|Y|N|N|Y|  
|Tam olarak güncelleştirilebilir|Y|Y|Y|Y|  
  
##  <a name="_core_determining_whether_your_recordset_is_updatable"></a>Belirleme olup olmadığını kümenizin güncelleştirilebilir değil  
 Kayıt kümesi nesnesi veri kaynağını güncelleştirilebilir ise ve kayıt kümesini güncelleştirilebilir olarak açtığınız güncelleştirilebilir. Kendi güncellenebilirliğini kullanın, SQL deyimini üzerinde ODBC sürücünüz yeteneklerini de bağlıdır ve ODBC imleç kitaplığı bellekte olup olmadığı. Salt okunur bir kayıt kümesi veya veri kaynağı güncelleştirilemiyor.  
  
#### <a name="to-determine-whether-your-recordset-is-updatable"></a>Kümenizin güncelleştirilebilir olup olmadığını belirlemek için  
  
1.  Kayıt kümesi nesnesinin çağrısı [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevi.  
  
     `CanUpdate`kayıt kümesi güncelleştirilebilir ise sıfır olmayan bir değer döndürür.  
  
 Varsayılan olarak, kayıt kümeleri tamamen güncelleştirilebilir (gerçekleştirebileceğiniz `AddNew`, **Düzenle**, ve **silmek** işlemleri). Ancak aynı zamanda [appendOnly](../../mfc/reference/crecordset-class.md#open) güncelleştirilebilir kayıt kümelerini açmak için seçeneği. Bu şekilde açılan bir kayıt kümesi yalnızca yenileriyle eklenmesine olanak veren `AddNew`. Düzenleyemez veya mevcut kayıtları silin. Bir kayıt kümesi yalnızca çağırarak ekleme için açık olup olmadığını sınayabilirsiniz [CanAppend](../../mfc/reference/crecordset-class.md#canappend) üye işlevi. `CanAppend`kayıt kümesi tamamen güncelleştirilebilir veya yalnızca ekleme için açık ise sıfır olmayan bir değer döndürür.  
  
 Aşağıdaki kodu nasıl kullanacağınızı gösterir `CanUpdate` için bir kayıt kümesi nesnesi adlı `rsStudentSet`:  
  
```  
if( !rsStudentSet.Open( ) )  
    return FALSE;  
if( !rsStudentSet.CanUpdate( ) )  
{  
    AfxMessageBox( "Unable to update the Student recordset." );  
    return;  
}  
```  
  
> [!CAUTION]
>  Kayıt çağırarak güncelleştirmek hazırlama zaman **güncelleştirme**, kümenizin tablonun (veya tüm tablo üzerinde benzersiz bir dizin sütunları) birincil anahtarı yapmadan tüm sütunları içeren dikkatli olun. Bazı durumlarda, framework yalnızca kümenize seçili sütun güncelleştirmek için tablodaki hangi kaydı tanımlamak için kullanabilirsiniz. Tüm gerekli sütunları, büyük olasılıkla tablosunun başvuru bütünlüğü zarar tablosunda birden çok kayıt güncelleştirilebilir. Bu durumda, çağırdığınızda çerçeve özel durumlar atar **güncelleştirme**.  
  
##  <a name="_core_adding_a_record_to_a_recordset"></a>Bir kayıt kümesine kayıt ekleme  
 Yeni kayıtlar, kayıt kümesine ekleyebilirsiniz, [CanAppend](../../mfc/reference/crecordset-class.md#canappend) üye işlevi sıfır olmayan bir değer döndürür.  
  
#### <a name="to-add-a-new-record-to-a-recordset"></a>Bir kayıt kümesine yeni bir kayıt eklemek için  
  
1.  Kayıt kümesi eklenebilir olduğundan emin olun.  
  
2.  Kayıt kümesi nesnesinin çağrısı [AddNew](../../mfc/reference/crecordset-class.md#addnew) üye işlevi.  
  
     `AddNew`kayıt düzenleme arabellek olarak davranacak şekilde hazırlar. Tüm alan veri üyeleri özel Null değere ayarlanır ve çağırdığınızda yalnızca değiştirilen (kirli) değerleri veri kaynağına yazılır şekilde değiştirilmemiş olarak işaretlenmiş [güncelleştirme](../../mfc/reference/crecordset-class.md#update).  
  
3.  Yeni kayıttaki alan veri üyeleri değerlerini ayarlayın.  
  
     Alan veri üyelerine değerler atayın. Bu atadığınız değil, veri kaynağına yazılmaz.  
  
4.  Kayıt kümesi nesnesinin çağrısı **güncelleştirme** üye işlevi.  
  
     **Güncelleştirme** eklenmesi veri kaynağına yeni kayıttaki yazarak tamamlar. Çağrı başarısız olursa hakkında bilgi gerçekleşir **güncelleştirme**, bkz: [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
 Kayıt eklemeler nasıl çalışır ve eklenen kayıtları kümenizde görünür olduğunda hakkında bilgi için bkz: [kayıt kümesi: nasıl AddNew, düzenleme ve silme çalışma (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md).  
  
 Aşağıdaki örnek yeni bir kayıt ekleme gösterir:  
  
```  
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
>  İptal etmek için bir `AddNew` veya **Düzenle** çağrısı, yalnızca başka bir çağırmaya `AddNew` veya **Düzenle** veya arama **taşıma** ile **AFX_MOVE_REFRESH**  parametresi. Veri üyeleri önceki değerlerine sıfırlanır ve hala olduğunuz **Düzenle** veya **Ekle** modu.  
  
##  <a name="_core_editing_a_record_in_a_recordset"></a>Bir kayıt kümesindeki bir kaydı düzenleme  
 Varolan kayıtları düzenleyebilirsiniz kümenizin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevi sıfır olmayan bir değer döndürür.  
  
#### <a name="to-edit-an-existing-record-in-a-recordset"></a>Bir kayıt kümesinde varolan kaydını düzenlemek için  
  
1.  Kayıt kümesi güncelleştirilebilir olduğundan emin olun.  
  
2.  Güncelleştirmek istediğiniz kayda ilerleyin.  
  
3.  Kayıt kümesi nesnesinin çağrısı [Düzenle](../../mfc/reference/crecordset-class.md#edit) üye işlevi.  
  
     **Düzen** düzenleme arabellek olarak davranacak şekilde kayıt kümesini hazırlar. Kayıt kümesi daha sonra bunlar değiştirilmiş olup olmadığını yapıp yapmadığını tüm alan veri üyeleri işaretlenir. Çağırdığınızda değiştirilen alan veri üyeleri için yeni değerleri veri kaynağına yazılır [güncelleştirme](../../mfc/reference/crecordset-class.md#update).  
  
4.  Yeni kayıttaki alan veri üyeleri değerlerini ayarlayın.  
  
     Alan veri üyelerine değerler atayın. Bu değerleri atamayın değişmeden kalır.  
  
5.  Kayıt kümesi nesnesinin çağrısı **güncelleştirme** üye işlevi.  
  
     **Güncelleştirme** veri kaynağına değiştirilen kaydı yazarak düzenleme tamamlar. Çağrı başarısız olursa hakkında bilgi gerçekleşir **güncelleştirme**, bkz: [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
 Bir kayıt düzenledikten sonra düzenlenen kaydı geçerli kayıt kalır.  
  
 Aşağıdaki örnekte gösterildiği bir **Düzenle** işlemi. Bu kullanıcıyı düzenlemek istediği bir kayda taşındığını varsayar.  
  
```  
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
>  İptal etmek için bir `AddNew` veya **Düzenle** çağrısı, yalnızca başka bir çağırmaya `AddNew` veya **Düzenle** veya arama **taşıma** ile **AFX_MOVE_REFRESH**  parametresi. Veri üyeleri önceki değerlerine sıfırlanır ve hala olduğunuz **Düzenle** veya **Ekle** modu.  
  
##  <a name="_core_deleting_a_record_from_a_recordset"></a>Bir kayıt kümesinden bir kaydı siliniyor  
 Kayıt yoksa silebilirsiniz kümenizin [CanUpdate](../../mfc/reference/crecordset-class.md#canupdate) üye işlevi sıfır olmayan bir değer döndürür.  
  
#### <a name="to-delete-a-record"></a>A kaydı silinemiyor  
  
1.  Kayıt kümesi güncelleştirilebilir olduğundan emin olun.  
  
2.  Güncelleştirmek istediğiniz kayda ilerleyin.  
  
3.  Kayıt kümesi nesnesinin çağrısı [silmek](../../mfc/reference/crecordset-class.md#delete) üye işlevi.  
  
     **Silme** hemen kaydı, kayıt kümesindeki ve veri kaynağı silinmiş olarak işaretler.  
  
     Farklı `AddNew` ve **Düzenle**, **silmek** hiçbir karşılık gelen **güncelleştirme** çağırın.  
  
4.  Başka bir kayıtla kaydırın.  
  
    > [!NOTE]
    >  Kayıt kümesi içinde taşırken, silinen kayıtlar atlandı değildir. Daha fazla bilgi için bkz: [IsDeleted](../../mfc/reference/crecordset-class.md#isdeleted) üye işlevi.  
  
 Aşağıdaki örnekte gösterildiği bir **silmek** işlemi. Bu, kullanıcı silmek için kullanıcının istediği bir kayda taşındığını varsayar. Sonra **silmek** olduğu adlı yeni bir kayda taşımak önemlidir.  
  
```  
rsStudent.Delete( );  
rsStudent.MoveNext( );  
```  
  
 Etkilerini hakkında daha fazla bilgi için `AddNew`, **Düzenle**, ve **silmek** üye işlevleri bkz [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)