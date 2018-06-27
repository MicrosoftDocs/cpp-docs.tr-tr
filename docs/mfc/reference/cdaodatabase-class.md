---
title: CDaoDatabase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoDatabase
- AFXDAO/CDaoDatabase
- AFXDAO/CDaoDatabase::CDaoDatabase
- AFXDAO/CDaoDatabase::CanTransact
- AFXDAO/CDaoDatabase::CanUpdate
- AFXDAO/CDaoDatabase::Close
- AFXDAO/CDaoDatabase::Create
- AFXDAO/CDaoDatabase::CreateRelation
- AFXDAO/CDaoDatabase::DeleteQueryDef
- AFXDAO/CDaoDatabase::DeleteRelation
- AFXDAO/CDaoDatabase::DeleteTableDef
- AFXDAO/CDaoDatabase::Execute
- AFXDAO/CDaoDatabase::GetConnect
- AFXDAO/CDaoDatabase::GetName
- AFXDAO/CDaoDatabase::GetQueryDefCount
- AFXDAO/CDaoDatabase::GetQueryDefInfo
- AFXDAO/CDaoDatabase::GetQueryTimeout
- AFXDAO/CDaoDatabase::GetRecordsAffected
- AFXDAO/CDaoDatabase::GetRelationCount
- AFXDAO/CDaoDatabase::GetRelationInfo
- AFXDAO/CDaoDatabase::GetTableDefCount
- AFXDAO/CDaoDatabase::GetTableDefInfo
- AFXDAO/CDaoDatabase::GetVersion
- AFXDAO/CDaoDatabase::IsOpen
- AFXDAO/CDaoDatabase::Open
- AFXDAO/CDaoDatabase::SetQueryTimeout
- AFXDAO/CDaoDatabase::m_pDAODatabase
- AFXDAO/CDaoDatabase::m_pWorkspace
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabase [MFC], CDaoDatabase
- CDaoDatabase [MFC], CanTransact
- CDaoDatabase [MFC], CanUpdate
- CDaoDatabase [MFC], Close
- CDaoDatabase [MFC], Create
- CDaoDatabase [MFC], CreateRelation
- CDaoDatabase [MFC], DeleteQueryDef
- CDaoDatabase [MFC], DeleteRelation
- CDaoDatabase [MFC], DeleteTableDef
- CDaoDatabase [MFC], Execute
- CDaoDatabase [MFC], GetConnect
- CDaoDatabase [MFC], GetName
- CDaoDatabase [MFC], GetQueryDefCount
- CDaoDatabase [MFC], GetQueryDefInfo
- CDaoDatabase [MFC], GetQueryTimeout
- CDaoDatabase [MFC], GetRecordsAffected
- CDaoDatabase [MFC], GetRelationCount
- CDaoDatabase [MFC], GetRelationInfo
- CDaoDatabase [MFC], GetTableDefCount
- CDaoDatabase [MFC], GetTableDefInfo
- CDaoDatabase [MFC], GetVersion
- CDaoDatabase [MFC], IsOpen
- CDaoDatabase [MFC], Open
- CDaoDatabase [MFC], SetQueryTimeout
- CDaoDatabase [MFC], m_pDAODatabase
- CDaoDatabase [MFC], m_pWorkspace
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30e6ac1f1ed780415e7f0a10d82175c2b287fb29
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953902"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase sınıfı
Verileri çalışabilir veritabanına bağlantıyı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDaoDatabase : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|Oluşturan bir `CDaoDatabase` nesnesi. Çağrı `Open` nesne bir veritabanına bağlanmak için.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](#cantransact)|Veritabanı işlemleri destekliyorsa sıfır olmayan bir değer döndürür.|  
|[CDaoDatabase::CanUpdate](#canupdate)|Döndürür sıfır olmayan IF `CDaoDatabase` nesne güncelleştirilebilir değil (salt okunur değil).|  
|[CDaoDatabase::Close](#close)|Veritabanı bağlantıyı kapatır.|  
|[CDaoDatabase::Create](#create)|DAO veritabanı nesnesini oluşturur ve başlatır `CDaoDatabase` nesnesi.|  
|[CDaoDatabase::CreateRelation](#createrelation)|Yeni bir ilişkisi tablolar arasında veritabanında tanımlar.|  
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|Veritabanının QueryDefs koleksiyonu kaydedilmiş QueryDefs siler.|  
|[CDaoDatabase::DeleteRelation](#deleterelation)|Veritabanındaki tablolar arasında var olan bir ilişki siler.|  
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|Veritabanındaki bir tablo tanımını siler. Bu, gerçek tablo ve tüm verilerini siler.|  
|[CDaoDatabase::Execute](#execute)|Bir eylem sorgusunu çalıştırır. Çağırma `Execute` için sonuçları döndüren bir sorgu bir özel durum oluşturur.|  
|[CDaoDatabase::GetConnect](#getconnect)|Bağlanmak için kullanılan bağlantı dizesi döndürür `CDaoDatabase` bir veritabanı nesnesi. ODBC için kullanılır.|  
|[CDaoDatabase::GetName](#getname)|Veritabanının adını şu anda kullanımda döndürür.|  
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|Veritabanı için tanımlı olan sorgu sayısını döndürür.|  
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|Veritabanında tanımlanan belirtilen bir sorgu hakkında bilgi verir.|  
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|Operations sorgusu hangi veritabanı saniye sayısını döndürür zaman aşımına uğrar. Sonraki tüm etkiler açın, yeni Ekle, Güncelleştir ve işlemler ve ODBC veri kaynakları üzerinde başka işlemler (yalnızca) gibi Düzenle `Execute` çağrıları.|  
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|Düzenleme veya ekleme işlemi kayıt sayısı tarafından son güncelleştirme, etkilenen verir veya bir çağrı tarafından `Execute`.|  
|[CDaoDatabase::GetRelationCount](#getrelationcount)|Veritabanındaki tablolar arasındaki tanımlanan ilişkiler sayısını döndürür.|  
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|Veritabanındaki tablolar arasındaki tanımlanan belirtilen bir ilişki hakkında bilgi verir.|  
|[CDaoTableDefInfo](#gettabledefcount)|Veritabanında tanımlanan tablo sayısını döndürür.|  
|[CDaoDatabase::GetTableDefCount](#gettabledefinfo)|Belirtilen bir tablodaki hakkındaki bilgileri veritabanında döndürür.|  
|[CDaoDatabase::GetVersion](#getversion)|Veritabanıyla ilişkili veritabanı altyapısı sürümünü döndürür.|  
|[CDaoDatabase::IsOpen](#isopen)|Döndürür sıfır olmayan IF `CDaoDatabase` nesne şu anda bir veritabanına bağlı.|  
|[CDaoDatabase::Open](#open)|Bir veritabanına bir bağlantı kurar.|  
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|İşlemlerde (yalnızca ODBC veri kaynakları için) sorgusu hangi veritabanı saniye sayısını ayarlar zaman aşımına uğrar. Sonraki tüm etkiler açın, yeni Ekle, güncelleştirme ve silme işlemleri.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|DAO veritabanı nesnesini bir işaretçi.|  
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|Bir işaretçi [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) veritabanını içeren ve kendi işlem alanını tanımlayan bir nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Desteklenen veritabanı biçimleri hakkında daha fazla bilgi için bkz: [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) üye işlevi. Bir veya daha fazla olabilir `CDaoDatabase` "tarafından temsil edilen bir belirli çalışma alanında," nesneleri aynı anda etkin bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesi. Çalışma alanı veritabanı koleksiyonu adlı açık veritabanı nesnelerinin bir koleksiyonu tutar.  
  
> [!NOTE]
>  MFC DAO veritabanı sınıfları ODBC tabanlı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. Sınıf `CDaoDatabase` ODBC sınıfı için benzer bir arabirim sağlayan [CDatabase](../../mfc/reference/cdatabase-class.md). Ana fark `CDatabase` DBMS bu DBMS için açık veritabanı bağlantısı (ODBC) ve ODBC sürücüsü erişir. `CDaoDatabase` Veri aracılığıyla bir veri erişim nesnesi (Microsoft Jet veritabanı altyapısını temel DAO) erişir. Genel olarak, üzerinde DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıfları daha yetenekli; DAO tabanlı sınıflar kendi veritabanı altyapısı aracılığıyla ODBC sürücüleri üzerinden de dahil olmak üzere, verilere erişebilir. DAO tabanlı sınıflar da tabloları sınıfları aracılığıyla doğrudan çağırmak zorunda kalmadan ekleme gibi veri tanımlama dili (DDL) işlemleri desteklemez.  
  
## <a name="usage"></a>Kullanım  
 Kayıt kümesi nesneleri oluşturduğunuz zaman, veritabanı nesnelerini dolaylı olarak oluşturabilirsiniz. Ancak veritabanı nesneleri açıkça oluşturabilirsiniz. Var olan bir veritabanı açıkça kullanmak için `CDaoDatabase`, aşağıdakilerden birini yapın:  
  
-   Oluşturmak bir `CDaoDatabase` nesne, bir işaretçi bir açık olarak geçirme [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesi.  
  
-   Ya da oluşturmak bir `CDaoDatabase` (MFC geçici çalışma nesnesi oluşturur) çalışma belirtmeden nesnesi.  
  
 Yeni bir Microsoft Jet oluşturmak için (. MDB) veritabanı oluşturmak bir `CDaoDatabase` nesne ve çağrı kendi [oluşturma](#create) üye işlevi. Yapmak *değil* çağrısı `Open` sonra `Create`.  
  
 Varolan bir veritabanını açmak için oluşturmak bir `CDaoDatabase` nesne ve çağrı kendi [açmak](#open) üye işlevi.  
  
 Bu teknikler hiçbirini DAO veritabanı nesnesi Workspace'in veritabanları koleksiyonuna ekler ve verileri bir bağlantı açar. Ardından oluşturmak zaman [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), veya [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) bağlı veritabanında işletim için nesneleri geçirmek oluşturucuları bu nesneler için bir İşaretçi, `CDaoDatabase` nesnesi. Bağlantı kullanmayı bitirdiğinizde, çağrı [Kapat](#close) üye işlev ve destroy `CDaoDatabase` nesnesi. `Close` daha önce kapatılmamış kümeleri kapatır.  
  
## <a name="transactions"></a>İşlemler  
 Veritabanı işlem çalışma düzeyinde sağlanan — bkz [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), ve [geri alma](../../mfc/reference/cdaoworkspace-class.md#rollback) sınıfının üye işlevleri `CDaoWorkspace` .  
  
## <a name="odbc-connections"></a>ODBC Bağlantıları  
 ODBC veri kaynakları ile çalışmak için önerilen yöntem Microsoft Jet için dış tabloları eklemektir (. MDB) veritabanı.  
  
## <a name="collections"></a>Koleksiyonlar  
 Her veritabanı kendi koleksiyonları tabledef, querydef, kayıt kümesi ve ilişkisi nesneleri tutar. Sınıf `CDaoDatabase` bu nesneleri işlemek için üye işlevleri sağlar.  
  
> [!NOTE]
>  Nesneleri DAO'da, MFC veritabanı nesnesi değil depolanır. MFC sınıfları tabledef, querydef ve kayıt kümesi nesneleri için kullanılabilir ancak ilişkisi nesneleri sağlar.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
##  <a name="cantransact"></a>  CDaoDatabase::CanTransact  
 Veritabanı işlemleri izin verip vermediğini belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veritabanı işlemleri destekliyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlemler veritabanının çalışma alanında yönetilir.  
  
##  <a name="canupdate"></a>  CDaoDatabase::CanUpdate  
 Belirlemek için bu üye işlevini çağırın olup olmadığını `CDaoDatabase` nesne güncelleştirmeler sağlar.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CDaoDatabase` nesne güncelleştirmeler sağlar; Aksi halde 0 ya da bu gösteren geçirilen **TRUE** içinde *bReadOnly* açıldığında, `CDaoDatabase` nesne veya veritabanı olduğunu salt okunur. Bkz: [açık](#open) üye işlevi.  
  
### <a name="remarks"></a>Açıklamalar  
 Veritabanı Güncelleştirilebilirlik hakkında daha fazla bilgi için DAO Yardımı'ndaki "güncelleştirilebilir özellik" konusuna bakın.  
  
##  <a name="cdaodatabase"></a>  CDaoDatabase::CDaoDatabase  
 Oluşturan bir `CDaoDatabase` nesnesi.  
  
```  
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWorkspace*  
 Bir işaretçi `CDaoWorkspace` yeni veritabanı nesnesini içeren nesne. Varsayılan değerini kabul ederseniz **NULL**, geçici bir oluşturucusu oluşturur `CDaoWorkspace` varsayılan DAO çalışma kullanan nesnesi. Çalışma nesnesine bir işaretçi alma [m_pWorkspace](#m_pworkspace) veri üyesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir Microsoft Jet oluşturuyorsanız, sonra nesnesi oluşturma (. MDB) veritabanı, nesnenin çağrısı [oluşturma](#create) üye işlevi. Bunun yerine, olması durumunda nesnenin çağrısı var olan bir veritabanını açarken [açık](#open) üye işlevi.  
  
 Nesnesi ile işiniz bittiğinde, çağırmalıdır kendi [Kapat](#close) üye işlev ve ardından destroy `CDaoDatabase` nesnesi.  
  
 Katıştırmak kullanışlı bulabileceğiniz `CDaoDatabase` belge sınıfınızda nesnesi.  
  
> [!NOTE]
>  A `CDaoDatabase` nesnesi de oluşturulur örtük olarak açarsanız bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) var olan bir işaretçi geçirmeden nesne `CDaoDatabase` nesne. Kayıt kümesi nesnesi kapattığınızda, bu veritabanı nesnesi kapalı.  
  
##  <a name="close"></a>  CDaoDatabase::Close  
 Bir veritabanı bağlantısını kesmek ve herhangi bir açık kayıt kümeleri, tabledefs ve veritabanıyla ilişkili querydefs kapatmak için bu üye işlevini çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevini çağırmadan önce bu nesneleri kendiniz kapatmak iyi bir uygulamadır. Kapatma bir `CDaoDatabase` nesne koleksiyonundan veritabanları ilişkili onu kaldırır [çalışma](../../mfc/reference/cdaoworkspace-class.md). Çünkü `Close` yok `CDaoDatabase` nesne yeniden nesne aynı veya farklı bir veritabanının açarak.  
  
> [!CAUTION]
>  Çağrı [güncelleştirme](../../mfc/reference/cdaorecordset-class.md#update) (düzenlemeler varsa) üye işlevini ve `Close` bir veritabanı kapatmadan önce tüm açık kayıt nesnelerde üye işlevi. Bildiren bir işlev çıkarsanız [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) veya `CDaoDatabase` nesneleri yığında veritabanı kapalı, kaydedilmeyen tüm değişiklikler kaybolur, tüm bekleyen işlemler geri alınır ve verilerinize bekleyen düzenlemeler kaybolur.  
  
> [!CAUTION]
>  Herhangi bir kayıt kümesi nesne açıkken bir veritabanı nesnesi kapatmaya deneyin ya da bu belirli çalışma alanına ait tüm veritabanı nesnelerini açıkken workspace nesnesini kapatmaya çalışırsanız, bu kayıt kümesi nesneleri kapatılacak ve bekleyen tüm güncelleştirmeler veya düzenlemeler olacaktır geri alındı. Bir çalışma alanı nesnesi kendisine ait tüm veritabanı nesnelerini açıkken kapatmayı denerseniz, işlemi kapatılan kapatılmamış kayıt kümesi nesneleri neden olabilir, belirli çalışma nesnesine ait tüm veritabanı nesnelerini kapatır. Veritabanı nesnesi kapatmazsanız MFC hata ayıklama derlemelerinde onaylama hatası raporlar.  
  
 Veritabanı nesnesinin bir işlev kapsamı dışında tanımlanır ve kapatmadan işlevi çıkmak, veritabanı nesnesi açıkça kapatılana kadar açık kalır veya içinde tanımlandığı modülü kapsamının dışında.  
  
##  <a name="create"></a>  CDaoDatabase::Create  
 Yeni bir Microsoft Jet oluşturmak için (. MDB) veritabanı, siz oluşturduktan sonra bu üye işlevini çağırın bir `CDaoDatabase` nesnesi.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int dwOptions = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszName*  
 Oluşturmakta olduğunuz veritabanı dosyası adı bir dize ifadesi. Bu dosyanın tam yolunu ve dosya adı aşağıdaki gibi olabilir "C:\\\MYDB. MDB". Bir ad girmeniz gerekir. Bir dosya adı uzantısı belirtmezseniz. MDB eklenir. Ağınız Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, aynı zamanda bir ağ yolu gibi belirtebilirsiniz "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB". Yalnızca Microsoft Jet (. MDB) veritabanı dosyaları, bu üye işlevi kullanılarak oluşturulabilir. (Çift ters eğik çizgi, dize değişmez değerleri gereklidir, çünkü "\\" C++ kaçış karakteri.)  
  
 *lpszLocale*  
 Veritabanını oluşturmak için harmanlama sırası belirtmek için kullanılan bir dize ifadesi. Varsayılan değer **dbLangGeneral**. Olası değerler şunlardır:  
  
- **dbLangGeneral** İngilizce, Almanca, Fransızca, Portekizce, İtalyanca ve Modern İspanyolca  
  
- **dbLangArabic** Arapça  
  
- **dbLangCyrillic** Rusça  
  
- **dbLangCzech** Çekçe  
  
- **dbLangDutch** Hollanda dili  
  
- **dbLangGreek** Yunanca  
  
- **dbLangHebrew** İbranice  
  
- **dbLangHungarian** Macarca  
  
- **dbLangIcelandic** İzlanda  
  
- **dbLangNordic** Kuzey Dilleri (yalnızca Microsoft Jet veritabanı altyapısı sürüm 1.0)  
  
- **dbLangNorwdan** Norveççe ve Danca  
  
- **dbLangPolish** Lehçe  
  
- **dbLangSpanish** geleneksel İspanyolca  
  
- **dbLangSwedfin** İsveççe ve Fince  
  
- **dbLangTurkish** Türkçe  
  
 *dwOptions*  
 Bir veya daha fazla seçenek belirten tamsayı. Olası değerler şunlardır:  
  
- **dbEncrypt** şifrelenmiş bir veritabanı oluşturun.  
  
- **dbVersion10** Microsoft Jet veritabanı sürüm 1.0 bir veritabanı oluşturun.  
  
- **dbVersion11** Microsoft Jet veritabanı sürüm 1.1 bir veritabanı oluşturun.  
  
- **dbVersion20** Microsoft Jet veritabanı sürüm 2.0 bir veritabanı oluşturun.  
  
- **dbVersion30** Microsoft Jet veritabanı sürüm 3.0 bir veritabanı oluşturun.  
  
 Şifreleme sabiti atlarsanız, şifrelenmemiş bir veritabanı oluşturulur. Yalnızca bir sürümü sabiti belirtebilirsiniz. Sürüm sabiti atlarsanız, Microsoft Jet veritabanı sürüm 3.0 kullanan bir veritabanı oluşturulur.  
  
> [!CAUTION]
>  Bir veritabanı şifrelenmezse, doğrudan veritabanı oluşturduğunu ikili disk dosyası okumak için kullanıcı/parola güvenlik uygulamak olsa bile, mümkündür.  
  
### <a name="remarks"></a>Açıklamalar  
 `Create` Veritabanı dosyası ve DAO veritabanı nesnesini oluşturur ve C++ nesnesini başlatır. Nesnenin ilişkili Workspace'in veritabanları koleksiyonuna eklenir. Veritabanı nesne açık bir durumda; çağırmayın `Open*` sonra `Create`.  
  
> [!NOTE]
>  İle `Create`, yalnızca Microsoft Jet oluşturabilirsiniz (. MDB) veritabanları. ISAM veritabanları veya ODBC veritabanı oluşturulamıyor.  
  
##  <a name="createrelation"></a>  CDaoDatabase::CreateRelation  
 Bir veya daha fazla veritabanındaki birincil bir tablodaki ve bir veya daha fazla alanları yabancı tablosundaki (başka bir veritabanı tablosunda) arasında bir ilişki oluşturmak için bu üye işlevini çağırın.  
  
```  
void CreateRelation(
    LPCTSTR lpszName,  
    LPCTSTR lpszTable,  
    LPCTSTR lpszForeignTable,  
    long lAttributes,  
    LPCTSTR lpszField,  
    LPCTSTR lpszForeignField);  
  
void CreateRelation(CDaoRelationInfo& relinfo);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszName*  
 İlişki nesnesinin benzersiz adı. Adı bir harf ile başlamalı ve en çok 40 karakter içerebilir. Sayı içerebilir ve alt çizgi karakterleri ancak noktalama veya boşluk içeremez.  
  
 *lpszTable*  
 İlişkinin birincil tablo adı. Tablo mevcut değilse, MFC türünde bir özel durum atar [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 *lpszForeignTable*  
 İlişki yabancı tablo adı. Tablo mevcut değilse, MFC türünde bir özel durum atar `CDaoException`.  
  
 *lAttributes*  
 İlişki türü hakkında bilgi içeren bir uzun değeri. Bu değer, başka şeylerin bilgi tutarlılığı zorlamak için kullanabilirsiniz. Bit düzeyinde OR işleci kullanabilirsiniz ( **&#124;**) (birleşimi mantıklı sürece) aşağıdaki değerlerden herhangi birini birleştirmek için:  
  
- **dbRelationUnique** birebir ilişki.  
  
- **dbRelationDontEforce'a** ilişkisi değil (hiçbir başvuru bütünlüğü) uygulanmaz.  
  
- **dbRelationInherited** ilişkisi, iki bağlı tabloları içeren noncurrent bir veritabanında yok.  
  
- **dbRelationUpdateCascade** güncelleştirmeleri basamaklı (basamaklar hakkında daha fazla bilgi için açıklamalar bakın).  
  
- **dbRelationDeleteCascade** silme işlemleri basamaklı.  
  
 *lpszField*  
 Birincil tablo bir alanın adını içeren null ile sonlandırılmış bir dize için bir işaretçi (tarafından adlı *lpszTable*).  
  
 *lpszForeignField*  
 Yabancı tablo bir alanın adını içeren null ile sonlandırılmış bir dize için bir işaretçi (tarafından adlı *lpszForeignTable*).  
  
 *relinfo*  
 Bir başvuru bir [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) oluşturmak istiyorsanız ilişki hakkında bilgi içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlişki bir sorgu veya dış veritabanı bağlı bir tablodan ilgili olamaz.  
  
 İlişki her iki tablonun bir alana gerektirdiğinde işlevi ilk sürümünü kullanın. Birden çok alan ilişkisi içerir ikinci sürümü kullanın. En fazla bir ilişkisi alanlarında 14 sayısıdır.  
  
 Bu eylem bir DAO ilişkisi nesnesini oluşturur, ancak MFC'nin kapsülleme ilişkisi nesnelerin sınıfı içinde yer aldığından bu bir MFC uygulaması ayrıntı `CDaoDatabase`. MFC sınıf ilişkileri için sağlamıyor.  
  
 İlişki cascade işlemlerini etkinleştirmek için nesnenin öznitelikleri ayarlarsanız, veritabanı altyapısı otomatik olarak güncelleştirir veya ilgili birincil anahtar tablolarda değişiklik yapıldığında, bir veya daha fazla diğer tablolardaki kayıtlarını siler.  
  
 Örneğin, Müşteriler tablosu ve Siparişler tablosu arasında bir cascade delete ilişki kurmak varsayalım. Müşteriler tablosundan kayıtları sildiğinizde, o müşteri ile ilgili Siparişler tablosundaki kayıtları da silinir. Ayrıca, Siparişler tablosundaki ve diğer tablolar arasındaki cascade delete ilişkileri kurmak, Müşteriler tablosundan kayıtları sildiğinizde bu tablolardan kayıtları otomatik olarak silinir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "CreateRelation yöntemi" konusuna bakın.  
  
##  <a name="deletequerydef"></a>  CDaoDatabase::DeleteQueryDef  
 Belirtilen querydef silmek için bu üye işlevini çağırın — sorgu kaydedilmiş — gelen `CDaoDatabase` nesnenin QueryDefs koleksiyonu.  
  
```  
void DeleteQueryDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszName*  
 Silmek için kayıtlı sorgunun adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha sonra bu sorguyu artık veritabanında tanımlanır.  
  
 Querydef nesneleri oluşturma hakkında daha fazla bilgi için bkz [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). QueryDefs belirli bir ile ilişkili hale `CDaoDatabase` nesnesini oluştururken, `CDaoQueryDef` nesnesi, veritabanı nesnesine bir işaretçi geçirme.  
  
##  <a name="deleterelation"></a>  CDaoDatabase::DeleteRelation  
 Varolan bir ilişkisi veritabanı nesnesi ilişkileri koleksiyonundan silmek için bu üye işlevini çağırın.  
  
```  
void DeleteRelation(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszName*  
 Silmek için ilişki adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha sonra ilişkisi artık yok.  
  
 İlgili bilgi için "Delete yöntemini" DAO Yardım konusuna bakın.  
  
##  <a name="deletetabledef"></a>  CDaoDatabase::DeleteTableDef  
 Belirtilen tablo ve tüm alt verilerini silmek için bu üye işlevini çağırın `CDaoDatabase` nesnenin TableDefs koleksiyonu.  
  
```  
void DeleteTableDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszName*  
 Silinecek tabledef adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha sonra bu tabloyu artık veritabanında tanımlanır.  
  
> [!NOTE]
>  Sistem tabloları silmemeniz çok dikkatli olun.  
  
 Tabledef nesneleri oluşturma hakkında daha fazla bilgi için bkz [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Tabledef nesnesi ile belirli bir ilişkili hale `CDaoDatabase` nesnesini oluştururken, `CDaoTableDef` nesnesi, veritabanı nesnesine bir işaretçi geçirme.  
  
 İlgili bilgi için "Delete yöntemini" DAO Yardım konusuna bakın.  
  
##  <a name="execute"></a>  CDaoDatabase::Execute  
 Eylem sorgusu çalıştırmak veya veritabanı bir SQL deyimi yürütmek için bu üye işlevini çağırın.  
  
```  
void Execute(
    LPCTSTR lpszSQL,  
    int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszSQL*  
 İşaretçi yürütmek için geçerli bir SQL komut içeren null ile sonlandırılmış bir dize.  
  
 *nOptions*  
 Sorgu bütünlüğünü ilgili seçenekler belirten bir tamsayı. Bit düzeyinde OR işleci kullanabilirsiniz ( **&#124;**) aşağıdaki sabitlerden herhangi birisi birleştirmek için (birleşimi mantıklı sağlanan — Örneğin, size değil birleştirmek **dbInconsistent** ile**dbConsistent**):  
  
- **dbDenyWrite** diğer kullanıcılara reddetme yazma izni.  
  
- **dbInconsistent** (varsayılan) tutarsız güncelleştirmeler.  
  
- **dbConsistent** tutarlı güncelleştirmeler.  
  
- **dbSQLPassThrough** SQL doğrudan. İşlenmek üzere bir ODBC veri kaynağı için geçirilecek SQL deyimini neden olur.  
  
- **dbFailOnError** bir hata oluşursa güncelleştirmeleri geri alma.  
  
- **dbSeeChanges** başka bir kullanıcı düzenlemekte verileri değiştirme, bir çalışma zamanı hatası oluşturur.  
  
> [!NOTE]
>  Her iki **dbInconsistent** ve **dbConsistent** dahil edilen veya hiçbiri dahil değilse varsayılan sonucudur. Bu sabitleri açıklaması için DAO Yardımı'ndaki "yöntemi Çalıştır" konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 `Execute` Yalnızca eylem sorguları veya sonuçları döndürmeyen SQL doğrudan sorguları için çalışır. Kayıtları döndürmesi seçim sorguları için çalışmaz.  
  
 Tanım ve eylem sorguları hakkında bilgi için "Eylem sorgu" ve "Yürütme yönteminde" DAO Yardım konularına bakın.  
  
> [!TIP]
>  Verilen sözdizimsel olarak doğru bir SQL deyimi ve uygun izinleri `Execute` üye işlevi değil başarısız olur bile tek bir satır değiştirilmiş veya silinmiş değilse. Bu nedenle, her zaman kullanın **dbFailOnError** seçeneğini kullanırken `Execute` bir güncelleştirme veya silme sorgusu üye işlevi. Bu seçenek türünde bir özel durum throw MFC neden [CDaoException](../../mfc/reference/cdaoexception-class.md) ve etkilenen kayıtların hiçbirini kilitli ve güncelleştirilemiyor veya silinen, tüm başarılı değişiklikleri geri alır. Her zaman çağırabilirsiniz Not `GetRecordsAffected` kaç kayıt etkilendi görmek için.  
  
 Çağrı [GetRecordsAffected](#getrecordsaffected) üye işlevi tarafından en son etkilenen kayıtların sayısı belirlemek için veritabanı nesnesinin `Execute` çağırın. Örneğin, `GetRecordsAffected` silinmiş, güncelleştirilmiş veya eylem sorgusu yürütürken eklenen kayıt sayısı hakkında bilgi döndürür. Döndürülen sayı cascade güncelleştirir veya sildiğinde ilgili tablolarda değişiklikleri etkindir yansıtmaz.  
  
 `Execute` bir kayıt kümesi döndürmüyor. Kullanarak `Execute` türünde bir özel durum throw MFC kayıtları seçen bir sorgu neden `CDaoException`. (Var. hiçbir `ExecuteSQL` üye işlevine benzer `CDatabase::ExecuteSQL`.)  
  
##  <a name="getconnect"></a>  CDaoDatabase::GetConnect  
 Bağlanmak için kullanılan bağlantı dizesini almak için bu üye işlevini çağırın `CDaoDatabase` bir ODBC veya ISAM veritabanına nesne.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlantı dizesi [açık](#open) boyunca bir ODBC veri kaynağında başarıyla; tersi durumda, boş bir dize. Microsoft Jet için (. MDB) veritabanı dize boşsa her zaman ile kullanılmak üzere ayarlamadıysanız **dbSQLPassThrough** seçeneği ile kullanılan [yürütme](#execute) üye işlevi veya bir kayıt açmayı kullanılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Dize kaynağı doğrudan Sorguda kullanılan bir veritabanı veya açık bir veritabanı hakkında bilgi sağlar. Bağlantı dizesi bir veritabanı türü belirticisi ve noktalı virgülle ayırarak sıfır veya daha fazla parametre kümesinden oluşur.  
  
> [!NOTE]
>  Aracılığıyla ODBC veri kaynağına bağlanmak için MFC DAO sınıflarını kullanarak, ekli bir tablo bağlanma değerinden daha az verimlidir.  
  
> [!NOTE]
>  Bağlantı dizesi ODBC ve belirli ISAM sürücüleri gerektiği gibi ek bilgileri geçirmek için kullanılır. İçin kullanılmaz. MDB veritabanları. Microsoft Jet veritabanı temel tablolar için bağlantı dizesi boş bir dizedir (""), bir SQL doğrudan sorgu için dönüş değeri altında yukarıda açıklandığı gibi kullandığınızda dışında.  
  
 Bkz: [açık](#open) üye işlevi için bağlantı dizesini nasıl oluşturulduğunu açıklaması. Bağlantı dizesini ayarlayın sonra `Open` çağrı, daha sonra bu tür, yol, kullanıcı kimliği, parola veya ODBC veri kaynağı veritabanının belirlemek için ayarını denetleyin için kullanabilirsiniz.  
  
##  <a name="getname"></a>  CDaoDatabase::GetName  
 Varolan bir veritabanı dosyası adı şu anda açık veritabanının adını veya kayıtlı bir ODBC veri kaynağı adını almak için bu üye işlevini çağırın.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tam yol ve dosya adı veritabanının başarılı olursa; Aksi durumda, boş bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Ağınızı Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, bir ağ yolu da belirtebilirsiniz; Örneğin, "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Çift ters eğik çizgi, dize değişmez değerleri gereklidir, çünkü "\\" C++ kaçış karakteri.)  
  
 Örneğin, bu ad, bir başlık görüntülemek isteyebilirsiniz. Adı alınırken bir hata oluşursa, MFC türünde bir özel durum atar [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
> [!NOTE]
>  Dış veritabanlarını erişilebilir olduğunda, daha iyi performans için bir Microsoft Jet veritabanına dış veritabanı tablolarını ekleme öneririz (. MDB) yerine doğrudan veri kaynağına bağlanma.  
  
 Veritabanı türü, dosya veya yol noktaları için aşağıdaki gibi dizin tarafından belirtilir:  
  
|PathName noktalarına...|Veritabanı türü|  
|--------------------------|-------------------|  
|. MDB dosyası|Microsoft Jet veritabanı (Microsoft Access)|  
|İçeren dizini. DBF dosyaları|dBASE veritabanı|  
|İçeren dizini. XLS dosyası|Microsoft Excel veritabanı|  
|İçeren dizini. PDX dosyaları|Paradox veritabanı|  
|Uygun şekilde biçimlendirilmiş metin veritabanı dosyaları içeren dizini|Metin biçiminde veritabanı|  
  
 SQL Server ve Oracle gibi ODBC veritabanları için veritabanı bağlantı dizesi tarafından ODBC kayıtlı bir veri kaynağı adı (DSN) tanımlar.  
  
##  <a name="getquerydefcount"></a>  CDaoDatabase::GetQueryDefCount  
 Veritabanının QueryDefs koleksiyonu içinde tanımlı olan sorgu sayısını almak için bu üye işlevini çağırın.  
  
```  
short GetQueryDefCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veritabanında tanımlanan sorgu sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetQueryDefCount` QueryDefs koleksiyonu içinde tüm querydefs döngü gerektiğinde kullanışlı olur. Bir koleksiyondaki belirli bir sorgu hakkında bilgi edinmek için bkz: [GetQueryDefInfo](#getquerydefinfo).  
  
##  <a name="getquerydefinfo"></a>  CDaoDatabase::GetQueryDefInfo  
 Çeşitli veritabanında tanımlı bir sorgu hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
```  
void GetQueryDefInfo(
    int nIndex,  
    CDaoQueryDefInfo& querydefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetQueryDefInfo(
    LPCTSTR lpszName,  
    CDaoQueryDefInfo& querydefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Önceden tanımlanmış sorgu veritabanının QueryDefs koleksiyondaki, dizine göre arama dizini.  
  
 *querydefinfo*  
 Bir başvuru bir [Cdaoquerydefınfo](../../mfc/reference/cdaoquerydefinfo-structure.md) istenen bilgileri döndürür nesnesi.  
  
 *dwInfoOptions*  
 Hangi bilgilerini almak için kayıt kümesi belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi hakkında kayıt döndürecek şekilde neden birlikte aşağıda listelenmiştir:  
  
- `AFX_DAO_PRIMARY_INFO` (Varsayılan) Adı, türü  
  
- `AFX_DAO_SECONDARY_INFO` Birincil bilgileri artı: oluşturma tarihi, son güncelleştirme tarihi, döndürür kayıtları, güncelleştirilebilir  
  
- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgi artı: SQL, Connect ODBCTimeout  
  
 *lpszName*  
 Ada göre arama için veritabanında tanımlı bir sorgunun adını içeren dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Veritabanının QueryDefs koleksiyonu dizinde veya sorgunun adını göre bir sorgu seçebilmeniz için işlevi iki sürümü sağlanır.  
  
 Döndürülen bilgi açıklaması *querydefinfo*, bkz: [Cdaoquerydefınfo](../../mfc/reference/cdaoquerydefinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor *dwInfoOptions*. Bir düzey bilgilerin isterse bilgilerini de önceki tüm düzeylerini alın.  
  
##  <a name="getquerytimeout"></a>  CDaoDatabase::GetQueryTimeout  
 Sonraki işlemlerde bağlı veritabanı aşımına önce izin verilen saniye sayısı almak için bu üye işlevini çağırın.  
  
```  
short GetQueryTimeout();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saniye cinsinden zaman aşımı değeri içeren bir kısa tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işlem ağ erişim sorunları, aşırı sorgu işleme süresini ve benzeri nedeniyle zaman. Ayarı etkinken, tüm açık etkiler, yeni ekleme, güncelleştirme ve silme işlemleri bununla ilişkili tüm kayıt kümeleri üzerinde `CDaoDatabase` nesnesi. Çağırarak geçerli zaman aşımı ayarını değiştirebilirsiniz [SetQueryTimeout](#setquerytimeout). Bir kayıt kümesi için sorgu zaman aşımı değeri açıldıktan sonra değiştirme kayıt değeri değiştirmez. Örneğin, sonraki [taşıma](../../mfc/reference/cdaorecordset-class.md#move) işlemleri, yeni değer kullanmayın. Varsayılan değer, başlangıçta veritabanı altyapısı başlatıldığında ayarlanır.  
  
 Sorgu zaman aşımı için varsayılan değer Windows kayıt defterinden alınır. Hiçbir kayıt defteri ayarı ise, varsayılan değer 60 saniyedir. Tüm veritabanları sorgu zaman aşımı değerini ayarlama özelliği destekler. Bir sorgu zaman aşımı değeri 0 olarak ayarlarsanız, hiçbir zaman aşımı oluşur; ve veritabanı ile iletişim yanıt vermeyebilir. Bu davranış geliştirme sırasında yararlı olabilir. Çağrı başarısız olursa, MFC türünde bir özel durum atar [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 İlgili bilgi için DAO Yardımı'ndaki "QueryTimeout özelliği" konusuna bakın.  
  
##  <a name="getrecordsaffected"></a>  CDaoDatabase::GetRecordsAffected  
 En son çağrı tarafından etkilenen kayıtların sayısı belirlemek için bu üye işlevini çağırın [yürütme](#execute) üye işlevi.  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkilenen kayıtların sayısı içeren uzun tamsayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen değer silinen, güncellenen veya çalıştırmalarına eylem sorgusu tarafından eklenen kayıt sayısını içeren `Execute`. Döndürülen sayı cascade güncelleştirir veya sildiğinde ilgili tablolarda değişiklikleri etkindir yansıtmaz.  
  
 İlgili bilgi için DAO Yardımı'ndaki "RecordsAffected özelliği" konusuna bakın.  
  
##  <a name="getrelationcount"></a>  CDaoDatabase::GetRelationCount  
 Veritabanındaki tablolar arasındaki tanımlanan ilişkiler numarasını almak için bu üye işlevini çağırın.  
  
```  
short GetRelationCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veritabanındaki tablolar arasındaki tanımlanan ilişkiler sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **GetRelationCount** veritabanının ilişkileri koleksiyonundaki tüm tanımlı ilişkileri döngü gerektiğinde kullanışlı olur. Koleksiyonda belirtilen bir ilişki hakkında bilgi edinmek için bkz: [GetRelationInfo](#getrelationinfo).  
  
 Bir ilişki kavramını göstermek için bir değişecekse ve bir-çok ilişkisi olabilir bir Ürünler tablosuna göz önünde bulundurun. Bu ilişki içinde bir sağlayıcı birden fazla ürün sağlayabilir. Diğer ilişkileri birebir ve çok-çok.  
  
##  <a name="getrelationinfo"></a>  CDaoDatabase::GetRelationInfo  
 Veritabanının ilişkileri koleksiyonda belirtilen bir ilişki hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
```  
void GetRelationInfo(
    int nIndex,  
    CDaoRelationInfo& relinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetRelationInfo(
    LPCTSTR lpszName,  
    CDaoRelationInfo& relinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Dizine göre arama için veritabanının ilişkiler koleksiyonu ilişki nesnesinde dizini.  
  
 *relinfo*  
 Bir başvuru bir [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) istenen bilgileri döndürür nesnesi.  
  
 *dwInfoOptions*  
 Hangi bilgilerini almak için ilişkisi belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi hakkında ilişkisi döndürecek şekilde neden birlikte aşağıda listelenmiştir:  
  
- `AFX_DAO_PRIMARY_INFO` (Varsayılan) Ad, tablo, yabancı tablosu  
  
- `AFX_DAO_SECONDARY_INFO` Öznitelikler, alanın bilgileri  
  
 Alan bilgiler bir [Cdaorelationfieldınfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) ilişkisinde katılan birincil tablodan alanları içeren bir nesne.  
  
 *lpszName*  
 Ada göre arama ilişkisi nesne adını içeren dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev iki sürümü, dizin veya adına göre erişim sağlar. Döndürülen bilgi açıklaması *relinfo*, bkz: [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor *dwInfoOptions*. Bir düzeyde bilgi istemek, tüm önceki düzeylerinde de bilgi alın.  
  
> [!NOTE]
>  İlişki cascade işlemlerini etkinleştirmek için nesnenin öznitelikleri ayarlarsanız ( **dbRelationUpdateCascades** veya **dbRelationDeleteCascades**), Microsoft Jet veritabanı altyapısı otomatik olarak güncelleştirir veya ilgili birincil anahtar tablolarda değişiklik yapıldığında, bir veya daha fazla diğer tablolardaki kayıtlarını siler. Örneğin, Müşteriler tablosu ve Siparişler tablosu arasında bir cascade delete ilişki kurmak varsayalım. Müşteriler tablosundan kayıtları sildiğinizde, o müşteri ile ilgili Siparişler tablosundaki kayıtları da silinir. Ayrıca, Siparişler tablosundaki ve diğer tablolar arasındaki cascade delete ilişkileri kurmak, Müşteriler tablosundan kayıtları sildiğinizde bu tablolardan kayıtları otomatik olarak silinir.  
  
##  <a name="gettabledefcount"></a>  CDaoTableDefInfo  
 Veritabanında tanımlanan tablo sayısını almak için bu üye işlevini çağırın.  
  
```  
short GetTableDefCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veritabanında tanımlanan tabledefs sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetTableDefCount` veritabanının TableDefs koleksiyonundaki tüm tabledefs döngü gerektiğinde kullanışlı olur. Bir koleksiyondaki belirli bir tablodaki hakkında bilgi edinmek için bkz: [GetTableDefInfo](#gettabledefinfo).  
  
##  <a name="gettabledefinfo"></a>  CDaoDatabase::GetTableDefCount  
 Çeşitli veritabanında tanımlı bir tablo hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
```  
void GetTableDefInfo(
    int nIndex,  
    CDaoTableDefInfo& tabledefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetTableDefInfo(
    LPCTSTR lpszName,  
    CDaoTableDefInfo& tabledefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Dizine göre arama için veritabanının TableDefs koleksiyonu tabledef nesnesinde dizini.  
  
 *tabledefinfo*  
 Bir başvuru bir [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) istenen bilgileri döndürür nesnesi.  
  
 *dwInfoOptions*  
 Hangi bilgilerini almak için tabloyu belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi hakkında ilişkisi döndürecek şekilde neden birlikte aşağıda listelenmiştir:  
  
- `AFX_DAO_PRIMARY_INFO` (Varsayılan) Ad, güncelleştirilebilir, öznitelikleri  
  
- `AFX_DAO_SECONDARY_INFO` Birincil bilgileri artı: oluşturma tarihi, tarih son güncelleştirilmiş, kaynak tablo adı Bağlan  
  
- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgi artı: doğrulama kuralı, doğrulama metin kayıt sayısı  
  
 *lpszName*  
 Ada göre arama tabledef nesnesinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tablo veritabanı TableDefs koleksiyonu dizinde veya tablonun adını göre seçebilmeniz işlevi iki sürümü sağlanır.  
  
 Döndürülen bilgi açıklaması *tabledefinfo*, bkz: [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor *dwInfoOptions*. Bir düzeyde bilgi isterse de önceki tüm düzeylerde bilgilerini edinin.  
  
> [!NOTE]
>  `AFX_DAO_ALL_INFO` Seçeneği elde etmek yavaş olabilir bilgi sağlar. Bu durumda, tablodaki kayıtları sayım çok sayıda kayıt varsa zun olabilir.  
  
##  <a name="getversion"></a>  CDaoDatabase::GetVersion  
 Microsoft Jet veritabanı dosyası sürümünü belirlemek için bu üye işlevini çağırın.  
  
```  
CString GetVersion();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesiyle ilişkili veritabanı dosyası sürümünü belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen değer "major.minor"; formunda sürüm numarasını temsil eder Örneğin, "3.0". Ürün sürüm numarası (örneğin, 3.0) sürüm numarası (3), nokta ve sürüm numarasını (0) oluşur. Tarihe sürümleri 1.0, 1.1, 2.0 ve 3.0.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Version özelliği" konusuna bakın.  
  
##  <a name="isopen"></a>  CDaoDatabase::IsOpen  
 Belirlemek için bu üye işlevini çağırın olup olmadığını `CDaoDatabase` nesne bir veritabanı üzerinde şu anda açık.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CDaoDatabase` nesne şu anda açık; Aksi halde 0 değil.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_pdaodatabase"></a>  CDaoDatabase::m_pDAODatabase  
 DAO veritabanı nesnesinin altındaki için OLE arabirimi için bir işaretçi içeriyor `CDaoDatabase` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 DAO arabirimi doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.  
  
 Doğrudan çağırma DAO hakkında bilgi için bkz [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
##  <a name="m_pworkspace"></a>  CDaoDatabase::m_pWorkspace  
 Bir işaretçi içeriyor [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) veritabanı nesnesini içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Çalışma alanına doğrudan erişim gerekiyorsa bu işaretçiyi kullanın — örneğin, çalışma alanı'nın veritabanları koleksiyondaki diğer veritabanı nesnelerine işaretçiler elde edilir.  
  
##  <a name="open"></a>  CDaoDatabase::Open  
 Yeni oluşturulan başlatmak için bu üye işlevini çağırmanız gerekir `CDaoDatabase` varolan bir veritabanını temsil eden nesne.  
  
```  
virtual void Open(
    LPCTSTR lpszName,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T(""));
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszName*  
 Var olan bir Microsoft Jet adı bir dize ifadesi (. MDB) veritabanı dosyası. Dosya adı bir uzantıya sahipse, gerekli değildir. Ağınız Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, aynı zamanda bir ağ yolu gibi belirtebilirsiniz "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Çift ters eğik çizgi, dize değişmez değerleri gereklidir, çünkü "\\" C++ kaçış karakteri.)  
  
 Bazı önemli noktalar kullanılırken geçerlidir *lpszName*. Varsa bu:  
  
-   Zaten başka bir kullanıcı tarafından türünde özel bir MFC atar özel erişim için açık olan bir veritabanı başvurduğu [CDaoException](../../mfc/reference/cdaoexception-class.md). Veritabanı kullanılamaz olduğunu biliyorsanız, kullanıcı izin vermek için başka bir özel durum yakalar.  
  
-   Boş bir dize ("") ve *lpszConnect* "ODBC;", kullanıcı bir veritabanı seçebilmeniz için tüm kayıtlı ODBC veri kaynağı adları listeleyen bir iletişim kutusu görüntülenir. ODBC veri kaynaklarını doğrudan bağlantılar kaçınmanız gerekir; ekli bir tablo kullanın.  
  
-   Aksi takdirde varolan bir veritabanına veya geçerli ODBC veri kaynağı adı, özel durum türü MFC verir başvurmuyor `CDaoException`.  
  
> [!NOTE]
>  DAO hata kodları hakkında daha fazla ayrıntı için DAOERR bakın. H dosyası. İlgili bilgi için "Yakalanabilir veri erişimi hatası" DAO Yardım konusuna bakın.  
  
 *bExclusive*  
 Bir Boole değeri **TRUE** veritabanı için özel (paylaşılmayan) erişim açılacak olup olmadığını ve **FALSE** veritabanı için paylaşılan erişim açılacak ise. Bu bağımsız değişken atlarsanız, veritabanını paylaşılan erişim için açıldı.  
  
 *bReadOnly*  
 Bir Boole değeri **TRUE** veritabanı salt okunur erişim için açık olup olmadığını ve **FALSE** veritabanı için okuma/yazma erişimi açılacak ise. Bu bağımsız değişken atlarsanız, veritabanının okuma/yazma erişimi için açıldı. Tüm bağımlı kayıt kümeleri, bu öznitelik devralır.  
  
 *lpszConnect*  
 Veritabanını açmak için kullanılan bir dize ifadesi. Bu dize ODBC oluşturduğunu bağımsız değişkenleri bağlanın. Bir kaynak dizesi sağlamak için özel ve salt okunur bağımsız değişkenleri belirtmeniz gerekir. Microsoft Jet veritabanı veritabanıysa (. MDB), bu dize boşsa (""). Varsayılan değer sözdizimi — **_T**("") — taşınabilirlik ANSI yanı sıra Unicode için uygulamanızın veya derlemeler sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 **Açık** veritabanı DAO nesnesini ile ilişkilendirir. Veritabanı nesnesi, başlatılana dek kayıt kümesi, tabledef veya querydef nesneleri oluşturmak için kullanamazsınız. **Açık** veritabanı nesnesi ilişkili Workspace'in veritabanları koleksiyonuna ekler.  
  
 Parametreleri aşağıdaki şekilde kullanın:  
  
-   Microsoft Jet açarsa (. MDB) veritabanı, kullanım *lpszName* parametre ve boş bir dize için geçişi *lpszConnect* parametresi veya geçişi biçiminde bir parola dizesi "; PWD parola = "veritabanı parola korumalı ise (. MDB veritabanları yalnızca).  
  
-   ODBC veri kaynağını açıyorsanız, geçerli bir ODBC bağlantı dizesinde geçirmek *lpszConnect* ve boş bir dize *lpszName*.  
  
 İlgili bilgi için DAO Yardımı'ndaki "OpenDatabase yöntemi" konusuna bakın.  
  
> [!NOTE]
>  ISAM veritabanları ve ODBC veri kaynakları gibi dış veritabanlarını erişirken daha iyi performans için bir Microsoft Jet altyapısı veritabanına dış veritabanı tablolarını ekleme önerilir (. MDB) yerine doğrudan veri kaynağına bağlanma.  
  
 Örneğin, DBMS konak kullanılamıyorsa, bağlantı girişimi zaman aşımına mümkündür. Bağlantı denemesi başarısız olursa, `Open` türünde bir özel durum atar [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Kalan açıklamalar yalnızca ODBC veritabanları için geçerlidir:  
  
 Veritabanı bir ODBC veritabanı ve parametrelerinde olup olmadığını, `Open` çağrısı bağlantı oluşturmak için yeterli bilgi içermiyor, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açılır. Çağırdığınızda `Open`, bağlantı dizenizi *lpszConnect*, özel olarak depolanır ve çağırarak kullanılabilir [GetConnect](#getconnect) üye işlevi.  
  
 İsterseniz, çağırmadan önce kendi iletişim kutusunu açabilirsiniz `Open` kullanıcıdan bir parola gibi bilgileri almak için daha sonra bu bilgileri geçirmek için bağlantı dizesi ekleyin `Open`. Veya uygulama çağrılarınızı geçirdiğiniz (belki de Windows Kayıt Defteri'nde) sonraki yeniden şekilde bağlantı dizesini zaman isteyebilirsiniz `Open` üzerinde bir `CDaoDatabase` nesnesi.  
  
 Oturum açma yetkilendirme birden çok düzeyi için bağlantı dizesini de kullanabilirsiniz (her biri için farklı bir `CDaoDatabase` nesnesi) veya diğer veritabanı özgü bilgileri iletmek için.  
  
##  <a name="setquerytimeout"></a>  CDaoDatabase::SetQueryTimeout  
 Sonraki işlemlerde bağlı veritabanı zaman aşımı önce izin vermek için saniye varsayılan sayısını geçersiz kılma için bu üye işlevini çağırın.  
  
```  
void SetQueryTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>Parametreler  
 *nSeconds*  
 Bir sorguyu denemeden önce izin vermek için saniye sayısını zaman aşımına uğradı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işlem ağ erişim sorunları, aşırı sorgu işleme süresini ve benzeri nedeniyle zaman. Çağrı `SetQueryTimeout` kümenizin açmadan önce veya kayıt kümesinin çağırmadan önce [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [güncelleştirme](../../mfc/reference/cdaorecordset-class.md#update), veya [silmek](../../mfc/reference/cdaorecordset-class.md#delete) üye işlevlerini sorgu değiştirmek istiyorsanız zaman aşımı değeri. Ayar sonraki tüm etkiler [açık](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`, `Update`, ve `Delete` bu ile ilişkili tüm kayıt kümeleri çağrıları `CDaoDatabase` nesnesi. Bir kayıt kümesi için sorgu zaman aşımı değeri açıldıktan sonra değiştirme kayıt değeri değiştirmez. Örneğin, sonraki [taşıma](../../mfc/reference/cdaorecordset-class.md#move) işlemleri, yeni değer kullanmayın.  
  
 Sorgu zaman aşımı için varsayılan değer 60 saniyedir. Tüm veritabanları sorgu zaman aşımı değerini ayarlama özelliği destekler. Bir sorgu zaman aşımı değeri 0 olarak ayarlarsanız, hiçbir zaman aşımı oluşur; veritabanı ile iletişim yanıt vermeyebilir. Bu davranış geliştirme sırasında yararlı olabilir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "QueryTimeout özelliği" konusuna bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)   
 [CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
