---
title: "Cdaodatabaseınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoDatabaseInfo
dev_langs: C++
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c445d2db084e6148032cfde0c356ad88ad1cccfa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdaodatabaseinfo-structure"></a>CDaoDatabaseInfo Yapısı
`CDaoDatabaseInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan bir veritabanı nesnesi hakkında bilgiler içerir.  
  
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
 `m_strName`  
 Veritabanı nesnesinin adlandıran. Bu özellik doğrudan almak için arama [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Ayrıntılar için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 `m_bUpdatable`  
 Değişiklikler veritabanına yapılan olup olmadığını gösterir. Bu özellik doğrudan almak için arama [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Ayrıntılar için DAO Yardımı'ndaki "güncelleştirilebilir özellik" konusuna bakın.  
  
 *m_bTransactions*  
 Bir veri kaynağı işlemleri destekleyip desteklemediğini belirten — bir dizi daha sonra geri alınması değişiklikleri kaydetme (İptal) ya da kaydedilmiş (kaydedilir). Microsoft Jet veritabanı altyapısı bir veritabanını temel alıyorsa, işlemleri sıfır olmayan bir özelliktir ve işlemleri kullanabilirsiniz. Diğer veritabanı motoru işlemleri desteklemiyor olabilir. Bu özellik doğrudan almak için arama [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Ayrıntılar için "İşlemler özelliğinde" DAO Yardım konusuna bakın.  
  
 *m_strVersion*  
 Microsoft Jet veritabanı altyapısı sürümünü gösterir. Bu özelliğin değerini doğrudan almak için veritabanı nesnesi çağrısı [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) üye işlevi. Ayrıntılar için DAO Yardımı'ndaki "Version özelliği" konusuna bakın.  
  
 `m_lCollatingOrder`  
 Dize karşılaştırma ve sıralama metninde sıralama düzenini dizisini belirtir. Olası değerler şunlardır:  
  
- **dbSortGeneral** genel (İngilizce, Fransızca, Almanca, Portekizce, İtalyanca ve Modern İspanyolca) sıralama düzenini kullanın.  
  
- **dbSortArabic** Arapça sıralama düzenini kullanın.  
  
- **dbSortCyrillic** Rusça sıralama düzenini kullanın.  
  
- **dbSortCzech** Çekçe sıralama düzenini kullanın.  
  
- **dbSortDutch** Felemenkçe sıralama düzenini kullanın.  
  
- **dbSortGreek** Yunanca sıralama düzenini kullanın.  
  
- **dbSortHebrew** İbranice sıralama düzenini kullanın.  
  
- **dbSortHungarian** Macarca sıralama düzenini kullanın.  
  
- **dbSortIcelandic** İzlanda sıralama düzenini kullanın.  
  
- **dbSortNorwdan** Norveççe veya Danca sıralama düzenini kullanın.  
  
- **dbSortPDXIntl** Paradox Uluslararası sıralama düzenini kullanın.  
  
- **dbSortPDXNor** Paradox Norveççe veya Danca sıralama düzenini kullanın.  
  
- **dbSortPDXSwe** Paradox İsveççe veya Fince sıralama düzenini kullanın.  
  
- **dbSortPolish** Lehçe sıralama düzenini kullanın.  
  
- **dbSortSpanish** İspanyolca sıralama düzenini kullanın.  
  
- **dbSortSwedFin** İsveççe veya Fince sıralama düzenini kullanın.  
  
- **dbSortTurkish** Türkçe sıralama düzenini kullanın.  
  
- **dbSortUndefined** tanımlanmamış veya bilinmeyen sıralama düzeni.  
  
 Daha fazla bilgi için "Özelleştirme Windows kayıt defteri ayarları için veri erişim" DAO Yardım konusuna bakın.  
  
 *m_nQueryTimeout*  
 Microsoft Jet veritabanı altyapısı bir zaman aşımı hatası önce bekleyeceği saniye sayısını bir ODBC veritabanı sorgusu oluşur. Varsayılan zaman aşımı değeri 60 saniyedir. QueryTimeout 0 olarak ayarlandığında hiçbir zaman aşımı oluşur; Bu programın yanıt vermemesine neden olabilir. Bu özelliğin değerini doğrudan almak için veritabanı nesnesi çağrısı [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) üye işlevi. Ayrıntılar için DAO Yardımı'ndaki "QueryTimeout özelliği" konusuna bakın.  
  
 `m_strConnect`  
 Açık bir veritabanını kaynak hakkında bilgi sağlar. Bilgi hakkında bağlantı dizesi ve bu özelliğin değerini doğrudan alma hakkında daha fazla bilgi için bkz: [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) üye işlevi. Daha fazla bilgi için DAO Yardımı'nda "özellik Bağlan" konusuna bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir MFC nesne sınıfı, temel alınan bir DAO nesnesi veritabanıdır [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) üye işlevi.  
  
 Tarafından alınan bilgileri [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) üye işlevi depolanır bir `CDaoDatabaseInfo` yapısı. Çağrı `GetDatabaseInfo` için `CDaoWorkspace` nesne olan veritabanları koleksiyonunda veritabanı nesnesi depolanır. `CDaoDatabaseInfo`Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoDatabaseInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)
