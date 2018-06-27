---
title: 'TN043: RFX rutinleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RFX
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc6556cabaa8f1f04a2a53771b495233620e1a14
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954415"
---
# <a name="tn043-rfx-routines"></a>TN043: RFX Rutinleri
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not kayıt alanı değişimi (RFX) mimarisini açıklar. Ayrıca yazma biçimini açıklar bir **RFX_** yordamı.  
  
## <a name="overview-of-record-field-exchange"></a>Kayıt alanı değişimi genel bakış  
 Tüm kayıt kümesi alanı işlevleri C++ kodu ile yapılır. Özel kaynaklar veya Sihirli makroları yok. Kalp mekanizmasının her türetilmiş kayıt kümesi sınıfında geçersiz kılınmalıdır sanal bir işlevdir. Ayrıca, bu formda her zaman bulunur:  
  
```  
void CMySet::DoFieldExchange(CFieldExchange* pFX)  
{ *//{{AFX_FIELD_MAP(CMySet)  
 <recordset exchange field type call>  
 <recordset exchange function call> *//}}AFX_FIELD_MAP  
}  
```  
  
 Özel biçim AFX açıklamaları bulun ve bu işlev içindeki kod düzenlemek ClassWizard izin verin. ClassWizard ile uyumlu olmayan kod dışında özel biçim açıklamaları yerleştirilmelidir.  
  
 Yukarıdaki örnekte, < recordset_exchange_field_type_call > biçiminde olan:  
  
```  
pFX->SetFieldType(CFieldExchange::outputColumn);
```  
  
 ve < recordset_exchange_function_call > şu şekildedir:  
  
```  
RFX_Custom(pFX, "Col2",
    m_Col2);
```  
  
 Çoğu **RFX_** işlevleri sahip üç yukarıda gösterildiği gibi bağımsız değişkenler, ancak bazı (örneğin `RFX_Text` ve `RFX_Binary`) ek isteğe bağlı bağımsız değişkenlere sahiptir.  
  
 Birden fazla **RFX_** her eklenebilir `DoDataExchange` işlevi.  
  
 'Afxdb.h' MFC ile sağlanan tüm kayıt alanı değişimi rutinleri listesi için bkz.  
  
 Kayıt kümesi alan çağrıları alan verilerini depolamak için bellek konumlarını (genellikle veri üyeleri) kaydı bir yolu olan bir `CMySet` sınıfı.  
  
## <a name="notes"></a>Notlar  
 Kayıt kümesi alanı işlevleri yalnızca çalışmak için tasarlanmış `CRecordset` sınıfları. Bunlar genellikle diğer MFC sınıfları tarafından kullanılabilir değildir.  
  
 Verilerin ilk değerleri standart C++ oluşturucuda, genellikle bir blok ile ayarlanır `//{{AFX_FIELD_INIT(CMylSet)` ve `//}}AFX_FIELD_INIT` açıklamaları.  
  
 Her **RFX_** işlevi alan düzenlemek için hazırlama alanı arşivleme için alanın kirli durumu döndüren arasında değişen çeşitli işlemlerini desteklemesi gerekir.  
  
 Çağıran her işlev `DoFieldExchange` (örneğin `SetFieldNull`, `IsFieldDirty`), kendi başlatma çağrısı geçici mu `DoFieldExchange`.  
  
## <a name="how-does-it-work"></a>Nasıl çalışır  
 Kayıt alanı değişimi kullanmak için aşağıdakileri anlamanız gerekmez. Ancak, arka planda nasıl işlediğine yardımcı olacak anlama kendi exchange yordamı yazma.  
  
 `DoFieldExchange` Üye işlevi çok benzer olduğunu `Serialize` üye işlevi — almayı veya veri, / formundan bir dış (bir ODBC sorgusunun sonucu servis talebi bu sütunlarından) / sınıf üyesi verilerde ayarlamayı sorumludur. *PFX* parametre veri değiş tokuşu yapmak için bağlam ve benzer *CArchive* parametresi `CObject::Serialize`. *PFX* (bir `CFieldExchange` nesnesi) benzer bir işlem göstergesi, ancak bir genelleme sahip *CArchive* yön bayrağı. RFX işlevi aşağıdaki işlemleri desteklemek sahip olabilir:  
  
- `BindParam` Gösterir burada ODBC parametre veri almak  
  
- `BindFieldToColumn` — Burada ODBC alma/outputColumn veri banka gerekir belirtin  
  
- `Fixup` — Ayarlama `CString/CByteArray` uzunlukları, bit NULL durumunu ayarla  
  
- `MarkForAddNew` — İşareti kirli AddNew çağrısından değer değiştiyse  
  
- `MarkForUpdate` — İşareti kirli düzenleme çağrısından değer değiştiyse  
  
- `Name` — Kirli olarak işaretlenmiş alanlar için alan adlarını ekleme  
  
- `NameValue` — Append "\<sütun adı > =" kirli olarak işaretlenmiş alanlar için  
  
- `Value` — Append "" ayırıcı tarafından izlenen ister ',' veya ' '  
  
- `SetFieldDirty` — Durum bit kirli (yani değiştirilen) alanını ayarlayın  
  
- `SetFieldNull` — Alan için null değer gösteren durum biti ayarlanmış  
  
- `IsFieldDirty` — Kirli durumu bit dönüş değeri  
  
- `IsFieldNull` — Null durumu bit dönüş değeri  
  
