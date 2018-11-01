---
title: CDaoDatabaseInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoDatabaseInfo
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
ms.openlocfilehash: 43095707718fe00a746d082d30c689dbd05292bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564794"
---
# <a name="cdaodatabaseinfo-structure"></a>CDaoDatabaseInfo Yapısı

`CDaoDatabaseInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir veritabanı nesnesi hakkında bilgiler içerir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoDatabaseInfo
{
    CString m_strName;       // Primary
    BOOL m_bUpdatable;       // Primary
    BOOL m_bTransactions;    // Primary
    CString m_strVersion;    // Secondary
    long m_lCollatingOrder;  // Secondary
    short m_nQueryTimeout;   // Secondary
    CString m_strConnect;    // All
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
Veritabanı nesnesi benzersiz olarak adlandırır. Bu özellik doğrudan almak için arama [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Ayrıntılar için "Name özelliği" DAO Yardım konusuna bakın.

*m_bUpdatable*<br/>
Değişiklikler veritabanına yapılan olup olmadığını gösterir. Bu özellik doğrudan almak için arama [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Ayrıntılar için DAO Yardımı'nda "güncelleştirilebilir özelliği" konusuna bakın.

*m_bTransactions*<br/>
Bir veri kaynağı işlemleri destekleyip desteklemediğini belirten — daha sonra geri alınabilir değişiklikler dizisini kaydını (iptal edildi) veya kaydedilmiş (kaydedilir). Bir veritabanı Microsoft Jet veritabanı altyapısını temel alıyorsa, işlem sıfır olmayan bir özelliktir ve işlemleri kullanabilirsiniz. Diğer veritabanı altyapıları işlemleri desteklemiyor olabilir. Bu özellik doğrudan almak için arama [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Ayrıntılar için DAO Yardımı'nda "işlemleri özelliği" konusuna bakın.

*m_strVersion*<br/>
Microsoft Jet veritabanı altyapısı sürümünü gösterir. Doğrudan bu özelliğin değerini almak için veritabanı nesnesinin çağrı [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) üye işlevi. Ayrıntılar için DAO Yardımı'nda "Version özelliği" konusuna bakın.

*m_lCollatingOrder*<br/>
Dize karşılaştırma ve sıralama için metin sıralama düzeni dizisini belirtir. Olası değerler şunlardır:

- `dbSortGeneral` Genel (İngilizce, Fransızca, Almanca, Portekizce, İtalyanca ve Modern İspanyolca) sıralama düzeni kullanın.

- `dbSortArabic` Arapça sıralama düzenini kullanın.

- `dbSortCyrillic` Rusça sıralama düzenini kullanın.

- `dbSortCzech` Çekçe sıralama düzenini kullanın.

- `dbSortDutch` Felemenkçe sıralama düzenini kullanın.

- `dbSortGreek` Yunanca sıralama düzenini kullanın.

- `dbSortHebrew` İbranice sıralama düzenini kullanın.

- `dbSortHungarian` Macarca sıralama düzenini kullanın.

- `dbSortIcelandic` İzlanda sıralama düzenini kullanın.

- `dbSortNorwdan` Norveççe veya Danca sıralama düzenini kullanın.

- `dbSortPDXIntl` Paradox Uluslararası sıralama düzenini kullanın.

- `dbSortPDXNor` Norveççe Paradox veya Danca sıralama düzeni kullanın.

- `dbSortPDXSwe` Paradox İsveççe veya Fince sıralama düzeni kullanın.

- `dbSortPolish` Lehçe sıralama düzenini kullanın.

- `dbSortSpanish` İspanyolca sıralama düzenini kullanın.

- `dbSortSwedFin` İsveç dili veya Fince sıralama düzenini kullanın.

- `dbSortTurkish` Türkçe sıralama düzenini kullanın.

- `dbSortUndefined` Sıralama düzenini tanımsız veya bilinmeyen.

Daha fazla bilgi için "Özelleştirme Windows kayıt defteri ayarları için veri erişim" DAO Yardım konusuna bakın.

*m_nQueryTimeout*<br/>
Microsoft Jet veritabanı altyapısı bir zaman aşımı hatası önce bekleyeceği saniye sayısını bir ODBC veritabanı üzerinde bir sorgu çalıştırıldığında gerçekleşir. Varsayılan zaman aşımı değer 60 saniyedir. QueryTimeout 0 olarak ayarlandığında, hiçbir zaman aşımı oluşur; Bu programın yanıt vermeyi durdurmasına neden olabilir. Doğrudan bu özelliğin değerini almak için veritabanı nesnesinin çağrı [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) üye işlevi. Ayrıntılar için DAO Yardımı'nda "QueryTimeout özelliği" konusuna bakın.

*m_strConnect*<br/>
Açık bir veritabanının kaynak hakkında bilgi sağlar. Bilgi dizeleri hakkında bağlanın ve doğrudan bu özelliğin değerini alma hakkında daha fazla bilgi için bkz [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) üye işlevi. Daha fazla bilgi için DAO Yardımı'nda "özelliği Bağlan" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

Veritabanı bir MFC nesne sınıfı, temel alınan bir DAO nesnedir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) üye işlevi.

Tarafından alınan bilgileri [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) üye işlevi depolanan bir `CDaoDatabaseInfo` yapısı. Çağrı `GetDatabaseInfo` için `CDaoWorkspace` veritabanı nesnesi olan veritabanları koleksiyonda depolanan nesne. `CDaoDatabaseInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoDatabaseInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace Sınıfı](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)
