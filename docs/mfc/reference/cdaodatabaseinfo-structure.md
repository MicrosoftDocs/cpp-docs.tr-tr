---
title: Cdaodatabaseınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoDatabaseInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0815d248b6726d830fc50af9886c729c34ba2f29
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336487"
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
 *m_strName*  
 Veritabanı nesnesi benzersiz olarak adlandırır. Bu özellik doğrudan almak için arama [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Ayrıntılar için "Name özelliği" DAO Yardım konusuna bakın.  
  
 *m_bUpdatable*  
 Değişiklikler veritabanına yapılan olup olmadığını gösterir. Bu özellik doğrudan almak için arama [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Ayrıntılar için DAO Yardımı'nda "güncelleştirilebilir özelliği" konusuna bakın.  
  
 *m_bTransactions*  
 Bir veri kaynağı işlemleri destekleyip desteklemediğini belirten — daha sonra geri alınabilir değişiklikler dizisini kaydını (iptal edildi) veya kaydedilmiş (kaydedilir). Bir veritabanı Microsoft Jet veritabanı altyapısını temel alıyorsa, işlem sıfır olmayan bir özelliktir ve işlemleri kullanabilirsiniz. Diğer veritabanı altyapıları işlemleri desteklemiyor olabilir. Bu özellik doğrudan almak için arama [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Ayrıntılar için DAO Yardımı'nda "işlemleri özelliği" konusuna bakın.  
  
 *m_strVersion*  
 Microsoft Jet veritabanı altyapısı sürümünü gösterir. Doğrudan bu özelliğin değerini almak için veritabanı nesnesinin çağrı [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) üye işlevi. Ayrıntılar için DAO Yardımı'nda "Version özelliği" konusuna bakın.  
  
 *m_lCollatingOrder*  
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
  
 *m_nQueryTimeout*  
 Microsoft Jet veritabanı altyapısı bir zaman aşımı hatası önce bekleyeceği saniye sayısını bir ODBC veritabanı üzerinde bir sorgu çalıştırıldığında gerçekleşir. Varsayılan zaman aşımı değer 60 saniyedir. QueryTimeout 0 olarak ayarlandığında, hiçbir zaman aşımı oluşur; Bu programın yanıt vermeyi durdurmasına neden olabilir. Doğrudan bu özelliğin değerini almak için veritabanı nesnesinin çağrı [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) üye işlevi. Ayrıntılar için DAO Yardımı'nda "QueryTimeout özelliği" konusuna bakın.  
  
 *m_strConnect*  
 Açık bir veritabanının kaynak hakkında bilgi sağlar. Bilgi dizeleri hakkında bağlanın ve doğrudan bu özelliğin değerini alma hakkında daha fazla bilgi için bkz [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) üye işlevi. Daha fazla bilgi için DAO Yardımı'nda "özelliği Bağlan" konusuna bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 Veritabanı bir MFC nesne sınıfı, temel alınan bir DAO nesnedir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) üye işlevi.  
  
 Tarafından alınan bilgileri [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) üye işlevi depolanan bir `CDaoDatabaseInfo` yapısı. Çağrı `GetDatabaseInfo` için `CDaoWorkspace` veritabanı nesnesi olan veritabanları koleksiyonda depolanan nesne. `CDaoDatabaseInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoDatabaseInfo` nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)
