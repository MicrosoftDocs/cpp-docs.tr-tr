---
title: Cdaoquerydefınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoQueryDefInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure [MFC]
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0b3e5834aa8b338448c2024603783cedb6f6cae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367236"
---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo Yapısı
`CDaoQueryDefInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan QueryDefs hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoQueryDefInfo  
{  
    CString m_strName;               // Primary  
    short m_nType;   // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    BOOL m_bUpdatable;               // Secondary  
    BOOL m_bReturnsRecords;          // Secondary  
    CString m_strSQL;                // All  
    CString m_strConnect;            // All  
    short m_nODBCTimeout;            // All  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `m_strName`  
 QueryDefs adlandıran. Daha fazla bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın. Çağrı [CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname) doğrudan bu özelliği alınamadı.  
  
 `m_nType`  
 QueryDefs işletimsel türünü belirten bir değer. Değerin aşağıdakilerden biri olabilir:  
  
- **dbQSelect** seçin — sorgu kayıtları seçer.  
  
- **dbQAction** eylem — sorgu taşır veya veriler değiştiğinde, ancak kayıt döndürmez.  
  
- **dbQCrosstab** çapraz — sorgu bir elektronik tablo benzeri biçiminde verileri döndürür.  
  
- **dbQDelete** silmek — sorgu belirtilen satır kümesini siler.  
  
- **dbQUpdate** güncelleştirme — sorgu bir kayıt kümesini değiştirir.  
  
- **dbQAppend** Append — sorguyu yeni kayıtlar tabloyu veya sorguyu sonuna ekler.  
  
- **dbQMakeTable** tablo oluşturma — sorgu kayıt kümesinden yeni bir tablo oluşturur.  
  
- **dbQDDL** veri tanımı — tablolar ya da kendi bölümleri yapısını sorgu etkiler.  
  
- **dbQSQLPassThrough** doğrudan — SQL deyimini doğrudan Ara işleme olmadan veritabanı arka ucu geçirilir.  
  
- **dbQSetOperation** birleşim — sorgu belirtilen tüm kayıtların iki veri içeren bir anlık görüntü türündeki kayıt kümesi oluşturur veya daha fazla yinelenen kayıtları tablolarla kaldırılamaz. Yinelemeleri dahil etmek için anahtar sözcüğünü ekleyin **tüm** querydef's SQL deyiminde.  
  
- **dbQSPTBulk** ile kullanılan **dbQSQLPassThrough** kayıtları döndürmeyen bir sorgu belirtmek için.  
  
> [!NOTE]
>  SQL doğrudan sorgu oluşturmak için ayarlamayın **dbQSQLPassThrough** sabit. QueryDefs oluşturmak ve Connect özelliğini ayarladığınızda, bu Microsoft Jet veritabanı altyapısı tarafından otomatik olarak ayarlanır.  
  
 Daha fazla bilgi için DAO Yardımı'ndaki "Type özelliği" konusuna bakın.  
  
 `m_dateCreated`  
 Tarih ve saat querydef oluşturuldu. Doğrudan querydef oluşturulduğu tarihi almak için arama [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) üye işlevini `CDaoTableDef` tabloyla ilişkili nesne. Açıklamalar aşağıda daha fazla bilgi için bkz. Ayrıca "Notes, LastUpdated özellikleri" DAO Yardım konusuna bakın.  
  
 `m_dateLastUpdated`  
 Tarih ve saat için querydef yapılan en son değişikliğin. Tablonun son güncelleştirilen tarih doğrudan almak için arama [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated) querydef üye işlevini. Açıklamalar aşağıda daha fazla bilgi için bkz. Ve DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
 `m_bUpdatable`  
 Değişiklikleri querydef nesneye yapılan olup olmadığını gösterir. Bu özellik ise **TRUE**querydef güncelleştirilebilir; Aksi takdirde, bu değildir. Güncelleştirilebilir querydef nesnesinin sorgu tanımı değiştirilebilir anlamına gelir. QueryDefs güncelleştirilebilir özellik kümesine **TRUE** elde edilen kayıt kümesi güncelleştirilebilir değilse bile sorgu tanımı, güncelleştirilebilir değilse. Bu özellik doğrudan almak için querydef's çağrısı [CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate) üye işlevi. Daha fazla bilgi için DAO Yardımı'ndaki "güncelleştirilebilir özellik" konusuna bakın.  
  
 *m_bReturnsRecords*  
 Dış veritabanı için SQL doğrudan sorgu kayıt döndürüp döndürmediğini gösterir. Bu özellik ise **doğru**, sorgu kayıtları döndürür. Bu özellik doğrudan almak için arama [CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords). Tüm SQL doğrudan sorguları dış veritabanlarına kayıtları döndürür. Örneğin, bir SQL **güncelleştirme** deyimi, bir SQL durumdayken kayıt dönmeden kayıtları güncelleştirmeleri **seçin** deyimi kayıtları döndürür. Daha fazla bilgi için DAO Yardımı'ndaki "ReturnsRecords özelliğini" konusuna bakın.  
  
 *m_strSQL*  
 Querydef nesnesi tarafından çalıştırılan sorguyu tanımlayan SQL deyimi. SQL özellik sorgu yürütülürken nasıl kayıtları, gruplandırılmış ve sıralı seçileceğini belirleyen SQL deyimi içerir. Dynaset veya anlık görüntü türü kayıt kümesi nesnesinde içermek üzere kayıtları seçmek için sorgu kullanabilirsiniz. Veri kayıtları dönmeden değiştirmek için Toplu sorguları da tanımlayabilirsiniz. Doğrudan querydef's çağırarak bu özelliğin değerini alabilir [GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql) üye işlevi.  
  
 `m_strConnect`  
 Geçiş sorguda kullanılan bir veritabanı kaynak hakkında bilgi sağlar. Bu bilgiler bir bağlantı dizesi biçimi alır. Daha fazla bilgi için ilgili bağlantı dizesi ve bu özelliğin değerini doğrudan alma hakkında daha fazla bilgi için bkz: [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) üye işlevi.  
  
 *m_nODBCTimeout*  
 Microsoft Jet veritabanı altyapısı bir zaman aşımı hatası önce bekleyeceği saniye sayısını bir ODBC veritabanı sorgusu oluşur. Microsoft SQL Server gibi bir ODBC veritabanı kullanılırken ağ trafiği veya ODBC sunucusunun kullanımını nedeniyle gecikmeler olabilir. Sonsuza kadar beklemek yerine, bir hata üretir önce Microsoft Jet altyapısı ne kadar bekleyeceğini belirtebilirsiniz. Varsayılan zaman aşımı değeri 60 saniyedir. Doğrudan querydef's çağırarak bu özelliğin değerini alabilir [GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout) üye işlevi. Daha fazla bilgi için DAO Yardımı'ndaki "ODBCTimeout özelliği" konusuna bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi querydef olan [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) üye işlevi sınıfında `CDaoDatabase`.  
  
 Tarafından alınan bilgileri [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo) üye işlevi depolanır bir `CDaoQueryDefInfo` yapısı. Çağrı `GetQueryDefInfo` veritabanı nesnesinin olan QueryDefs koleksiyonu QueryDefs depolanır. `CDaoQueryDefInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoQueryDefInfo` nesnesi. Sınıfı `CDaoDatabase` de doğrudan döndürülen özelliklerin tümünü erişmek için üye işlevleri sağlayan bir `CDaoQueryDefInfo` büyük olasılıkla nadiren çağırmanız gerekir böylece nesne `GetQueryDefInfo`.  
  
 QueryDefs alanları veya parametre koleksiyonu yeni bir alan veya parametre nesnesi ekleme, temel alınan veritabanı yeni nesne için belirtilen veri türü desteklemiyorsa özel durum oluşur.  
  
 Tarih ve saat ayarları üzerinde querydef oluşturulmuş veya son güncelleştirme bilgisayardan türetilir. Çok kullanıcılı bir ortamda kullanıcıların bu ayarları doğrudan kullanarak dosya sunucusu gelen almalısınız **net zaman** Notes ve LastUpdated özelliği ayarlarında Tutarsızlıklardan kaçınmak için komutu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)
