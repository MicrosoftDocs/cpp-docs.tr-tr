---
title: CDaoDatabase sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 6bdabafc905b1ae5d6ed9a1fcd83ab1982871c3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439293"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase sınıfı

Veriler üzerinde çalışabileceğiniz veritabanı bağlantısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|Oluşturur bir `CDaoDatabase` nesne. Çağrı `Open` nesne bir veritabanına bağlanmak için.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoDatabase::CanTransact](#cantransact)|İşlemleri veritabanına destekliyorsa, sıfır döndürür.|
|[CDaoDatabase::CanUpdate](#canupdate)|Döndürür gösterimiyse `CDaoDatabase` nesne güncelleştirilebilir değil (salt okunur).|
|[CDaoDatabase::Close](#close)|Veritabanı bağlantıyı kapatır.|
|[CDaoDatabase::Create](#create)|DAO veritabanı nesnesini oluşturur ve başlatır `CDaoDatabase` nesne.|
|[CDaoDatabase::CreateRelation](#createrelation)|Tablolar arasında yeni bir ilişki veritabanında tanımlar.|
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|Veritabanının QueryDefs koleksiyona kaydedilen QueryDefs siler.|
|[CDaoDatabase::DeleteRelation](#deleterelation)|Veritabanındaki tablolar arasında var olan bir ilişki siler.|
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|Veritabanındaki bir tablo tanımını siler. Bu, gerçek tablo ve tüm verilerini siler.|
|[CDaoDatabase::Execute](#execute)|Bir eylem sorguyu yürütür. Çağırma `Execute` için sonuçları döndüren bir sorgu bir özel durum oluşturur.|
|[CDaoDatabase::GetConnect](#getconnect)|Bağlanmak için kullanılan bağlantı dizesi döndürür `CDaoDatabase` nesne bir veritabanı. ODBC için kullanılır.|
|[CDaoDatabase::GetName](#getname)|Veritabanının adı, şu anda kullanımda döndürür.|
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|Veritabanı için tanımlanan sorguların sayısını döndürür.|
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|Veritabanında tanımlanan belirtilen bir sorgu hakkındaki bilgileri döndürür.|
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|İşlem Sorgusu saniye sonra hangi veritabanı sayısını döndürür, zaman aşımına uğrar. Tüm sonraki etkiler açın, yeni Ekle, Güncelleştir ve işlemlerinin ve ODBC veri kaynakları üzerinde başka işlemler (yalnızca) gibi düzenleyin `Execute` çağırır.|
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|Etkilenen son güncelleştirme ile kayıt sayısını döndürür, düzenleme veya ekleme işlemi veya yapılan bir çağrıyla `Execute`.|
|[CDaoDatabase::GetRelationCount](#getrelationcount)|Tanımlanan veritabanındaki tablolar arasında ilişkiler sayısını döndürür.|
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|Veritabanındaki tablolar arasında tanımlanan belirtilen bir ilişki hakkındaki bilgileri döndürür.|
|[CDaoTableDefInfo](#gettabledefcount)|Veritabanında tanımlanan tablo sayısını döndürür.|
|[CDaoDatabase::GetTableDefCount](#gettabledefinfo)|Belirtilen tablo hakkındaki bilgileri veritabanında döndürür.|
|[CDaoDatabase::GetVersion](#getversion)|Veritabanıyla ilişkili veritabanı altyapısı sürümünü döndürür.|
|[CDaoDatabase::IsOpen](#isopen)|Döndürür gösterimiyse `CDaoDatabase` nesnesi şu anda bir veritabanına bağlı.|
|[CDaoDatabase::Open](#open)|Veritabanına bir bağlantı kurar.|
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|Saniye sonra hangi veritabanı sayısı (yalnızca ODBC veri kaynakları için) işlemleri sorgu kümelerini zaman aşımına uğrar. Tüm sonraki etkiler açın, yeni Ekle, güncelleştirme ve silme işlemleri.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|DAO veritabanı nesnesini bir işaretçi.|
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|Bir işaretçi [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) veritabanını içeren ve işlem alanı tanımlayan nesne.|

## <a name="remarks"></a>Açıklamalar

Desteklenen veritabanı biçimleri hakkında daha fazla bilgi için bkz: [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) üye işlevi. Bir veya daha fazla olabilir `CDaoDatabase` "tarafından temsil edilen bir verilen çalışma alanında," nesneleri aynı anda etkin bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesne. Çalışma alanı veritabanı koleksiyonu olarak adlandırılan, açık veritabanı nesnelerinin koleksiyonunu tutar.

> [!NOTE]
>  MFC DAO veritabanı sınıfları, ODBC tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. Sınıf `CDaoDatabase` ODBC sınıfı için benzer bir arabirim sağlayan [CDatabase](../../mfc/reference/cdatabase-class.md). Ana fark `CDatabase` DBMS bu DBMS için açık veritabanı bağlantısı (ODBC) ve ODBC sürücüsü aracılığıyla erişir. `CDaoDatabase` Veri aracılığıyla bir veri erişim nesnesi (Microsoft Jet veritabanı altyapısını temel alan DAO) erişir. Genel olarak, üzerinde DAO göre MFC sınıflarını ODBC tabanlı MFC sınıfları daha yetenekli; DAO dayalı sınıflar kendi veritabanı altyapısı aracılığıyla ODBC sürücüleri dahil olmak üzere, verilere erişebilir. DAO dayalı sınıflar da DAO doğrudan çağırmak zorunda kalmadan tablo sınıfları aracılığıyla ekleme gibi veri tanımlama dili (DDL) işlemleri destekler.

## <a name="usage"></a>Kullanım

Kayıt kümesi nesneler oluşturduğunuzda, veritabanı nesneleri örtülü olarak oluşturabilirsiniz. Ancak veritabanı nesneleri açıkça oluşturabilirsiniz. Açıkça ile varolan bir veritabanını kullanmayı `CDaoDatabase`, aşağıdakilerden birini yapın:

- Oluşturmak bir `CDaoDatabase` nesne, işaretçi bir açık olarak geçirme [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesne.

- Veya oluşturmak bir `CDaoDatabase` (MFC oluşturduğu geçici çalışma alanı nesnesi) çalışma alanı belirtmeden nesne.

Yeni bir Microsoft Jet oluşturmak için (. MDB) veritabanı oluşturmak bir `CDaoDatabase` nesne ve çağrı kendi [Oluştur](#create) üye işlevi. Yapmak *değil* çağrı `Open` sonra `Create`.

Varolan bir veritabanını açmak, oluşturmak bir `CDaoDatabase` nesne ve çağrı kendi [açın](#open) üye işlevi.

Aşağıdaki tekniklerden birini çalışma alanınızın veritabanı derlemesine DAO veritabanı nesnesi ekler ve verileri bir bağlantı açar. Ardından oluşturmak zaman [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), veya [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) bağlı veritabanında çalışmak nesnelerini geçirmek bu nesneler için oluşturucular bir İşaretçi, `CDaoDatabase` nesne. Bağlantıyı kullanmayı bitirdiğinizde, çağrı [Kapat](#close) üye işlevi ve yok et `CDaoDatabase` nesne. `Close` önceden kapattıysanız değil tüm kayıt kümelerini kapatır.

## <a name="transactions"></a>İşlemler

Veritabanı işlem çalışma alanı düzeyinde sağlanan — bkz [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), ve [geri alma](../../mfc/reference/cdaoworkspace-class.md#rollback) sınıfın üye işlevleri `CDaoWorkspace` .

## <a name="odbc-connections"></a>ODBC Bağlantıları

ODBC veri kaynakları ile çalışmak için önerilen yöntem dış tablolar için Microsoft Jet eklemektir (. MDB) veritabanı.

## <a name="collections"></a>Koleksiyonlar

Her veritabanı kendi tabledef, querydef, kayıt kümesi ve ilişki nesneleri koleksiyonunu tutar. Sınıf `CDaoDatabase` bu nesneleri işlemek için üye işlevlerini sağlar.

> [!NOTE]
>  Nesneleri DAO'da, MFC veritabanı nesnesi değil depolanır. MFC sınıfları tabledef querydef ve kayıt kümesi nesneler için ilişki nesneleri ancak sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="cantransact"></a>  CDaoDatabase::CanTransact

Veritabanı işlemleri izin verip vermeyeceğini belirlemek için bu üye işlevini çağırın.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanı işlemleri destekler olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İşlem, veritabanı çalışma alanında yönetilir.

##  <a name="canupdate"></a>  CDaoDatabase::CanUpdate

Belirlemek için bu üye işlevi çağrısı olup olmadığını `CDaoDatabase` nesne güncelleştirmeler sağlar.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

Yalnız `CDaoDatabase` nesne güncelleştirmeleri sağlar; Aksi durumda 0 ya da sizin belirten TRUE geçirilen *bReadOnly* açtığınızda `CDaoDatabase` nesne veya veritabanı salt okunur. Bkz: [açık](#open) üye işlevi.

### <a name="remarks"></a>Açıklamalar

Veritabanı Güncelleştirilebilirlik hakkında daha fazla bilgi için DAO Yardımı'nda "güncelleştirilebilir özelliği" konusuna bakın.

##  <a name="cdaodatabase"></a>  CDaoDatabase::CDaoDatabase

Oluşturur bir `CDaoDatabase` nesne.

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>Parametreler

*pWorkspace*<br/>
Bir işaretçi `CDaoWorkspace` yeni veritabanı nesnesini içeren nesne. NULL varsayılan değeri kabul ederseniz, geçici bir oluşturucu oluşturur `CDaoWorkspace` varsayılan DAO çalışma kullanan nesne. Çalışma alanı nesnesi bir işaretçi alabilirsiniz [m_pWorkspace](#m_pworkspace) veri üyesi.

### <a name="remarks"></a>Açıklamalar

Yeni bir Microsoft Jet oluşturuyorsanız sonra nesneyi oluşturmak (. MDB) veritabanı, nesnenin [Oluştur](#create) üye işlevi. Bunun yerine, olması durumunda nesnenin çağrısı var olan bir veritabanını açmak [açık](#open) üye işlevi.

Nesne ile işiniz bittiğinde, çağırmalıdır kendi [Kapat](#close) üye işlevi ve ardından yok `CDaoDatabase` nesne.

Eklemek kullanışlı bulabileceğiniz `CDaoDatabase` belge sınıfınızdaki nesne.

> [!NOTE]
>  A `CDaoDatabase` nesnesi de oluşturulur örtük olarak açarsanız bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) varolan bir işaretçi geçirmeden nesne `CDaoDatabase` nesne. Kayıt kümesi nesnesi kapattığınızda, bu veritabanı nesnesi kapalı.

##  <a name="close"></a>  CDaoDatabase::Close

Bir veritabanı bağlantısını kesmek ve herhangi bir açık kayıt kümeleri, tabledefs ve veritabanıyla ilişkili querydefs kapatmak için bu üye işlevini çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırmadan önce bu nesneleri kendiniz kapatmak için iyi bir uygulamadır. Kapatma bir `CDaoDatabase` nesne ilişkili veritabanlarını koleksiyondan onu kaldırır [çalışma](../../mfc/reference/cdaoworkspace-class.md). Çünkü `Close` yok `CDaoDatabase` yeniden nesne aynı veya farklı bir veritabanının açarak nesnesi.

> [!CAUTION]
>  Çağrı [güncelleştirme](../../mfc/reference/cdaorecordset-class.md#update) (Bekleyen düzenlemeler varsa) üye işlevi ve `Close` veritabanı kapatmadan önce tüm açık kayıt nesnelerde üye işlevi. Bildiren bir işlev çıkarsanız [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) veya `CDaoDatabase` nesneler yığında, veritabanı kapalı, kaydedilmemiş tüm değişiklikler kaybedilir, tüm bekleyen işlemler geri alınır ve verilerinize bekleyen düzenlemeler kaybedilir.

> [!CAUTION]
>  Herhangi bir kayıt kümesi nesne açıkken veritabanı nesnesini kapatmak deneyin veya bir çalışma alanı nesnesi, belirli bir çalışma alanına ait veritabanı nesneler açıkken kapatmak çalışırsanız, kayıt kümesi nesnelere kapatılacak ve tüm bekleyen güncelleştirmeleri veya düzenleme geri alındı. Bir çalışma nesnesi kendisine ait veritabanı nesneler açıkken kapatmak çalışırsanız, işlem kapatıldığından kuşkulanılıyor kapatılmamış kayıt nesneleri neden olabilir, belirli bir çalışma alanı nesnesine ait tüm veritabanı nesnelerinin kapatır. Veritabanı Nesnenizi kapatmazsanız MFC hata ayıklama yapılarında bir onaylama işlemi hatası raporlar.

Veritabanı nesnesi açıkça kapatılana kadar açık kalır veya veritabanı nesnesi bir işlevin kapsamı dışında tanımlanır ve kapatmadan işlevi çıkın, içinde tanımlandığı modül kapsam dışında olsa.

##  <a name="create"></a>  CDaoDatabase::Create

Yeni bir Microsoft Jet oluşturmak için (. MDB), oluşturduktan sonra bu üye işlevini çağırın, veritabanı bir `CDaoDatabase` nesne.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Oluşturmakta olduğunuz veritabanı dosyasının adı bir dize ifadesi. Bu dosyanın tam yolunu ve dosya adı gibi olabilir "C:\\\MYDB. MDB". Bir ad sağlamanız gerekir. Varsa, bir dosya adı uzantısı vermezsiniz. MDB eklenir. Ağınızı Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, bir ağ yolu gibi belirtebilirsiniz "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB". Yalnızca Microsoft Jet (. MDB) veritabanı dosyaları, bu üye işlevi kullanılarak oluşturulabilir. (Çift ters eğik çizgi, dize sabit gereklidir, çünkü "\\" C++ kaçış karakteri olan.)

*lpszLocale*<br/>
Veritabanı oluşturmak için harmanlama sırası belirtmek için kullanılan bir dize ifadesi. Varsayılan değer `dbLangGeneral` şeklindedir. Olası değerler şunlardır:

- `dbLangGeneral` İspanyolca, İngilizce, Almanca, Fransızca, Portekizce, İtalyanca ve Modern

- `dbLangArabic` Arapça

- `dbLangCyrillic` Rusça

- `dbLangCzech` Çekçe

- `dbLangDutch` Hollanda dili

- `dbLangGreek` Yunanca

- `dbLangHebrew` İbranice

- `dbLangHungarian` Macarca

- `dbLangIcelandic` İzlanda dili

- `dbLangNordic` Kuzey Dilleri (yalnızca Microsoft Jet veritabanı motoru sürüm 1.0)

- `dbLangNorwdan` Norveççe ve Danca

- `dbLangPolish` Lehçe

- `dbLangSpanish` Geleneksel İspanyolca

- `dbLangSwedfin` İsveç dili ve Fince

- `dbLangTurkish` Türkçe

*dwOptions*<br/>
Bir veya daha fazla gösteren bir tamsayı. Olası değerler şunlardır:

- `dbEncrypt` Şifrelenmiş bir veritabanı oluşturun.

- `dbVersion10` Microsoft Jet veritabanı sürüm 1.0 ile bir veritabanı oluşturun.

- `dbVersion11` Microsoft Jet veritabanı sürüm 1.1 ile bir veritabanı oluşturun.

- `dbVersion20` Microsoft Jet veritabanı sürüm 2.0 ile bir veritabanı oluşturun.

- `dbVersion30` Microsoft Jet veritabanı sürüm 3.0 ile bir veritabanı oluşturun.

Şifreleme sabiti atlarsanız, şifrelenmemiş bir veritabanı oluşturulur. Yalnızca bir sürümü sabiti belirtebilirsiniz. Bir sürüm sabit atlarsanız, Microsoft Jet veritabanı sürüm 3.0 kullanan bir veritabanı oluşturulur.

> [!CAUTION]
>  Bir veritabanı şifreli değilse, kullanıcı/parola güvenlik, doğrudan veritabanı oluşturan ikili disk dosyası okuma için bile uygularsanız, mümkündür.

### <a name="remarks"></a>Açıklamalar

`Create` Veritabanı dosyası ve DAO veritabanı nesnesini oluşturur ve C++ nesnesini başlatır. Nesne, ilişkili çalışma alanınızın veritabanları koleksiyona eklenir. Veritabanı nesnesi açık bir durumda; çağırmayın `Open*` sonra `Create`.

> [!NOTE]
>  İle `Create`, yalnızca Microsoft Jet oluşturabilirsiniz (. MDB) veritabanları. ISAM veritabanı veya ODBC veritabanı oluşturulamıyor.

##  <a name="createrelation"></a>  CDaoDatabase::CreateRelation

Veritabanı birincil bir tablodaki bir veya daha fazla alanlarına ve yabancı bir tablodaki (başka bir tablo veritabanındaki) bir veya daha fazla alanları arasında bir ilişki kurmak için bu üye işlevini çağırın.

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

*lpszName*<br/>
İlişki nesnesinin benzersiz adı. Ad bir harf ile başlamalı ve en fazla 40 karakter içerebilir. Sayılar içerebilir ve alt çizgi karakterleri, ancak noktalama işaretleri veya boşluk içeremez.

*lpszTable*<br/>
İlişkinin birincil tablosunun adı. Tablo mevcut değilse bir özel durum türü, MFC oluşturur [CDaoException](../../mfc/reference/cdaoexception-class.md).

*lpszForeignTable*<br/>
İlişkinin yabancı tablosunun adı. Tablo mevcut değilse bir özel durum türü, MFC oluşturur `CDaoException`.

*lAttributes*<br/>
İlişki türü hakkında bilgi içeren bir uzun değer. Diğer özelliklerin yanı sıra bilgi tutarlılığını zorlamak için bu değeri kullanabilirsiniz. Bit düzeyinde OR işleci kullanabilirsiniz ( **&#124;**) (birlikte mantıklı olduğu sürece) aşağıdaki değerlerden herhangi birini birleştirmek için:

- `dbRelationUnique` Bire bir ilişkidir.

- `dbRelationDontEnforce` İlişki (hiçbir bilgi tutarlılığı) zorunlu tutulur.

- `dbRelationInherited` İlişki, iki bağlı tabloları içeren çerçevesidir bir veritabanında zaten var.

- `dbRelationUpdateCascade` Güncelleştirmeleri basamaklı (basamaklar hakkında daha fazla bilgi için bkz. Notlar).

- `dbRelationDeleteCascade` Silme işlemleri basamaklı.

*lpszField*<br/>
Birincil tablo bir alanın adını içeren bir null ile sonlandırılmış dizeye bir işaretçi (tarafından adlandırılan *lpszTable*).

*lpszForeignField*<br/>
Dış tablo bir alanın adını içeren bir null ile sonlandırılmış dizeye bir işaretçi (tarafından adlandırılan *lpszForeignTable*).

*relinfo*<br/>
Bir başvuru bir [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) ilişki oluşturmak istediğiniz bilgi içeren nesne.

### <a name="remarks"></a>Açıklamalar

İlişki, bir sorgu veya harici bir veritabanına ekli bir tablodan ilgili olamaz.

Bir alan her iki tablonun ilişki içerdiğinde işlevin ilk sürümünü kullanın. İlişki birden çok alan gerektirdiğinde dosyanın ikinci sürümü kullanın. En fazla bir ilişki alanları 14 sayısıdır.

Bu eylem bir temel alınan DAO ilişki nesnesi oluşturur, ancak bir MFC uygulaması ayrıntı ilişkisi nesnelerin MFC'nin kapsülleme sınıfı içinde yer aldığından budur `CDaoDatabase`. MFC sınıf ilişkileri için sağlamaz.

İlişki cascade işlemlerini etkinleştirmek için nesnenin öznitelikleri ayarlarsanız, veritabanı altyapısı, otomatik olarak güncelleştirir veya ilgili birincil anahtar tablolarda değişiklik yapıldığında, bir veya daha fazla diğer tablodaki kayıtları siler.

Örneğin, bir Customers ve Orders tablosunu arasında bir cascade delete ilişkisi oluşturmanız varsayalım. Müşteriler tablosundan kayıtları sildiğinizde, o müşterilerle ilgili Siparişler tablosunda kayıtlar da silinir. Ayrıca, Siparişler tablosu ve diğer tablolar arasındaki art arda silme ilişkileri kurmak, Müşteriler tablosundan kayıtları sildiğinizde bu tablolardan kayıtları otomatik olarak silinir.

İlgili bilgiler için DAO Yardımı'nda "CreateRelation yöntemi" konusuna bakın.

##  <a name="deletequerydef"></a>  CDaoDatabase::DeleteQueryDef

Belirtilen querydef silmek için bu üye işlevini çağırın; kayıtlı sorgu — dan `CDaoDatabase` nesnenin QueryDefs koleksiyonu.

```
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Silmek için kaydedilmiş bir sorgu adı.

### <a name="remarks"></a>Açıklamalar

Bu sorguyu daha sonra artık veritabanında tanımlı.

Querydef nesneleri oluşturma hakkında daha fazla bilgi için bkz. [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Belirli bir QueryDefs ilişkilendirilir `CDaoDatabase` nesne oluşturduğunuzda, `CDaoQueryDef` veritabanı nesnesine bir işaretçi geçirme nesnesi.

##  <a name="deleterelation"></a>  CDaoDatabase::DeleteRelation

Veritabanı nesnesinin ilişkileri koleksiyonundan mevcut bir ilişkiyi silmek için bu üye işlevini çağırın.

```
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
İlişkinin adıyla birlikte silinecek.

### <a name="remarks"></a>Açıklamalar

Daha sonra ilişkisi artık yok.

İlgili bilgiler için "Delete yöntemini" DAO Yardım konusuna bakın.

##  <a name="deletetabledef"></a>  CDaoDatabase::DeleteTableDef

Belirtilen tablo ve tüm verilerini silmek için bu üye işlevi çağrısı `CDaoDatabase` nesnenin TableDefs koleksiyonu.

```
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Silinecek tabledef adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra bu tablosu artık veritabanında tanımlanır.

> [!NOTE]
>  Sistem tabloları silmemeyi çok dikkatli olun.

Tabledef nesneleri oluşturma hakkında daha fazla bilgi için bkz. [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Tabledef nesnesi ile belirli bir ilişkilendirilir `CDaoDatabase` nesne oluşturduğunuzda, `CDaoTableDef` veritabanı nesnesine bir işaretçi geçirme nesnesi.

İlgili bilgiler için "Delete yöntemini" DAO Yardım konusuna bakın.

##  <a name="execute"></a>  CDaoDatabase::Execute

Eylem sorgusu çalıştırmak veya veritabanında bir SQL deyimi yürütmek için bu üye işlevini çağırın.

```
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Parametreler

*lpszSQL*<br/>
Yürütmek için geçerli bir SQL komut içeren null ile sonlandırılmış bir dize işaretçisi.

*nOptions*<br/>
Sorgu bütünlüğünü seçenekleri belirten bir tamsayı. Bit düzeyinde OR işleci kullanabilirsiniz ( **&#124;**) herhangi birini aşağıdaki sabitler birleştirmek için (birleşimi mantıklı sağlanan — örneğin değil birleştirerek `dbInconsistent` ile `dbConsistent`):

- `dbDenyWrite` Diğer kullanıcılara yazma izni reddetme.

- `dbInconsistent` (Varsayılan) Tutarsız güncelleştirmeler.

- `dbConsistent` Tutarlı güncelleştirmeler.

- `dbSQLPassThrough` SQL doğrudan. İşleme için bir ODBC veri kaynağı için geçirilecek SQL deyimi neden olur.

- `dbFailOnError` Hata oluşması durumunda geri güncelleştirir.

- `dbSeeChanges` Düzenlemekte olduğunuz veri başka bir kullanıcı değişiyorsa, bir çalışma zamanı hatası oluşturur.

> [!NOTE]
>  Her iki `dbInconsistent` ve `dbConsistent` içerdiği ya da hiçbiri dahil ise, sonuç varsayılandır. Bu sabitler açıklaması için DAO Yardımı'nda "yöntemi Çalıştır" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

`Execute` Yalnızca eylem sorguları ya da sonuçları döndürmeyen SQL doğrudan sorgular için çalışır. Kayıt döndüren select sorgusu için çalışmaz.

Tanım ve eylem sorguları hakkında daha fazla bilgi için "Eylem sorgu" ve "Yürütme yönteminde" DAO Yardım konularına bakın.

> [!TIP]
>  Verilen sözdizimsel olarak doğru bir SQL deyimi ve uygun izinlere `Execute` üye işlevi değil başarısız olur bile tek bir satır değiştirilen veya silinen değilse. Bu nedenle, her zaman kullan `dbFailOnError` seçeneğini kullanırken `Execute` bir güncelleştirme veya silme sorgusu üye işlevi. MFC özel durum türü bu seçeneği neden [CDaoException](../../mfc/reference/cdaoexception-class.md) ve etkilenen kayıtların birini kilitli ve güncelleştirilemiyor veya silinmesi durumunda başarılı tüm değişiklikleri geri alır. Her zaman çağırabilirsiniz Not `GetRecordsAffected` kaç tane kaydın etkilendiğini görmek için.

Çağrı [GetRecordsAffected](#getrecordsaffected) üye işlevi tarafından en son etkilenen kayıtların sayısını belirlemek için veritabanı nesnesinin `Execute` çağırın. Örneğin, `GetRecordsAffected` silindi, güncelleştirilen veya bir eylem sorgu yürütülürken eklenen kayıtlar sayısı hakkında bilgi döndürür. Bu sayı, döndürülen cascade güncelleştirir veya sildiğinde ilişkili tablolardaki değişiklikleri yürürlükte olan yansıtmaz.

`Execute` bir kayıt kümesi döndürmüyor. Kullanarak `Execute` kayıtları seçen bir sorgu üzerinde MFC özel durum türü neden `CDaoException`. (Yok hiçbir `ExecuteSQL` üye işlevine benzer `CDatabase::ExecuteSQL`.)

##  <a name="getconnect"></a>  CDaoDatabase::GetConnect

Bağlanmak için kullanılan bağlantı dizesini almak için bu üye işlevi çağrısı `CDaoDatabase` ODBC veya ISAM veritabanı nesnesi.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

Bağlantı dizesi [açık](#open) olan bir ODBC veri kaynağında başarıyla; tersi durumda, boş bir dize. Microsoft Jet (. MDB) dize veritabanıdır her zaman boş ile kullanmak için ayarladığınız sürece `dbSQLPassThrough` seçeneği ile birlikte kullanılan [yürütme](#execute) üye işlevini veya bir kayıt kümesi açılırken kullanılan.

### <a name="remarks"></a>Açıklamalar

Dize, açık bir veritabanını veya doğrudan bir sorguda kullanılan bir veritabanının kaynak hakkında bilgi sağlar. Bağlantı dizesi, bir veritabanı türü belirticisi ve sıfır veya daha fazla parametre noktalı virgülle ayrılmış oluşur.

> [!NOTE]
>  Aracılığıyla ODBC veri kaynağına bağlanmak için MFC DAO sınıflarını kullanırken, eklenen tablonun bağlanan daha az verimlidir.

> [!NOTE]
>  Bağlantı dizesi, ODBC ve gerektiğinde belirli ISAM sürücüleri için ek bilgiler iletmek için kullanılır. İçin kullanılmaz. MDB veritabanları. Microsoft Jet veritabanı temel tablolar için bağlantı dizesi boş bir dizedir ("") dışında ne zaman bir SQL doğrudan sorgu için dönüş değerini altında yukarıda açıklandığı gibi kullanılır.

Bkz: [açık](#open) üye işlevi için bir açıklama bağlantı dizesini nasıl oluşturulur. Bağlantı dizesi ayarlandıktan sonra `Open` çağrı, daha sonra kullanabileceğiniz, türü, yol, kullanıcı kimliği, parola veya ODBC veri kaynağı veritabanının belirlemek için bu ayarı denetlemek için.

##  <a name="getname"></a>  CDaoDatabase::GetName

Mevcut bir veritabanı dosyasının adı şu anda açık veritabanının adını veya kayıtlı bir ODBC veri kaynağı adını almak için bu üye işlevini çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa veritabanının dosya adını ve tam yolunu; Aksi takdirde boş [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

Ağınızı Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, bir ağ yolu da belirtebilirsiniz; Örneğin, "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Çift ters eğik çizgi, dize sabit gereklidir, çünkü "\\" C++ kaçış karakteri olan.)

Örneğin, bu ad bir başlığa görüntülemek isteyebilirsiniz. Adı alınırken bir hata oluşursa, MFC türünde bir özel durum oluşturur. [CDaoException](../../mfc/reference/cdaoexception-class.md).

> [!NOTE]
>  Dış veritabanlarını Erişilmekte olduğunu daha iyi performans için bir Microsoft Jet veritabanı için dış veritabanı tablolarına ekleme öneririz (. MDB) yerine doğrudan veri kaynağına bağlanma.

Veritabanı türü, dosya veya yol gösteren, aşağıdaki gibi dizin tarafından belirtilir:

|PathName noktalarına...|Veritabanı türü|
|--------------------------|-------------------|
|. Dosyayı MDB|Microsoft Jet veritabanı (Microsoft Access)|
|İçeren dizin. DBF dosya|dBASE veritabanı|
|İçeren dizin. XLS dosyası|Microsoft Excel veritabanı|
|İçeren dizin. PDX dosyaları|Paradox veritabanı|
|Uygun şekilde biçimlendirilmiş metin veritabanı dosyalarını içeren dizin|Metin biçiminde veritabanı|

SQL Server ve Oracle gibi ODBC veritabanları için veritabanı bağlantı dizesi tarafından ODBC kayıtlı bir veri kaynağı adı (DSN) tanımlar.

##  <a name="getquerydefcount"></a>  CDaoDatabase::GetQueryDefCount

Veritabanının QueryDefs koleksiyonu içinde tanımlanan sorguların sayısını almak için bu üye işlevini çağırın.

```
short GetQueryDefCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanında tanımlanan sorgularının sayısı.

### <a name="remarks"></a>Açıklamalar

`GetQueryDefCount` QueryDefs koleksiyonu içindeki tüm querydefs döngü istiyorsanız kullanışlıdır. Bir koleksiyondaki belirli bir sorgu hakkında bilgi edinmek için bkz: [GetQueryDefInfo](#getquerydefinfo).

##  <a name="getquerydefinfo"></a>  CDaoDatabase::GetQueryDefInfo

Çeşitli veritabanında tanımlanan bir sorgu hakkında bilgi edinmek için bu üye işlevini çağırın.

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

*nIndex*<br/>
Dizine göre arama için veritabanının QueryDefs koleksiyonu içinde önceden tanımlanmış sorgu dizini.

*querydefinfo*<br/>
Bir başvuru bir [Cdaoquerydefınfo](../../mfc/reference/cdaoquerydefinfo-structure.md) nesnesini istenen bilgileri döndürür.

*dwInfoOptions*<br/>
Seçenekleri hangi bilgilerini almak için kayıt kümesi belirtin. Kullanılabilir seçenekler, bunlar hakkında kayıt döndüren işlev nedeni ne yanı sıra aşağıda listelenmiştir:

- (Varsayılan) AFX_DAO_PRIMARY_INFO adı, türü

- Artı AFX_DAO_SECONDARY_INFO birincil bilgileri: oluşturma tarihi, son güncelleştirme tarihi, kayıtları döndürür, güncelleştirilebilir

- AFX_DAO_ALL_INFO birincil ve ikincil bilgi artı: SQL, bağlan, ODBCTimeout

*lpszName*<br/>
Ada göre arama, veritabanında tanımlanan bir sorgu adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Bir sorgu veritabanının QueryDefs koleksiyonu dizininde veya sorgunun adı seçebilmeniz için iki işlevin sürümleri sağlanır.

Döndürülen bilgilerin açıklamasını *querydefinfo*, bkz: [Cdaoquerydefınfo](../../mfc/reference/cdaoquerydefinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzey bilgilerin istenmişse bilgilerini de önceki tüm düzeylerini alın.

##  <a name="getquerytimeout"></a>  CDaoDatabase::GetQueryTimeout

Saniye önce bağlı veritabanında sonraki işlemleri aşımına izin geçerli sayısını almak için bu üye işlevini çağırın.

```
short GetQueryTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Saniye cinsinden zaman aşımı değerini içeren bir kısa tamsayı.

### <a name="remarks"></a>Açıklamalar

Bir işlem nedeniyle ağ erişim sorunları, aşırı miktarda sorgu işleme süresi ve benzeri zaman. Ayarı etkinken, tüm açık etkiler., yeni Ekle, güncelleştirme ve silme işlemleri bununla ilişkili tüm kayıt kümelerini üzerinde `CDaoDatabase` nesne. Çağırarak geçerli zaman aşımı ayarını değiştirebilirsiniz [SetQueryTimeout](#setquerytimeout). Kayıt kümesi için bir değer açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirmeyi değiştirmez. Örneğin, sonraki [taşıma](../../mfc/reference/cdaorecordset-class.md#move) işlemleri, yeni değer kullanmayın. Varsayılan değer, başlangıçta veritabanı altyapısı başlatıldığında ayarlanır.

Sorgu zaman aşımı için'varsayılan değer Windows kayıt defterinden alınır. Hiçbir kayıt defteri ayarı varsa, varsayılan değer 60 saniyedir. Tüm veritabanları, bir sorgu zaman aşımı değerini ayarlama özelliğini destekler. Sorgu zaman aşımı değerini 0 olarak ayarlarsanız, hiçbir zaman aşımı oluşur; ve veritabanı ile iletişimi yanıt vermeyebilir. Bu davranış, geliştirme sırasında yararlı olabilir. Çağrı başarısız olursa, MFC türünde bir özel durum oluşturur. [CDaoException](../../mfc/reference/cdaoexception-class.md).

İlgili bilgiler için DAO Yardımı'nda "QueryTimeout özelliği" konusuna bakın.

##  <a name="getrecordsaffected"></a>  CDaoDatabase::GetRecordsAffected

En son çağrı tarafından etkilenen kayıtların sayısını belirlemek için bu üye işlevini çağırın [yürütme](#execute) üye işlevi.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Dönüş Değeri

Etkilenen kayıtların sayısını içeren büyük bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer silindi, güncelleştirilen veya çalıştıran bir eylem sorgu tarafından eklenen kayıt sayısını içerir `Execute`. Bu sayı, döndürülen cascade güncelleştirir veya sildiğinde ilişkili tablolardaki değişiklikleri yürürlükte olan yansıtmaz.

İlgili bilgiler için DAO Yardımı'nda "RecordsAffected özelliği" konusuna bakın.

##  <a name="getrelationcount"></a>  CDaoDatabase::GetRelationCount

Tanımlanan veritabanındaki tablolar arasında ilişkiler sayısını almak için bu üye işlevini çağırın.

```
short GetRelationCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tanımlanan veritabanındaki tablolar arasında ilişkiler sayısı.

### <a name="remarks"></a>Açıklamalar

`GetRelationCount` İlişkiler koleksiyonu veritabanının tüm tanımlı ilişkiler döngü gerektiğinde kullanışlıdır. Bir koleksiyondaki belirli bir ilişkisi hakkında bilgi edinmek için bkz: [GetRelationInfo](#getrelationinfo).

Bir ilişkinin bir konsepti açıklamak amacıyla bir değişecekse ve bire çok ilişkisi olabilir bir Ürünler tablosuna göz önünde bulundurun. Bu ilişkide birden fazla ürün bir tedarikçi sağlayabilirsiniz. Diğer ilişkileri bire bir ve bire çok.

##  <a name="getrelationinfo"></a>  CDaoDatabase::GetRelationInfo

Veritabanı ilişkileri koleksiyonda belirtilen bir ilişki hakkında bilgi edinmek için bu üye işlevini çağırın.

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

*nIndex*<br/>
Dizine göre arama için veritabanının ilişkiler koleksiyonu ilişki nesnesinde dizini.

*relinfo*<br/>
Bir başvuru bir [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesini istenen bilgileri döndürür.

*dwInfoOptions*<br/>
Alınacak ilişki hakkında bilgileri belirtmenize seçenekleri. Kullanılabilir seçenekler, hangi bunlar hakkında ilişki döndürülecek işlev neden yanı sıra aşağıda listelenmiştir:

- Ad, tablo, yabancı tablo AFX_DAO_PRIMARY_INFO (varsayılan)

- Alan bilgilerini AFX_DAO_SECONDARY_INFO öznitelikleri

Alan bilgiler bir [Cdaorelationfieldınfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) birincil tablo ilişkisinde kullanılan alanları içeren nesne.

*lpszName*<br/>
Ada göre arama ilişkisi nesne adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Bu işlevin iki sürümü, dizin veya ada göre erişim sağlar. Döndürülen bilgilerin açıklamasını *relinfo*, bkz: [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzeyde bilgi istemesi durumunda, tüm önceki düzeylerinde de bilgi alın.

> [!NOTE]
>  İlişki cascade işlemlerini etkinleştirmek için nesnenin öznitelikleri ayarlarsanız (`dbRelationUpdateCascades` veya `dbRelationDeleteCascades`), Microsoft Jet veritabanı altyapısı, otomatik olarak güncelleştirir veya bir kayıtları siler veya daha fazla tablo değişiklikler yapıldığında ilgili birincil anahtar tablolar. Örneğin, bir Customers ve Orders tablosunu arasında bir cascade delete ilişkisi oluşturmanız varsayalım. Müşteriler tablosundan kayıtları sildiğinizde, o müşterilerle ilgili Siparişler tablosunda kayıtlar da silinir. Ayrıca, Siparişler tablosu ve diğer tablolar arasındaki art arda silme ilişkileri kurmak, Müşteriler tablosundan kayıtları sildiğinizde bu tablolardan kayıtları otomatik olarak silinir.

##  <a name="gettabledefcount"></a>  CDaoTableDefInfo

Veritabanında tanımlanan tablo sayısını almak için bu üye işlevini çağırın.

```
short GetTableDefCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanında tanımlanan tabledefs sayısı.

### <a name="remarks"></a>Açıklamalar

`GetTableDefCount` veritabanının TableDefs koleksiyonu içindeki tüm tabledefs döngü istiyorsanız kullanışlıdır. Bir koleksiyondaki belirli bir tabloda hakkında bilgi edinmek için bkz: [GetTableDefInfo](#gettabledefinfo).

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

*nIndex*<br/>
Dizine göre arama için veritabanının TableDefs koleksiyonu tabledef nesnesinde dizini.

*tabledefinfo*<br/>
Bir başvuru bir [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) nesnesini istenen bilgileri döndürür.

*dwInfoOptions*<br/>
Seçenekler hangi bilgilerini almak için tabloyu belirtin. Kullanılabilir seçenekler, hangi bunlar hakkında ilişki döndürülecek işlev neden yanı sıra aşağıda listelenmiştir:

- Güncelleştirilebilir, AFX_DAO_PRIMARY_INFO (varsayılan) ad öznitelikleri

- Artı AFX_DAO_SECONDARY_INFO birincil bilgileri: kaynak tablo adı, bağlantı oluşturma tarihi, son güncelleştirme tarihi

- AFX_DAO_ALL_INFO birincil ve ikincil bilgi artı: doğrulama kuralı, doğrulama metin kayıt sayısı

*lpszName*<br/>
Ada göre arama tabledef nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

Bir tablo veritabanının TableDefs koleksiyonu dizininde veya tablonun adını seçebilmeniz için iki işlevin sürümleri sağlanır.

Döndürülen bilgilerin açıklamasını *tabledefinfo*, bkz: [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzeyde bilgi isterse de önceki tüm düzeylerde hakkında bilgi alın.

> [!NOTE]
>  AFX_DAO_ALL_INFO seçeneği elde yavaş olabiliyor bilgilerini sağlar. Bu durumda, tablodaki kaydın sayım çok zaman birçok kayıtlar varsa alıcı olabilir.

##  <a name="getversion"></a>  CDaoDatabase::GetVersion

Microsoft Jet veritabanı dosyasının sürümünü belirlemek için bu üye işlevini çağırın.

```
CString GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesneyle ilişkili veritabanı dosyasının sürümünü gösterir.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer "AnaSürüm.altsürüm"; biçiminde sürüm numarasını temsil eder. Örneğin, "3.0". Ürün sürüm numarasını (örneğin, 3.0), sürüm numarası (3), nokta ve sürüm numarasını (0) oluşur. Bugüne 1.0, 1.1, 2.0 ve 3.0 sürümleridir.

İlgili bilgiler için DAO Yardımı'nda "Version özelliği" konusuna bakın.

##  <a name="isopen"></a>  CDaoDatabase::IsOpen

Belirlemek için bu üye işlevi çağrısı olup olmadığını `CDaoDatabase` nesne bir veritabanı üzerinde şu anda açık değil.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `CDaoDatabase` nesnedir açık; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_pdaodatabase"></a>  CDaoDatabase::m_pDAODatabase

DAO veritabanı nesnesinin altındaki OLE arabirimi için bir işaretçi içeren `CDaoDatabase` nesne.

### <a name="remarks"></a>Açıklamalar

DAO arabirimi doğrudan erişim gerekiyorsa, bu işaretçi kullanın.

DAO çağırma hakkında bilgi için doğrudan bkz [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

##  <a name="m_pworkspace"></a>  CDaoDatabase::m_pWorkspace

Bir işaretçi içeren [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) veritabanı nesnesi içeren nesne.

### <a name="remarks"></a>Açıklamalar

Çalışma alanına doğrudan erişim gerekiyorsa, bu işaretçi kullanın; örneğin, çalışma alanınızın veritabanı koleksiyonu içindeki diğer veritabanı nesnelerine işaretçiler elde edilir.

##  <a name="open"></a>  CDaoDatabase::Open

Yeni oluşturulan başlatmak için bu üye işlevi çağırmanız gerekir `CDaoDatabase` varolan bir veritabanını temsil eden nesne.

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Mevcut bir Microsoft Jet adını bir dize ifadesi (. Veritabanı dosyayı MDB). Dosya adı uzantısına sahiptir, bu gereklidir. Ağınızı Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, bir ağ yolu gibi belirtebilirsiniz "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Çift ters eğik çizgi, dize sabit gereklidir, çünkü "\\" C++ kaçış karakteri olan.)

Kullanırken bazı önemli noktalar geçerlidir *lpszName*. Varsa bu:

- Zaten başka bir kullanıcı tarafından bir özel durum türü, MFC oluşturur özel erişim için açık bir veritabanı başvurduğu [CDaoException](../../mfc/reference/cdaoexception-class.md). Veritabanı kullanılamaz olduğunu bilmek, kullanıcı izin vermek için o özel durumu yakalar.

- Boş bir dizedir ("") ve *lpszConnect* "ODBC;", kullanıcı bir veritabanı seçebilmeniz için tüm kayıtlı ODBC veri kaynağı adları listeleyen bir iletişim kutusu görüntülenir. ODBC veri kaynaklarına doğrudan bağlantı kaçınmalısınız; eklenen tablonun kullanın.

- Aksi takdirde geçerli ODBC veri kaynağı adı, bir özel durum türü, MFC oluşturur veya var olan veritabanı başvurmuyor `CDaoException`.

> [!NOTE]
>  DAOERR DAO hata kodları hakkında daha fazla ayrıntı için bkz. H dosyası. İlgili bilgiler için "Yakalanabilir veri erişimi hatası" DAO Yardım konusuna bakın.

*bExclusive*<br/>
Veritabanı, veritabanı için paylaşılan erişim açılmasını ise özel (paylaşılmayan) erişim ve FALSE açılmasını ise TRUE olan bir Boole değeri. Bu bağımsız değişken atlarsanız, veritabanı için paylaşılan erişim açılır.

*bReadOnly*<br/>
Veritabanı, veritabanı için okuma/yazma erişimi ile açılması için ise salt okunur erişim ve FALSE açılmasını ise TRUE olan bir Boole değeri. Bu bağımsız değişken atlarsanız, veritabanının okuma/yazma erişimi için açılır. Bu özniteliğe bağımlı tüm kayıt kümelerini devralır.

*lpszConnect*<br/>
Veritabanını açmak için kullanılan bir dize ifadesi. Bu dize ODBC oluşturan bağımsız değişkenleri bağlanın. Bir kaynak dizesi sağlamak için özel ve salt okunur bağımsız değişken sağlamalısınız. Veritabanı Microsoft Jet veritabanı ise (. MDB), bu dize boşsa (""). Varsayılan değer sözdizimi — **_T**("") — ANSI yanı sıra Unicode taşınabilirlik derlemelerinin uygulamanızı sağlar.

### <a name="remarks"></a>Açıklamalar

`Open` Veritabanı, temel alınan DAO nesnesiyle ilişkilendirir. Veritabanı nesnesi başlayana kadar kayıt kümesi, tabledef veya querydef nesneleri oluşturmak için kullanamazsınız. `Open` Veritabanı nesnesi, ilişkili çalışma alanınızın veritabanı derlemesine ekler.

Parametreleri aşağıdaki şekilde kullanın:

- Microsoft Jet açarsa (. MDB) veritabanı, kullanım *lpszName* parametre ve boş bir dize için geçişi *lpszConnect* parametresi veya pass biçiminde bir parola dizesi "; PWD parola = "veritabanı, parola korumalı ise (. MDB veritabanları yalnızca).

- ODBC veri kaynağını açıyorsanız, geçerli bir ODBC bağlantı dizesini geçirmenizi *lpszConnect* ve boş bir dize içinde *lpszName*.

İlgili bilgiler için DAO Yardımı'nda "OpenDatabase yöntemi" konusuna bakın.

> [!NOTE]
>  ISAM veritabanları ve ODBC veri kaynakları gibi dış veritabanlarını erişirken daha iyi performans için bir Microsoft Jet motoru veritabanı dış veritabanı tablolarına ekleme önerilir (. MDB) yerine doğrudan veri kaynağına bağlanma.

Örneğin, DBMS konak kullanılamıyorsa, zaman aşımı bağlanma girişimi için mümkündür. Bağlantı denemesi başarısız olursa `Open` türünde bir özel durum oluşturduğunda [CDaoException](../../mfc/reference/cdaoexception-class.md).

Kalan açıklamalar yalnızca ODBC veritabanları için geçerlidir:

Veritabanı bir ODBC veritabanı ile parametrelerinde olup olmadığını, `Open` çağrı bağlantı kurmak için yeterli bilgi içermiyor, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açılır. Çağırdığınızda `Open`, bağlantı dizenizi *lpszConnect*, özel olarak depolanır ve nolu telefonu arayarak [GetConnect](#getconnect) üye işlevi.

İsterseniz, çağırmadan önce kendi iletişim kutusunu açabilirsiniz `Open` kullanıcıdan bir parola gibi bilgileri almak için daha sonra bu bilgileri geçirmek için bağlantı dizesi ekleyin `Open`. Veya sonraki yeniden kullanabilmesi (belki de Windows kayıt defterinde) geçirdiğiniz bağlantı dizesini, uygulama çağrıları zaman isteyebileceğiniz `Open` üzerinde bir `CDaoDatabase` nesne.

Birden çok oturum açma yetkilendirme düzeyi için bağlantı dizesini de kullanabilirsiniz (her biri için farklı bir `CDaoDatabase` nesne) ya da diğer veritabanı özgü bilgileri iletmek için.

##  <a name="setquerytimeout"></a>  CDaoDatabase::SetQueryTimeout

Saniye önce bağlı veritabanı zaman aşımı sonraki işlemlerde izin vermek için varsayılan sayısını geçersiz kılma için bu üye işlevini çağırın.

```
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>Parametreler

*nSeconds*<br/>
Bir sorgu girişiminden önce izin vermek için saniye sayısını zaman aşımına uğradı.

### <a name="remarks"></a>Açıklamalar

Bir işlem nedeniyle ağ erişim sorunları, aşırı miktarda sorgu işleme süresi ve benzeri zaman. Çağrı `SetQueryTimeout` kümenizin açmadan önce veya kümesinin çağırmadan önce [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [güncelleştirme](../../mfc/reference/cdaorecordset-class.md#update), veya [Sil](../../mfc/reference/cdaorecordset-class.md#delete) sorgu değiştirmek istiyorsanız üye işlevleri zaman aşımı değeri. Bu ayar tüm sonraki etkiler [açık](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`, `Update`, ve `Delete` bununla ilişkili tüm kayıt kümelerini çağrıları `CDaoDatabase` nesne. Kayıt kümesi için bir değer açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirmeyi değiştirmez. Örneğin, sonraki [taşıma](../../mfc/reference/cdaorecordset-class.md#move) işlemleri, yeni değer kullanmayın.

Sorgu zaman aşımı için'varsayılan değer 60 saniyedir. Tüm veritabanları, bir sorgu zaman aşımı değerini ayarlama özelliğini destekler. Sorgu zaman aşımı değerini 0 olarak ayarlarsanız, hiçbir zaman aşımı oluşur; veritabanı ile iletişimi yanıt vermemeye başlayabilir. Bu davranış, geliştirme sırasında yararlı olabilir.

İlgili bilgiler için DAO Yardımı'nda "QueryTimeout özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoWorkspace Sınıfı](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
