---
title: 'TN053: DAO için özel DFX rutinleri veritabanı sınıfları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dfx
dev_langs:
- C++
helpviewer_keywords:
- MFC, DAO and
- database classes [MFC], DAO
- DAO [MFC], MFC
- DFX (DAO record field exchange) [MFC], custom routines
- TN053
- DAO [MFC], classes
- DFX (DAO record field exchange) [MFC]
- custom DFX routines [MFC]
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47d1c9769055e0ab69f57f58b136b7844cb1f860
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: DAO Veritabanı Sınıfları için Özel DFX Rutinleri
> [!NOTE]
>  Visual C++ ortamı ve sihirbazları DAO (DAO sınıfları dahil edilmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, kullanmanızı önerir [OLE DB Şablonları](../data/oledb/ole-db-templates.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) yeni projeler için. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.  
  
 Bu teknik Not DAO kayıt alanı değişimi (DFX) mekanizmasını açıklar. DFX yordamları neler olduğunu anlamanıza yardımcı olması için `DFX_Text` işlevi, ayrıntılı bir örnek olarak verilecektir. Bir ek bilgi kaynağı olarak bu teknik unutmayın, kod için diğer tek tek DFX işlevleri inceleyebilirsiniz. Büyük olasılıkla özel DFX yordamına (ODBC veritabanı sınıfları ile kullanılır) özel bir RFX yordamı gerekebilecek sıklıkta gerekmez.  
  
 Bu teknik Not içerir:  
  
-   DFX genel bakış  
  
- [Örnekler](#_mfcnotes_tn053_examples) DAO kayıt alanı değişimi ve dinamik bağlama kullanma  
  
- [DFX nasıl çalışır?](#_mfcnotes_tn053_how_dfx_works)  
  
- [Özel DFX alışkanlık yaptığı](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)  
  
- [DFX_Text ayrıntıları](#_mfcnotes_tn053_details_of_dfx_text)  
  
 **DFX genel bakış**  
  
 DAO kayıt alanı değişimi mekanizması (DFX) alırken ve verileri kullanırken, güncelleştirme yordamı kolaylaştırmak için kullanılan `CDaoRecordset` sınıfı. Veri üyeleri kullanarak işlem Basitleştirilmiş `CDaoRecordset` sınıfı. Türetme tarafından `CDaoRecordset`, bir tablodaki veya sorgudaki her bir alan temsil eden türetilmiş bir sınıf veri üyeleri ekleyebilirsiniz. Bu "statik bağlama" mekanizması basittir ancak tüm uygulamalar için veri getirme/güncelleştirme yöntemi tercih olmayabilir. DFX ilişkili her alan geçerli kayıt her değiştirildiğinde alır. Para birimi değiştirildiğinde, her alan getirme gerektirmeyen bir performans duyarlı uygulama geliştiriyorsanız, "dinamik bağlama" aracılığıyla `CDaoRecordset::GetFieldValue` ve `CDaoRecordset::SetFieldValue` veri erişim yöntemi tercih olabilir.  
  
> [!NOTE]
>  Statik ve dinamik bağlama karma kullanımını kullanılabilmesi için DFX ve dinamik bağlama birbirini dışlayan değildir.  
  
## <a name="_mfcnotes_tn053_examples"></a> Örnek 1 — DAO kayıt alanı değişimi yalnızca kullanımı  
  
 (varsayar `CDaoRecordset` — türetilmiş sınıf `CMySet` açık)  
  
```  
// Add a new record to the customers table  
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```  
  
 **Örnek 2 — kullanımını, yalnızca dinamik bağlama**  
  
 (kullanan varsaymaktadır `CDaoRecordset` sınıfı, `rs`, ve zaten açık olan)  
  
```  
// Add a new record to the customers table  
COleVariant  varFieldValue1 (_T("MSFT"),
    VT_BSTRT);

//Note: VT_BSTRT flags string type as ANSI,
    instead of UNICODE default  
COleVariant  varFieldValue2  (_T("Microsoft"),
    VT_BSTRT);

rs.AddNew();

rs.SetFieldValue(_T("Customer_ID"),
    varFieldValue1);

rs.SetFieldValue(_T("Customer_Name"),
    varFieldValue2);

rs.Update();
```  
  
 **Örnek 3 — Kullanım DAO kayıt alanı değişimi ve dinamik bağlama**  
  
 (gözatma çalışan verilerle varsayar `CDaoRecordset`-türetilmiş sınıf `emp`)  
  
```  
// Get the employee's data so that it can be displayed  
emp.MoveNext();

 
// If user wants to see employee's photograph,  
// fetch it  
COleVariant varPhoto;  
if (bSeePicture)  
    emp.GetFieldValue(_T("photo"),
    varPhoto);

 
// Display the data  
PopUpEmployeeData(emp.m_strFirstName,  
    emp.m_strLastName,
    varPhoto);
```  
  
## <a name="_mfcnotes_tn053_how_dfx_works"></a> DFX nasıl çalışır?  
  
 MFC ODBC sınıfları tarafından kullanılan kayıt alanı değişimi (RFX) mekanizması için benzer bir şekilde DFX mekanizması çalışır. DFX ve RFX ilkeleri aynıdır, ancak çok sayıda dahili farklılıklar vardır. DFX işlevleri tasarımını sağlayacak şekilde neredeyse tüm kod tek tek DFX yordamları tarafından paylaşılan oluştu. Yüksek düzey DFX yalnızca birkaç şey yapar.  
  
-   DFX yapıları SQL **seçin** yan tümcesi ve SQL **parametreleri** gerekirse yan tümcesi.  
  
-   DFX DAO tarafından 's kullanılan bağlama yapısı oluşturur `GetRows` işlevi (Bu, daha sonra daha fazla).  
  
-   DFX (iki kez arabelleğe alma kullanılıyorsa) kirli alanları algılamak için kullanılan veri arabelleği yönetir  
  
-   DFX yönetir **NULL** ve **DIRTY** durum diziler ve güncelleştirmeleri gerekirse değerlerini ayarlar.  
  
 DFX Kalp mekanizmasıdır `CDaoRecordset` türetilmiş sınıf'ın `DoFieldExchange` işlevi. Bu işlev çağrıları uygun işlemi bir türde ayrı ayrı DFX işlevleri gönderir. Çağırmadan önce `DoFieldExchange` iç MFC işlevleri işlemi türünü ayarlayın. Aşağıdaki listede, çeşitli işlem türlerini ve kısa bir açıklama gösterir.  
  
|Çalışma|Açıklama|  
|---------------|-----------------|  
|**AddToParameterList**|Derlemeleri parametreleri yan tümcesi|  
|**AddToSelectList**|Derlemeleri SELECT yan tümcesi|  
|**BindField**|Bağlama yapısı ayarlar|  
|**BindParam**|Parametre değerlerini ayarlar|  
|**Düzeltmesi**|NULL durumu ayarlar|  
|**AllocCache**|Önbellek kirli denetle ayırır|  
|**StoreField**|Geçerli kayıt önbelleğine kaydeder|  
|**LoadField**|Üye değerleri önbelleğine geri yükler|  
|**FreeCache**|Önbelleği boşaltır|  
|`SetFieldNull`|& Durum NULL değerine ayarlar alan|  
|**MarkForAddNew**|Alanları kirli değilse SÖZDE NULL işaretler|  
|**MarkForEdit**|İşaretleri alanları kirli IF önbellek eşleşmiyor|  
|**SetDirtyField**|Ayarlar kirli olarak işaretlenmiş değerleri alan|  
  
 Daha fazla ayrıntı için her bir işlemin sonraki bölümde açıklanacaktır `DFX_Text`.  
  
 DAO kayıt alanı değişimi işlemi hakkında anlamak için en önemli özelliği, kullanmasıdır `GetRows` işlevinin `CDaoRecordset` nesnesi. DAO `GetRows` işlevi, çeşitli yollarla çalışabilir. Bu teknik not yalnızca kısaca açıklayan `GetRows` olarak bu Teknik Not kapsamı dışında.  
  
 DAO `GetRows` çeşitli yollarla çalışabilirsiniz.  
  
-   Bir seferde birden çok kayıt ve verilerin birden çok alan getirebilir. Bu, olası bir büyük veri yapısı ve her bir alan için uygun uzaklıkları postalarla ile daha hızlı veri erişimi ve verilerin yapısı, her kayıt için sağlar. MFC mekanizması getirme bu birden çok kaydı avantajlarından yararlanmak değil.  
  
-   Başka bir yolu `GetRows` olabilir iştir alınan veriler veri tek bir kayıt için her bir alan için bağlama adresi belirtmeniz programcıların izin vermek için.  
  
-   DAO "geri çağıran değişken uzunlukta sütunlar için bellek tahsis etmek arayan izin vermek üzere çağırıp" olur. Bu ikinci özelliği veri kopya sayısını en aza yanı sıra veri doğrudan depolama bir sınıf üyeleri izin verme avantajına sahiptir ( `CDaoRecordset` türetilmiş sınıf). MFC kullandığı veri üyeleri bağlamak için bir yöntem bu ikinci mekanizmasıdır `CDaoRecordset` türetilmiş sınıfları.  
  
##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> Özel DFX alışkanlık yaptığı  
 Herhangi bir DFX işlevde uygulanan en önemli işlemi başarıyla çağırmak için gerekli veri yapılarını ayarlamanıza olanak olması gereken Bu tartışmayı açıktır `GetRows`. DFX işlevi de desteklemesi gereken diğer işlemleri, ancak none önemli veya karmaşık doğru hazırlık olarak bir dizi vardır `GetRows` çağırın.  
  
 DFX kullanımını çevrimiçi belgelerinde açıklanmıştır. Esas olarak, iki gereksinimi yoktur. İlk olarak, üyeler eklenmeli `CDaoRecordset` türetilmiş sınıf her ilişkili alan ve parametre. Bu aşağıdaki `CDaoRecordset::DoFieldExchange` geçersiz kılınmalıdır. Veri türü üyesinin önemli olduğunu unutmayın. Bu alanın veritabanındaki verilerden eşleşen veya en az bu türe dönüştürülebilir gerekir. Örneğin bir sayısal alana uzun tamsayı gibi veritabanına zaman metne dönüştürülecek ve bağlı bir `CString` üye, ancak bir metin alanı bir veritabanında mutlaka uzun tamsayı gibi sayısal bir gösterimi dönüştürülür ve uzun integ için bağlı er üye. DAO ve Microsoft Jet veritabanı altyapısı dönüştürme (yerine için MFC) sorumludur.  
  
##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> DFX_Text ayrıntıları  
 Daha önce belirtildiği gibi DFX nasıl çalıştığını açıklamak için iyi bir örnek üzerinde çalışmak için yoludur. İçyüzü giderek bu amaçla `DFX_Text` DFX temel en az bir anlayış sağlanmasına yardımcı olmak amacıyla oldukça düzgün çalışması gerekir.  
  
 **AddToParameterList**  
 Bu işlem SQL derlemeler **parametreleri** yan tümcesi ("`Parameters <param name>, <param type> ... ;`") Jet tarafından gerekli. Her parametre adı ve (RFX çağrısında belirtildiği şekilde) belirtilmiş. İşlev bkz **CDaoFieldExchange::AppendParamType** tek tek türlerinin adlarını görmek için işlev. Durumunda `DFX_Text`, kullanılan türü `text`.  
  
 **AddToSelectList**  
 SQL derlemeler **seçin** yan tümcesi. Bu oldukça doğrudan İleri DFX çağrısı tarafından belirtilen sütun adı yalnızca olarak eklenir ("`SELECT <column name>, ...`").  
  
 **BindField**  
 En karmaşık işlemleri. DAO bağlama yapısı tarafından kullanıldığı budur daha önce belirtildiği gibi `GetRows` ayarlanır. Koddan gördüğünüz `DFX_Text` kullanılan DAO türü yapısı içinde bilgi türleri içerir (**DAO_CHAR** veya **DAO_WCHAR** durumunda `DFX_Text`). Ayrıca, kullanılan bağlama türü de ayarlanır. Bir önceki bölümde `GetRows` yalnızca kısaca açıklanmıştır, ancak MFC tarafından kullanılan bağlama türü her zaman doğrudan adresi bağlama olduğunu açıklamak yeterli (**DAOBINDING_DIRECT**). Değişken uzunluklu sütun bağlama için ayrıca (gibi `DFX_Text`) geri çağırma bağlama kullanılan böylece MFC Bellek ayırma denetlemek ve doğru uzunlukta bir adres belirtin. Ne bu o MFC olduğu anlamına gelir her zaman DAO böylece doğrudan üye değişkenlerine bağlama sağlar verileri yerleştirmek "burada" anlayabilirsiniz. Bağlama yapısı kalan adresini bellek ayırma geri çağırma işlevi (sütun adıyla bağlama) sütun bağlama türü ve gibi şeyleri doldurulur.  
  
 **BindParam**  
 Bu çağrı, basit bir işlemdir `SetParamValue` belirlenen parametre üyesi parametre değerine sahip.  
  
 **Düzeltmesi**  
 Doldurur **NULL** her bir alan için durum.  
  
 `SetFieldNull`  
 Bu işlem yalnızca her bir alan durumu olarak işaretler **NULL** ve üye değişkenin değeri olarak ayarlar **PSEUDO_NULL**.  
  
 **SetDirtyField**  
 Çağrıları `SetFieldValue` kirli olarak işaretlenmiş her bir alan için.  
  
 Kalan tüm işlemleri yalnızca veri önbelleği kullanma ile ilgilidir. Veri, belirli konular daha kolay yapmak için kullanılan geçerli kayıt verilerin ek bir arabellek önbelleğidir. Örneğin, "kirli" alanlarını otomatik olarak algılanabilir. Çevrimiçi belgelerinde açıklandığı gibi tamamen veya alan düzeyinde kapatılabilir. Arabellek uyarlamasını bir harita kullanır. Bu haritada dinamik olarak ayrılan kopyaları "bağlı" alanının adresi ile eşleştirmek için kullanılır (veya `CDaoRecordset` veri üyesi türetilmiş).  
  
 **AllocCache**  
 Dinamik olarak önbelleğe alınan alan değeri ayırır ve eşlemesine ekler.  
  
 **FreeCache**  
 Önbelleğe alınan alan değeri siler ve eşlemesinden kaldırır.  
  
 **StoreField**  
 Geçerli alan değeri veri önbelleğine kopyalar.  
  
 **LoadField**  
 Önbelleğe alınan değer alan üye kopyalar.  
  
 **MarkForAddNew**  
 Geçerli alan değeri olmayan olup olmadığını denetler**NULL** ve kirli gerekirse eşitler.  
  
 **MarkForEdit**  
 Veri önbelleği geçerli alan değerle karşılaştırır ve gerekirse kirli işaretler.  
  
> [!TIP]
>  Standart veri türleri için varolan DFX rutinleri üzerinde özel DFX yordamları model.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

