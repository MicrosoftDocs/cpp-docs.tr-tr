---
title: CDaoTableDefInfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53e20ca3f483bd9c00b298c69a526d8f5dd31cdb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo Yapısı
`CDaoTableDefInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan bir tabledef nesne hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoTableDefInfo  
{  
    CString m_strName;               // Primary  
    BOOL m_bUpdatable;               // Primary  
    long m_lAttributes;              // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    CString m_strSrcTableName;       // Secondary  
    CString m_strConnect;            // Secondary  
    CString m_strValidationRule;     // All  
    CString m_strValidationText;     // All  
    long m_lRecordCount;             // All  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `m_strName`  
 Tabledef nesnesi adlandıran. Bu özelliğin değerini doğrudan almak için tabledef nesnesinin çağrısı [GetName](../../mfc/reference/cdaotabledef-class.md#getname) üye işlevi. Daha fazla bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 `m_bUpdatable`  
 Tabloda değişiklikleri yapılan olup olmadığını gösterir. Açmak için bir tablo güncelleştirilebilir olup olmadığını belirlemek için en hızlı yolu olan bir `CDaoTableDef` nesne için tablo ve nesnenin çağrısı [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) üye işlevi. `CanUpdate` her zaman sıfır olmayan bir değer döndürür (**TRUE**) yeni oluşturulan tabledef nesnesi ve 0 (**FALSE**) ekli tabledef nesnesi. Yeni bir tabledef nesnesi yalnızca geçerli kullanıcının yazma izni olan bir veritabanı eklenmiş. Tablo yalnızca güncellenemeyen alanları içeriyorsa `CanUpdate` 0 döndürür. Bir veya daha fazla alan güncelleştirilebilir, olduğunda `CanUpdate` sıfır olmayan bir değer döndürür. Yalnızca güncelleştirilebilir alanları düzenleyebilirsiniz. Daha fazla bilgi için DAO Yardımı'ndaki "güncelleştirilebilir özellik" konusuna bakın.  
  
 `m_lAttributes`  
 Tabledef nesnesinin temsil ettiği tablo özelliklerini belirtir. Geçerli bir tabledef özniteliklerini almak için arama kendi [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) üye işlevi. Döndürülen değer bu uzun sabitleri bir bileşimi olabilir (veya Bitsel kullanarak (**&#124;**) işleci):  
  
- **dbAttachExclusive** Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için tablo özel kullanım için açılan ekli bir tablo gösterir.  
  
- **dbAttachSavePWD** Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için kullanıcı kimliği ve parola ekli tablo için bağlantı bilgileriyle birlikte kaydedilir gösterir.  
  
- **dbSystemObject** tablodur Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu gösterir. (Salt okunur.)  
  
- **dbHiddenObject** tablodur Microsoft Jet veritabanı altyapısı (için geçici kullanım için) tarafından sağlanan gizli bir tablo gösterir. (Salt okunur.)  
  
- **dbAttachedTable** tablodur Paradox veritabanı gibi bir ODBC olmayan veritabanı bağlı bir tablodan gösterir.  
  
- **dbAttachedODBC** tablodur Microsoft SQL Server gibi bir ODBC veritabanı bağlı bir tablodan gösterir.  
  
 `m_dateCreated`  
 Tarih ve saat tablo oluşturulmuş. Doğrudan tablonun oluşturulduğu tarihi almak için arama [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) üye işlevini `CDaoTableDef` tabloyla ilişkili nesne. Açıklamalar aşağıda daha fazla bilgi için bkz. İlgili bilgiler için DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
 `m_dateLastUpdated`  
 Tarih ve saat tablo tasarımı için yapılan en son değişikliğin. Tablonun son güncelleştirilen tarih doğrudan almak için arama [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) üye işlevini `CDaoTableDef` tabloyla ilişkili nesne. Açıklamalar aşağıda daha fazla bilgi için bkz. İlgili bilgiler için DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
 *m_strSrcTableName*  
 Varsa ekli bir tablo adını belirtir. Doğrudan kaynak tablo adı almak için arama [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) üye işlevini `CDaoTableDef` tabloyla ilişkili nesne.  
  
 `m_strConnect`  
 Açık bir veritabanını kaynak hakkında bilgi sağlar. Bu özellik çağırarak denetleyebilirsiniz [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) üye işlevini, `CDaoTableDef` nesnesi. Hakkında daha fazla bilgi için bağlantı dizesi, bkz: `GetConnect`.  
  
 `m_strValidationRule`  
 Tabledef alanlardaki veriler değiştirilmiş veya tabloya eklenen doğrulayan bir değer. Doğrulama Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için desteklenir. Doğrulama kuralının doğrudan almak için arama [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) üye işlevini `CDaoTableDef` tabloyla ilişkili nesne. İlgili bilgi için "ValidationRule özelliğinde" DAO Yardım konusuna bakın.  
  
 `m_strValidationText`  
 ValidationRule özelliği tarafından belirtilen doğrulama kuralı yok sağlanıyorsa, uygulamanızın görüntülenmelidir ileti metnini belirten bir değer. İlgili bilgi için DAO Yardımı'ndaki "ValidationText özelliği" konusuna bakın.  
  
 *m_lRecordCount*  
 Bir tabledef nesnesinde erişilen kayıtların sayısı. Bu özellik ayarı salt okunurdur. Doğrudan kayıt sayısı almak için arama [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) üye işlevini `CDaoTableDef` nesnesi. Belgelerine `GetRecordCount` daha fazla kayıt sayısı açıklar. Tablo çok sayıda kayıt içeriyorsa bu sayısı alınırken zaman alan bir işlem olabileceğini unutmayın.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi tabledef olan [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) üye işlevi sınıfında `CDaoDatabase`.  
  
 Tarafından alınan bilgileri [CDaoDatabase::GetTableDefCount](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) üye işlevi depolanır bir `CDaoTableDefInfo` yapısı. Çağrı `GetTableDefInfo` üye işlevini `CDaoDatabase` nesne olan TableDefs koleksiyonu tabledef nesnesi depolanır. `CDaoTableDefInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoTableDefInfo` nesnesi.  
  
 Tarih ve saat ayarları üzerinde temel tablo oluşturulmuş veya son güncelleştirme bilgisayardan türetilir. Çok kullanıcılı bir ortamda, bu dosya sunucusundan doğrudan Notes Tutarsızlıklardan kaçınmak için ayarları ve LastUpdated özellik ayarları kullanıcıların almanız gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)
