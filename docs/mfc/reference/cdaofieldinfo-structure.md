---
title: "Cdaofieldınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoFieldInfo
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63fdab9bae7238f427ff2015beffd53570603af4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo Yapısı
`CDaoFieldInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan bir alan nesne hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoFieldInfo  
{  
    CString m_strName;           // Primary  
    short m_nType;               // Primary  
    long m_lSize;                // Primary  
    long m_lAttributes;          // Primary  
    short m_nOrdinalPosition;    // Secondary  
    BOOL m_bRequired;            // Secondary  
    BOOL m_bAllowZeroLength;     // Secondary  
    long m_lCollatingOrder;      // Secondary  
    CString m_strForeignName;    // Secondary  
    CString m_strSourceField;    // Secondary  
    CString m_strSourceTable;    // Secondary  
    CString m_strValidationRule; // All  
    CString m_strValidationText; // All  
    CString m_strDefaultValue;   // All  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `m_strName`  
 Alan nesne adlandıran. Ayrıntılar için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 `m_nType`  
 Alanın veri türünü belirten bir değer. Ayrıntılar için DAO Yardımı'ndaki "Type özelliği" konusuna bakın. Bu özelliğin değeri aşağıdakilerden biri olabilir:  
  
- **dbBoolean** Evet/Hayır, aynı **TRUE**/**FALSE**  
  
- **dbByte** bayt  
  
- **dbInteger** kısa  
  
- **dbLong** uzun  
  
- **dbCurrency** para birimi; bkz: MFC sınıf [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **dbSingle** tek  
  
- **dbDouble** çift  
  
- **dbDate** tarih/saat; bkz: MFC sınıf [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **dbText** metin; bkz: MFC sınıfı [CString](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **dbLongBinary** uzun ikili (OLE nesnesi); MFC sınıfı kullanmak isteyebilirsiniz [CLongBinary](../../mfc/reference/cbytearray-class.md) sınıfı yerine `CLongBinary` olarak `CByteArray` daha zengin ve daha kolay kullanılır.  
  
- **dbMemo** notları; bkz: MFC sınıfı`CString`  
  
- **dbGUID** bir genel benzersiz tanımlayıcı/evrensel benzersiz uzak yordam çağrıları ile kullanılan tanımlayıcı. Daha fazla bilgi için DAO Yardımı'ndaki "Type özelliği" konusuna bakın.  
  
> [!NOTE]
>  Dize veri türleri ikili veriler için kullanmayın. Bu, verilerinizi artan yükü ve büyük olasılıkla beklenmeyen çeviri kaynaklanan Unicode/ANSI çeviri katmanına geçmesine neden olur.  
  
 *m_lSize*  
 Metin veya metin veya sayı değerlerini içeren bir alan nesne sabit boyutlu içeren DAO field nesnesinin bayt cinsinden en büyük boyutu gösteren bir değer. Ayrıntılar için DAO Yardımı'ndaki "boyut özelliği" konusuna bakın. Boyutları aşağıdaki değerlerden biri olabilir:  
  
|Tür|Boyut (bayt)|Açıklama|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 bayt|Evet/Hayır (True/False ile aynı)|  
|**dbByte**|1.|Bayt|  
|**dbInteger**|2|Tamsayı|  
|**dbLong**|4|uzun|  
|**dbCurrency**|8|Para birimi ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Tek|  
|**dbDouble**|8|Çift|  
|**dbDate**|8|Tarih/saat ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Metin ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Uzun İkili (OLE nesnesi; [CLongBinary](../../mfc/reference/cbytearray-class.md); yerine kullanmak `CLongBinary`)|  
|**dbMemo**|0|Not ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbGUID**|16|Genel olarak benzersiz bir tanımlayıcı/evrensel benzersiz uzak yordam çağrıları ile kullanılan tanımlayıcı.|  
  
 `m_lAttributes`  
 Tabledef, kayıt kümesi, querydef veya dizin nesnesi tarafından yer alan nesne özelliklerini belirtir. Döndürülen değer Bitsel veya C++ ile oluşturulan bu sabitleri toplamını olabilir (**&#124;**) işleci:  
  
- **dbFixedField** alan boyutu (varsayılan sayısal alanlar için) sabittir.  
  
- **dbVariableField** alan boyutu değişkenidir (yalnızca metin alanları).  
  
- **dbAutoIncrField** yeni kayıtlar için alan değeri değiştirilemez bir benzersiz uzun tamsayı olarak otomatik olarak arttırılır. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.  
  
- **dbUpdatableField** alan değeri değiştirilebilir.  
  
- **dbDescending** alan azalan düzende sıralanır (Z - A veya 100-0) (yalnızca bir alan nesnesi bir alanlar koleksiyonu dizin nesnenin; MFC, dizin nesneleri kendilerini bulunuyorsa tabledef nesneleri için geçerlidir). Bu sabit atlarsanız, alan artan düzende sıralanır (A - Z veya 0 - 100) sipariş (varsayılan).  
  
 Bu özellik ayarı denetlerken C++ bit düzeyinde kullanabilirsiniz- ve işleci (**&**) için belirli bir öznitelik test etmek için. Birden çok öznitelik ayarlarken, bunları uygun sabitleri Bitsel veya ile birleştirerek birleştirebilirsiniz (**&#124;**) işleci. Ayrıntılar için DAO Yardımı'ndaki "öznitelikler özelliği" konusuna bakın.  
  
 *m_nOrdinalPosition*  
 Diğer alanlara göre görüntülenecek bir DAO alan nesnesiyle temsil edilen bir alan istediğiniz sayısal sırayı belirten bir değer. Bu özellik ile ayarlayabilirsiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Ayrıntılar için DAO Yardımı'ndaki "OrdinalPosition özelliğini" konusuna bakın.  
  
 `m_bRequired`  
 DAO alan nesne Null olmayan bir değer gerekli olup olmadığını gösterir. Bu özellik ise **doğru**, alan Null bir değere izin vermiyor. Kümesi gerekli olursa **yanlış**, alan AllowZeroLength ve ValidationRule özellik ayarları tarafından belirtilen koşullara uyan değerlerinin yanı sıra Null değerler içerebilir. Ayrıntılar için DAO Yardımı'ndaki "özelliği gerekli" konusuna bakın. Bu özellik ile tabledef için ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_bAllowZeroLength*  
 Gösterir boş bir dize olup olmadığını ("") bir metin veya Not veri türüne sahip bir DAO alan nesnesinin geçerli bir değer. Bu özellik ise **doğru**, geçerli bir değer boş bir dizedir. Bu özelliği ayarlamak **FALSE** bir alanın değerini ayarlamak için boş bir dize kullanamazsınız emin olmak için. Ayrıntılar için DAO Yardımı'ndaki "AllowZeroLength özelliği" konusuna bakın. Bu özellik ile tabledef için ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_lCollatingOrder`  
 Dize karşılaştırma ve sıralama metninde sıralama düzenini dizisini belirtir. Ayrıntılar için "Özelleştirme Windows kayıt defteri ayarları için veri erişim" DAO Yardım konusuna bakın. Döndürülen olası değerler listesi için bkz: **m_lCollatingOrder** üyesi [Cdaodatabaseınfo](../../mfc/reference/cdaodatabaseinfo-structure.md) yapısı. Bu özellik ile tabledef için ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strForeignName`  
 Bir ilişkisinde birincil bir tablodaki bir alana karşılık gelen bir yabancı tabloda DAO alan nesnesinin adını belirten bir değer. Ayrıntılar için DAO Yardımı'ndaki "ForeignName özelliği" konusuna bakın.  
  
 *m_strSourceField*  
 Özgün tabledef, kayıt kümesi veya querydef nesnesi tarafından bulunan DAO field nesnesi için veri kaynağı alanının adı gösterir. Bu özellik, bir alan nesnesiyle ilişkili özgün alan adını gösterir. Örneğin, özgün adı temel alınan tabloda yer alan adını ilgisiz olan bir sorgu alandaki veri kaynağını belirlemek için bu özelliği kullanabilirsiniz. Ayrıntılar için DAO Yardımı'ndaki "SourceField, SourceTable özellikleri" konusuna bakın. Bu özellik ile tabledef için ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strSourceTable*  
 Tabledef, kayıt kümesi veya querydef nesnesi tarafından bulunan DAO alan nesne verileri, özgün kaynak tablonun adını gösterir. Bu özellik, bir alan nesnesiyle ilişkili özgün tablo adını gösterir. Örneğin, özgün adı temel alınan tabloda yer alan adını ilgisiz olan bir sorgu alandaki veri kaynağını belirlemek için bu özelliği kullanabilirsiniz. Ayrıntılar için DAO Yardımı'ndaki "SourceField, SourceTable özellikleri" konusuna bakın. Bu özellik ile tabledef için ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strValidationRule`  
 Bir alandaki veri değiştirilmiş veya tabloya eklenen doğrulayan bir değer. Ayrıntılar için DAO Yardımı'ndaki "ValidationRule özelliğini" konusuna bakın. Bu özellik ile tabledef için ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 Tabledefs hakkında ilgili bilgi için bkz: **m_strValidationRule** üyesi [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısı.  
  
 `m_strValidationText`  
 DAO alan nesnenin değerini ValidationRule özellik ayarı tarafından belirtilen doğrulama kuralı karşılamadığı, uygulamanızın görüntülediği ileti metnini belirten bir değer. Ayrıntılar için DAO Yardımı'ndaki "ValidationText özelliği" konusuna bakın. Bu özellik ile tabledef için ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strDefaultValue*  
 DAO alan nesne varsayılan değeri. Yeni bir kayıt oluşturulduğunda, DefaultValue özellik ayarı için alan değeri olarak otomatik olarak girilir. Ayrıntılar için DAO Yardımı'ndaki "DefaultValue özelliği" konusuna bakın. Bu özellik ile tabledef için ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