- `IsFieldNullable` — Alanın NULL değerler içerebileceği olursa TRUE döndürür  
  
- `StoreField` — Arşiv alan değeri  
  
- `LoadField` — Yeniden arşivlenmiş alan değeri  
  
- `GetFieldInfoValue` — Bir alan genel bilgiler döndürür.  
  
- `GetFieldInfoOrdinal` — Bir alan genel bilgiler döndürür.  
  
## <a name="user-extensions"></a>Kullanıcı Uzantıları  
 Varsayılan RFX mekanizması genişletmek için birkaç yolu vardır. Şunları yapabilirsiniz  
  
-   Yeni veri türleri ekleyin. Örneğin:  
  
 ```  
    CBookmark 
 ```  
  
-   Yeni exchange yordamları (RFX_) ekleyin.  
  
 ```  
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
    const char *szName,  
    BIGINT& value);

 ```  
  
-   Sahip `DoFieldExchange` üye işlevi koşullu ek RFX çağrıları veya diğer herhangi bir geçerli C++ deyimleri gösterilebilir.  
  
 ```  
    while (posExtraFields != NULL)  
 {  
    RFX_Text(pFX,
    m_listName.GetNext(posExtraFields),   
    m_listValue.GetNext(posExtraValues));

 }  
 ```  
  
> [!NOTE]
>  Bu tür kod ClassWizard tarafından düzenlenemez ve yalnızca özel biçim yorumları dışında kullanılmalıdır.  
  
## <a name="writing-a-custom-rfx"></a>Özel bir RFX yazma  
 Kendi özel RFX işlevi yazmak için varolan bir RFX işlevi kopyalayıp kendi amaçlarınız için değiştirebilirsiniz önerilir. Kopyalamak için sağ RFX seçerek işinizi çok daha kolay hale getirebilir. Bazı RFX işlevleri kopyalama karar verirken dikkate almanız bazı benzersiz özelliklere sahiptir.  
  
 `RFX_Long` ve `RFX_Int`:  
 Bu basit bir RFX işlevlerdir. Veri değeri hiçbir özel yorumlama gerekli değildir ve veri boyutu sabit.  
  
 `RFX_Single` ve `RFX_Double`:  
 Bu işlevler RFX_Long ve rfx_ınt yukarıdaki gibi basit ve yapabilirsiniz varsayılan uygulaması bolca kullanırlar. Bunlar dbflt.cpp yerine dbrfx.cpp, ancak yalnızca açıkça başvuru olduklarında noktası kitaplığı kayan çalışma zamanı yükleme etkinleştirmek için depolanır.  
  
 `RFX_Text` ve `RFX_Binary`:  
 Bu iki işlevleri dizesi/ikili bilgiyi tutmak için statik bir arabellek erişinceye ve kaydetme & değeri yerine bu arabellekleri ODBC SQLBindCol ile kaydetmeniz gerekir. Bu nedenle, bu iki işlev özel durum kodu çok sayıda vardır.  
  
 `RFX_Date`:  
 ODBC kendi TIMESTAMP_STRUCT veri yapısında tarih ve saat bilgilerini döndürür. Bu işlev dinamik olarak bir TIMESTAMP_STRUCT bir "proxy" göndermek ve tarih saat verilerini almak için ayırır. Çeşitli işlemler arasında C++ tarih ve saat bilgilerini aktarmalısınız `CTime` nesne ve TIMESTAMP_STRUCT proxy. Bu önemli ölçüde bu işlev karmaşıklaştırır, ancak veri aktarımı için bir proxy kullanmayı iyi bir örneği değil.  
  
 `RFX_LongBinary`:  
 Yalnızca sınıf kitaplığı veri gönderip için sütun bağlama kullanmaz RFX işlevi budur. Bu işlev BindFieldToColumn işlemi yoksayar ve bunun yerine, düzeltme işlemi sırasında gelen SQL_LONGVARCHAR veya SQL_LONGVARBINARY verileri tutmak için depolama ayırır, ardından ayrılmış depolama alanına değerini almak için bir SQLGetData araması gerçekleştirir. Veri değerleri (örneğin, NameValue ve değer işlemleri) veri kaynağına geri göndermek hazırlık yaparken bu işlevi ODBC DATA_AT_EXEC işlevi kullanır. Bkz: [Teknik Not 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) SQL_LONGVARBINARY ve SQL_LONGVARCHARs ile çalışma hakkında daha fazla bilgi.  
  
 Kendi yazılırken **RFX_** işlevi, genellikle gerçekleştirilecektir kullanabilmek için `CFieldExchange::Default` belirli bir işlemi uygulamak için. Varsayılan uygulama söz konusu işlemi için bakın. İşlemi gerçekleştirdiğinde, yazılırken, **RFX_** için temsilci işlevi `CFieldExchange::Default`. Arama örnekleri görebilirsiniz `CFieldExchange::Default` dbrfx.cpp içinde  
  
 Çağrı önemlidir `IsFieldType` RFX işlevi ve hemen FALSE dönerse return başlangıcında. Bu mekanizma üzerinde gerçekleştirilen gelen parametre işlemleri tutar *outputColumns*, bunun tam tersi (arama gibi `BindParam` üzerinde bir *outputColumn*). Ayrıca, `IsFieldType` otomatik olarak sayısını izler *outputColumns* (*m_nFields*) ve parametrelerin (*m_nParams*).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

