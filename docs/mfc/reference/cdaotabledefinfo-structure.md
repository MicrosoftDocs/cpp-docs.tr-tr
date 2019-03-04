---
title: CDaoTableDefInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDefInfo
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
ms.openlocfilehash: 5785ed19c6929e19c7d376efa012dd1c059611c7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273715"
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo Yapısı

`CDaoTableDefInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan tabledef nesnesi hakkında bilgiler içerir.

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

*m_strName*<br/>
Benzersiz tabledef nesne adları. Doğrudan bu özelliğin değerini almak için tabledef nesnenin çağrı [GetName](../../mfc/reference/cdaotabledef-class.md#getname) üye işlevi. Daha fazla bilgi için "Name özelliği" DAO Yardım konusuna bakın.

*m_bUpdatable*<br/>
Tabloya değişiklikler yapılıp yapılmayacağı gösterir. Açmak için bir tablo güncelleştirilebilir olup olmadığını belirlemek için en hızlı yolu olan bir `CDaoTableDef` nesne tablosu için ve nesnenin [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) üye işlevi. `CanUpdate` her zaman (TRUE) için yeni oluşturulan tabledef nesnesi ile 0 (FALSE) bir ekli tabledef nesne için sıfır döndürür. Yeni bir tabledef nesne yazmak için izne sahip geçerli kullanıcı için bir veritabanı yalnızca eklenmiş. Tablo yalnızca güncellenemeyen alanlar içeriyorsa `CanUpdate` 0 döndürür. Bir veya daha fazla alan güncelleştirilebilir, olduğunda `CanUpdate` sıfır döndürür. Yalnızca güncelleştirilebilir alanlarını düzenleyebilirsiniz. Daha fazla bilgi için DAO Yardımı'nda "güncelleştirilebilir özelliği" konusuna bakın.

*m_lAttributes*<br/>
Tabledef nesnesiyle temsil edilen tablo özelliklerini belirtir. Geçerli değer özelliği öznitelikleri almak için arama, [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) üye işlevi. Döndürülen değer bu uzun sabiti bir birleşimi olabilir (bit düzeyinde OR kullanarak (**&#124;**) işleci):

- `dbAttachExclusive` Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için tablo özel kullanım için açılan eklenen tablonun gösterilir.

- `dbAttachSavePWD` Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için kullanıcı Kimliğini ve parolasını eklenen tablonun bağlantı bilgileriyle birlikte kaydedilir gösterir.

- `dbSystemObject` Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu olduğunu gösterir. (Salt okunur.)

- `dbHiddenObject` Tablonun Microsoft Jet veritabanı motoru (için geçici kullanım için) tarafından sağlanan gizli bir tablo gösterir. (Salt okunur.)

- `dbAttachedTable` Tablo Paradox veritabanı gibi bir ODBC olmayan veritabanına ekli bir tablodan olduğunu gösterir.

- `dbAttachedODBC` Ekli bir Microsoft SQL Server gibi bir ODBC veritabanı tablosundan tablo olduğunu gösterir.

*m_dateCreated*<br/>
Tarih ve saat tablo oluşturuldu. Doğrudan tablonun oluşturulma tarihi almak için arama [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) üye işlevinin `CDaoTableDef` tabloyla ilişkili nesne. Açıklamaları aşağıda daha fazla bilgi için bkz. İlgili bilgiler için DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

*m_dateLastUpdated*<br/>
Tablo Tasarımı için yapılan en son değişikliği saat ve tarihi. Doğrudan tablonun son güncelleme tarihi almak için arama [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) üye işlevinin `CDaoTableDef` tabloyla ilişkili nesne. Açıklamaları aşağıda daha fazla bilgi için bkz. İlgili bilgiler için DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

*m_strSrcTableName*<br/>
Varsa eklenen tablonun adını belirtir. Doğrudan kaynak tablo adını almak için arama [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) üye işlevinin `CDaoTableDef` tabloyla ilişkili nesne.

*m_strConnect*<br/>
Açık bir veritabanının kaynak hakkında bilgi sağlar. Bu özellik çağırarak denetleyebilirsiniz [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) üye işlevini, `CDaoTableDef` nesne. Hakkında daha fazla bilgi için bağlantı dizesi, bkz: `GetConnect`.

*m_strValidationRule*<br/>
Değiştirilmiş veya tabloya eklenen tabledef alanlardaki veriler doğrulayan bir değer. Doğrulama, yalnızca Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için desteklenir. Doğrulama kuralı doğrudan almak için arama [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) üye işlevinin `CDaoTableDef` tabloyla ilişkili nesne. İlgili bilgiler için DAO Yardımı'nda "ValidationRule özelliğini" konusuna bakın.

*m_strValidationText*<br/>
Eğer ValidationRule özelliği tarafından belirtilen doğrulama kuralı uygulamanızı görüntülemesi gerektiğini belirten bir ileti metnini belirten bir değeri. İlgili bilgiler için DAO Yardımı'nda "ValidationText özelliği" konusuna bakın.

*m_lRecordCount*<br/>
Tabledef nesnesinde erişilen kayıt sayısı. Bu özellik ayarı salt okunur. Doğrudan kayıt sayısını almak için arama [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) üye işlevinin `CDaoTableDef` nesne. Belgelerine `GetRecordCount` daha fazla kayıt sayısı açıklar. Çok sayıda kayıt tablosu içeriyorsa, bu sayı alınırken zaman alıcı bir işlem olabileceğini unutmayın.

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi tabledef olan [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) sınıf üyesi işlevinde `CDaoDatabase`.

Tarafından alınan bilgileri [CDaoDatabase::GetTableDefCount](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) üye işlevi depolanan bir `CDaoTableDefInfo` yapısı. Çağrı `GetTableDefInfo` üye işlevinin `CDaoDatabase` tabledef nesnesi, TableDefs koleksiyonu içinde depolanan nesne. `CDaoTableDefInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoTableDefInfo` nesne.

Tarih ve saat ayarları üzerinde temel tablo oluşturulduğu veya en son güncelleştirilen bilgisayardan türetilir. Çok kullanıcılı bir ortamda kullanıcılar bu Notes tutarsızlıkları önlemek için ayarları dosya sunucusundan doğrudan ve LastUpdated özellik ayarları almanız gerekir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)