## <a name="remarks"></a>Açıklamalar  
 Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek `GetFieldInfo` sınıflardaki üye işlevi [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), ve [ CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).  
  
 Alan nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, aşağıdaki sınıflar, MFC nesneleri temel alınan DAO nesneleri alan nesne koleksiyonları içerir: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), ve [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Bu sınıfların bazı tek tek öğelere alan bilgilerinin erişmek için üye işlevleri sağlamak ya da bunları tamamını tek seferde erişebilirsiniz bir `CDaoFieldInfo` çağırarak nesne `GetFieldInfo` kapsayan nesnenin üye işlevi.  
  
 Nesne özelliklerinin incelenmesi için kullanımı yanı sıra, kullanabilirsiniz `CDaoFieldInfo` bir tabledef yeni alanları oluşturmak için bir giriş parametresi oluşturulamadı. Bu görev için daha basit seçenekleri mevcuttur, ancak daha hassas denetim isterseniz, sürümünü kullanabilirsiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) alan bir `CDaoFieldInfo` parametresi.  
  
 Tarafından alınan bilgileri `GetFieldInfo` sınıfının üye işlevini (alanını içeren) depolanır bir `CDaoFieldInfo` yapısı. Çağrı `GetFieldInfo` üye işlevini, alanlar koleksiyonunda alan nesne depolandığı içeren nesne. `CDaoFieldInfo`Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoFieldInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)

