---
title: CDaoDatabase Sınıfı
ms.date: 09/17/2019
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
ms.openlocfilehash: debba137878da49921df83da7630003a7d62db2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369013"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase Sınıfı

Veri Erişim Nesneleri (DAO) kullanarak Access veritabanına olan bağlantıyı temsil eder. DAO, Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|Bir `CDaoDatabase` nesne inşa eder. Nesneyi veritabanına bağlamak için arayın. `Open`|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoDatabase::CanTransact](#cantransact)|Veritabanı hareketleri destekliyorsa sıfırsız döndürür.|
|[CDaoDatabase::CanUpdate](#canupdate)|`CDaoDatabase` Nesne güncel değilse sıfırsız döndürür (salt okunur değil).|
|[CDaoDatabase::Kapat](#close)|Veritabanı bağlantısını kapatır.|
|[CDaoDatabase::Oluştur](#create)|Altta yatan DAO veritabanı nesnesini oluşturur `CDaoDatabase` ve nesneyi başharfe amer.|
|[CDaoDatabase::CreateRelation](#createrelation)|Veritabanındaki tablolar arasında yeni bir ilişki tanımlar.|
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|Veritabanının QueryDefs koleksiyonunda kaydedilen bir querydef nesnesini siler.|
|[CDaoDatabase::Deleteİlişki](#deleterelation)|Veritabanındaki tablolar arasındaki varolan ilişkiyi siler.|
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|Veritabanındaki tablonun tanımını siler. Bu, gerçek tabloyu ve tüm verilerini siler.|
|[CDaoDatabase::Yürüt](#execute)|Eylem sorgusu yürütür. Sonuçları `Execute` döndüren bir sorgu için çağrı bir özel durum oluşturur.|
|[CDaoDatabase::GetConnect](#getconnect)|Nesneyi veritabanına bağlamak `CDaoDatabase` için kullanılan bağlantı dizesini döndürür. ODBC için kullanılır.|
|[CDaoDatabase::GetName](#getname)|Şu anda kullanılmakta olan veritabanının adını döndürür.|
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|Veritabanı için tanımlanan sorgu sayısını döndürür.|
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|Veritabanında tanımlanan belirli bir sorgu yla ilgili bilgileri verir.|
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|Veritabanı sorgusu işlemlerinin zaman dolana bakacağı saniye sayısını döndürür. Sonraki tüm açıkları etkiler, yeni ekleme, güncelleştirme ve güncelleştirme işlemleri ve aramalar gibi `Execute` ODBC veri kaynaklarındaki diğer işlemleri (yalnızca) etkiler.|
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|Son güncelleştirme, düzenleme veya ekleme işleminden veya `Execute`bir çağrıdan etkilenen kayıt sayısını verir.|
|[CDaoDatabase::GetRelationCount](#getrelationcount)|Veritabanındaki tablolar arasında tanımlanan ilişki sayısını döndürür.|
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|Veritabanındaki tablolar arasında tanımlanan belirli bir ilişki yle ilgili bilgileri verir.|
|[CDaoDatabase::GetTableDefCount](#gettabledefcount)|Veritabanında tanımlanan tablo sayısını döndürür.|
|[CDaoDatabase::GetTableDefInfo](#gettabledefinfo)|Veritabanında belirtilen bir tablo yla ilgili bilgileri verir.|
|[CDaoDatabase::GetVersion](#getversion)|Veritabanı yla ilişkili veritabanı altyapısının sürümünü döndürür.|
|[CDaoDatabase::Açık](#isopen)|Nesne şu anda bir veritabanına `CDaoDatabase` bağlıysa sıfırsız döndürür.|
|[CDaoDatabase::Aç](#open)|Veritabanına bağlantı kurar.|
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|Veritabanı sorgusu işlemlerinin (yalnızca ODBC veri kaynaklarında) zaman dolandırılacak saniye sayısını ayarlar. Sonraki tüm açık, yeni ekleme, güncelleştirme ve silme işlemlerini etkiler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoVeritabanı::m_pDAODatabase](#m_pdaodatabase)|Altta yatan DAO veritabanı nesnesine bir işaretçi.|
|[CDaoVeritabanı::m_pWorkspace](#m_pworkspace)|Veritabanını içeren ve işlem alanını tanımlayan [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine işaretçi.|

## <a name="remarks"></a>Açıklamalar

Desteklenen veritabanı biçimleri hakkında daha fazla bilgi için [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) üye işlevine bakın. [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) `CDaoDatabase` nesnesi tarafından temsil edilen belirli bir "çalışma alanında" bir anda etkin bir veya daha fazla nesneniz olabilir. Çalışma alanı, Veritabanları koleksiyonu adı verilen açık veritabanı nesneleri koleksiyonunu korur.

## <a name="usage"></a>Kullanım

Kayıt kümesi nesneleri oluşturduğunuzda, veritabanı nesnelerini dolaylı olarak oluşturabilirsiniz. Ancak veritabanı nesnelerini açıkça oluşturabilirsiniz. Varolan bir veritabanını `CDaoDatabase`açıkça kullanmak için aşağıdakilerden birini yapın:

- Açık `CDaoDatabase` bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine işaretçi geçerek bir nesne oluştur.

- Veya çalışma `CDaoDatabase` alanını belirtmeden bir nesne oluşturun (MFC geçici bir çalışma alanı nesnesi oluşturur).

Yeni bir Microsoft Jet oluşturmak için (. MDB) veritabanı, `CDaoDatabase` bir nesne oluşturmak ve üye [işlev oluştur.](#create) Sonra *aramayın.* `Open` `Create`

Varolan bir veritabanını `CDaoDatabase` açmak için bir nesne oluşturmak ve [Açık](#open) üye işlevini çağırın.

Bu tekniklerden herhangi biri, DAO veritabanı nesnesini çalışma alanının Veritabanları koleksiyonuna ekler ve verilere bağlantı açar. Daha sonra [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)veya [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesneleri bağlı veritabanında çalışmak için, bu nesneler için oluşturucular nesnenize `CDaoDatabase` bir işaretçi geçmek oluşturmak. Bağlantıyı kullanmayı bitirdiğinizde, [Kapat](#close) üye işlevini arayın `CDaoDatabase` ve nesneyi yok edin. `Close`daha önce kapatmadığınız kayıt kümelerini kapatır.

## <a name="transactions"></a>İşlemler

Veritabanı işlem işleme çalışma alanı düzeyinde sağlanır - [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)bakın , [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), `CDaoWorkspace`ve sınıfın [Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) üye işlevleri .

## <a name="odbc-connections"></a>ODBC Bağlantıları

ODBC veri kaynaklarıyla çalışmanın önerilen yolu, bir Microsoft Jet'ine () harici tablolar eklemektir. MDB) veritabanı.

## <a name="collections"></a>Koleksiyonlar

Her veritabanı tabledef, querydef, recordset ve ilişki nesnelerinin kendi koleksiyonlarını tutar. Sınıf, `CDaoDatabase` bu nesneleri işlemek için üye işlevleri sağlar.

> [!NOTE]
> Nesneler MFC veritabanı nesnesinde değil, DAO'da depolanır. MFC, tablodef, querydef ve recordset nesneleri için sınıflar sağlar, ancak ilişki nesneleri için değil.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="cdaodatabasecantransact"></a><a name="cantransact"></a>CDaoDatabase::CanTransact

Veritabanının hareketlere izin verip vermeyemeyeceğini belirlemek için bu üye işlevini arayın.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanı hareketleri destekliyorsa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Hareketler veritabanının çalışma alanında yönetilir.

## <a name="cdaodatabasecanupdate"></a><a name="canupdate"></a>CDaoDatabase::CanUpdate

Nesnenin `CDaoDatabase` güncelleştirmelere izin verip vermeyemeyeceğini belirlemek için bu üye işlevi arayın.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne güncelleştirmeleri `CDaoDatabase` izin veriyorsa sıfır olmayan; aksi takdirde 0, `CDaoDatabase` nesneyi açtığınızda *bReadOnly* TRUE geçti ya da veritabanı kendisi okunur olduğunu belirten. [Açık](#open) üye işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veritabanı güncellenebilirliği hakkında daha fazla bilgi için DAO Yardım'daki "Güncellenebilir Özellik" konusuna bakın.

## <a name="cdaodatabasecdaodatabase"></a><a name="cdaodatabase"></a>CDaoDatabase::CDaoDatabase

Bir `CDaoDatabase` nesne inşa eder.

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>Parametreler

*pÇalışma alanı*<br/>
Yeni veritabanı `CDaoWorkspace` nesnesi içerecek nesneye bir işaretçi. NULL varsayılan değerini kabul ederseniz, oluşturucu varsayılan `CDaoWorkspace` DAO çalışma alanı kullanan geçici bir nesne oluşturur. [m_pWorkspace](#m_pworkspace) veri üyesi aracılığıyla çalışma alanı nesnesine bir işaretçi alabilirsiniz.

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturduktan sonra, yeni bir Microsoft Jet oluşturuyorsanız (. MDB) veritabanı, nesnenin [Create](#create) üye işlevini arayın. Bunun yerine varolan bir veritabanını açıyorsanız, nesnenin [Açık](#open) üye işlevini arayın.

Nesneyle bitirdiğinizde, [Yakın](#close) üye işlevini aramalı ve `CDaoDatabase` nesneyi yok etmelisiniz.

Nesneyi belge sınıfınıza gömmeyi `CDaoDatabase` uygun bulabilirsiniz.

> [!NOTE]
> Bir `CDaoDatabase` [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesini varolan `CDaoDatabase` bir nesneye işaretçi geçmeden açarsanız, nesne de dolaylı olarak oluşturulur. Kayıt kümesi nesnesini kapattığınızda bu veritabanı nesnesi kapatılır.

## <a name="cdaodatabaseclose"></a><a name="close"></a>CDaoDatabase::Kapat

Veritabanının bağlantısını kesmek ve veritabanıyla ilişkili açık kayıt kümelerini, tabledef'leri ve querydefs'i kapatmak için bu üye işlevini arayın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağırmadan önce bu nesneleri kendiniz kapatmak iyi bir uygulamadır. Nesneyi `CDaoDatabase` kapatma, nesneyi ilişkili [çalışma alanındaki](../../mfc/reference/cdaoworkspace-class.md)Veritabanları koleksiyonundan kaldırır. Nesneyi yok `Close` `CDaoDatabase` etmediğinden, aynı veritabanını veya farklı bir veritabanını açarak nesneyi yeniden kullanabilirsiniz.

> [!CAUTION]
> Bir veritabanını kapatmadan önce [Tüm](../../mfc/reference/cdaorecordset-class.md#update) açık kayıt `Close` kümesi nesnelerinde Üye işlevin ilerkisini (bekleyen ayarlamalar varsa) ve üye işlevi arayın. [Yığında CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) veya `CDaoDatabase` nesneleri bildiren bir işlevden çıkarsanız, veritabanı kapatılır, kaydedilmemiş değişiklikler kaybolur, bekleyen tüm hareketler geri alınır ve verileriniz için bekleyen tüm değişiklikler kaybolur.

> [!CAUTION]
> Kayıt kümesi nesneleri açıkken bir veritabanı nesnesini kapatmaya çalışırsanız veya belirli bir çalışma alanına ait veritabanı nesneleri açıkken bir çalışma alanı nesnesini kapatmaya çalışırsanız, bu kayıt kümesi nesneleri kapatılır ve bekleyen güncelleştirmeler veya denetimler geri alınır. Bir çalışma alanı nesnesini, veritabanı nesneleri açıkken kapatmaya çalışırsanız, işlem o belirli çalışma alanı nesnesine ait tüm veritabanı nesnelerini kapatır ve bu da kapalı kayıt kümesi nesnelerinin kapatılmasına neden olabilir. Veritabanı nesnenizi kapatmazsanız, Hata ayıklama yapılığında Bir söz çözüm çağrısını müştürü

Veritabanı nesnesi bir işlevin kapsamı dışında tanımlanırsa ve işlevi kapatmadan çıkarsanız, veritabanı nesnesi açıkça kapanana veya tanımlandığı modül kapsam dışında kalana kadar açık kalır.

## <a name="cdaodatabasecreate"></a><a name="create"></a>CDaoDatabase::Oluştur

Yeni bir Microsoft Jet oluşturmak için (. MDB) veritabanı, bir `CDaoDatabase` nesne inşa ettikten sonra bu üye işlevi arayın.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Oluşturduğunuz veritabanı dosyasının adı olan dize ifadesi. "C:\\\MYDB" gibi tam yol ve dosya adı olabilir. MDB". Bir isim vermelisin. Dosya adı uzantısı sağlamazsanız, . MDB eklenir. Ağınız tek düzen adlandırma kuralını (UNC) destekliyorsa,\\\\\\"\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB" gibi bir ağ yolu da belirtebilirsiniz. Yalnızca Microsoft Jet (. MDB) veritabanı dosyaları bu üye işlevi kullanılarak oluşturulabilir. (Çift backslashes dize literals\\gereklidir çünkü " " C++ kaçış karakteridir.)

*lpszYerele*<br/>
Veritabanı oluşturmak için harmanlama sırası belirtmek için kullanılan bir dize ifadesi. Varsayılan değer: `dbLangGeneral`. Olası değerler şunlardır:

- `dbLangGeneral`İngilizce, Almanca, Fransızca, Portekizce, İtalyanca ve Modern İspanyolca

- `dbLangArabic`Arapça

- `dbLangCyrillic`Rusça

- `dbLangCzech`Çekçe

- `dbLangDutch`Hollanda dili

- `dbLangGreek`Yunanca

- `dbLangHebrew`İbranice

- `dbLangHungarian`Macarca

- `dbLangIcelandic`İzlanda dili

- `dbLangNordic`İskandinav dilleri (yalnızca Microsoft Jet veritabanı altyapısı sürümü 1.0)

- `dbLangNorwdan`Norveççe ve Danimarkaca

- `dbLangPolish`Lehçe

- `dbLangSpanish`Geleneksel İspanyolca

- `dbLangSwedfin`İsveççe ve Fince

- `dbLangTurkish`Türkçe

*Dwoptions*<br/>
Bir veya daha fazla seçeneği gösteren bir sonsayı. Olası değerler şunlardır:

- `dbEncrypt`Şifreli bir veritabanı oluşturun.

- `dbVersion10`Microsoft Jet veritabanı sürüm 1.0 ile bir veritabanı oluşturun.

- `dbVersion11`Microsoft Jet veritabanı sürüm 1.1 ile bir veritabanı oluşturun.

- `dbVersion20`Microsoft Jet veritabanı sürüm 2.0 ile bir veritabanı oluşturun.

- `dbVersion30`Microsoft Jet veritabanı sürüm 3.0 ile bir veritabanı oluşturun.

Şifreleme sabitini atlarsanız, şifrelenmemiş bir veritabanı oluşturulur. Yalnızca bir sürüm sabiti belirtebilirsiniz. Bir sürüm sabitini atlarsanız, Microsoft Jet veritabanı sürüm 3.0'ı kullanan bir veritabanı oluşturulur.

> [!CAUTION]
> Bir veritabanı şifrelenmemişse, kullanıcı/parola güvenliğini uygulasanız bile veritabanını oluşturan ikili disk dosyasını doğrudan okumak mümkündür.

### <a name="remarks"></a>Açıklamalar

`Create`veritabanı dosyasını ve altta yatan DAO veritabanı nesnesini oluşturur ve C++ nesnesini açar. Nesne ilişkili çalışma alanının Veritabanları koleksiyonuna eklenir. Veritabanı nesnesi açık durumda; sonra aramayın. `Open*` `Create`

> [!NOTE]
> Ile, `Create`yalnızca Microsoft Jet oluşturabilirsiniz (. MDB) veritabanları. ISAM veritabanları veya ODBC veritabanları oluşturamazsınız.

## <a name="cdaodatabasecreaterelation"></a><a name="createrelation"></a>CDaoDatabase::CreateRelation

Veritabanındaki birincil tablodaki bir veya daha fazla alan la yabancı bir tablodaki (veritabanındaki başka bir tablo) bir veya daha fazla alan arasında ilişki kurmak için bu üye işlevi arayın.

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

*Lpszname*<br/>
İlişki nesnesinin benzersiz adı. Ad bir harfle başlamalı ve en fazla 40 karakter içerebilir. Sayıları içerebilir ve karakterleri alt çizebilir, ancak noktalama işareti veya boşluk içeremez.

*lpszTable*<br/>
İlişkideki birincil tablonun adı. Tablo yoksa, MFC [cdaoException](../../mfc/reference/cdaoexception-class.md)türübir özel durum atar.

*lpszForeignTable*<br/>
İlişkideki yabancı tablonun adı. Tablo yoksa, MFC türünden `CDaoException`bir özel durum atar.

*lAttributes*<br/>
İlişki türü hakkında bilgi içeren uzun bir değer. Bu değeri, diğer şeylerin yanı sıra başvuru bütünlüğünü zorlamak için kullanabilirsiniz. Aşağıdaki değerlerden herhangi birini birleştirmek için bitwise-OR işleci **(&#124;) **kullanabilirsiniz (kombinasyon mantıklı olduğu sürece):

- `dbRelationUnique`İlişki bire birdir.

- `dbRelationDontEnforce`İlişki zorlanmaz (başvuru bütünlüğü yoktur).

- `dbRelationInherited`İlişki, iki eklenmiş tabloiçeren geçerli olmayan bir veritabanında vardır.

- `dbRelationUpdateCascade`Güncelleştirmeler basamakla yıkacak (basamaklı daha fazla bilgi için Açıklamalar'a bakın).

- `dbRelationDeleteCascade`Silmeler basamaklanacak.

*lpszField*<br/>
Birincil tablodaki bir alanın adını içeren null-sonlandırılan dize işaretçisi *(lpszTable*tarafından adlandırılır).

*lpszForeignField*<br/>
Yabancı tablodaki bir alanın adını içeren null-sonlandırılan dize için bir işaretçi *(lpszForeignTable*tarafından adlandırılır).

*relinfo*<br/>
Oluşturmak istediğiniz ilişki hakkında bilgi içeren bir [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

İlişki, dış veritabanından bir sorgu veya eklenmiş bir tablo içeremez.

İlişki iki tablonun her birinde bir alan içeriyorsa işlevin ilk sürümünü kullanın. İlişki birden çok alan içeriyorsa ikinci sürümü kullanın. Bir ilişkideki en fazla alan sayısı 14'tür.

Bu eylem altta yatan bir DAO ilişki nesnesi oluşturur, ancak MFC'nin ilişki nesnelerinin kapsülletistirimi sınıf `CDaoDatabase`içinde bulunduğundan bu bir MFC uygulama ayrıntısidir. MFC ilişkiler için bir sınıf sağlamaz.

İlişki nesnesinin özniteliklerini basamaklı işlemleri etkinleştirmek için ayarlarsanız, veritabanı altyapısı ilgili birincil anahtar tablolarında değişiklik yapıldığında bir veya daha fazla diğer tablodaki kayıtları otomatik olarak güncelleştirir veya siler.

Örneğin, Müşteriler tablosu ile Siparişler tablosu arasında basamaklı silme ilişkisi oluşturduğunuzu varsayalım. Müşteriler tablosundaki kayıtları sildiğinizde, bu müşteriyle ilgili Siparişler tablosundaki kayıtlar da silinir. Ayrıca, Siparişler tablosu ile diğer tablolar arasında basamaklı silme ilişkileri kurarsanız, Müşteriler tablosundaki kayıtları sildiğinizde bu tablolardaki kayıtlar otomatik olarak silinir.

İlgili bilgiler için DAO Yardım'daki "CreateRelation Method" konusuna bakın.

## <a name="cdaodatabasedeletequerydef"></a><a name="deletequerydef"></a>CDaoDatabase::DeleteQueryDef

Belirtilen querydef 'i ( kayıtlı sorgu) nesnenin `CDaoDatabase` QueryDefs koleksiyonundan silmek için bu üye işlevini arayın.

```
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Silinecek kaydedilen sorgunun adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, bu sorgu artık veritabanında tanımlanmaz.

querydef nesneleri oluşturma hakkında bilgi için [cDaoQueryDef sınıfına](../../mfc/reference/cdaoquerydef-class.md)bakın. Bir querydef `CDaoDatabase` `CDaoQueryDef` nesnesi, nesneyi oluşturarak veritabanı nesnesine bir işaretçi geçirdiğinizde belirli bir nesneyle ilişkilendirilmeye neden olur.

## <a name="cdaodatabasedeleterelation"></a><a name="deleterelation"></a>CDaoDatabase::Deleteİlişki

Veritabanı nesnesinin İlişkiler koleksiyonundan varolan bir ilişkiyi silmek için bu üye işlevi arayın.

```
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Silme ilişkisinin adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, ilişki artık yok.

İlgili bilgiler için DAO Yardım'daki "Silme Yöntemi" konusuna bakın.

## <a name="cdaodatabasedeletetabledef"></a><a name="deletetabledef"></a>CDaoDatabase::DeleteTableDef

Belirtilen tabloyu ve tüm verilerini nesnenin `CDaoDatabase` TableDefs koleksiyonundan silmek için bu üye işlevi arayın.

```
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Silmek için tabledef adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, bu tablo artık veritabanında tanımlı değildir.

> [!NOTE]
> Sistem tablolarını silmemeye çok dikkat edin.

tabledef nesneleri oluşturma hakkında bilgi için [cDaoTableDef sınıfına](../../mfc/reference/cdaotabledef-class.md)bakın. Bir tabledef `CDaoDatabase` `CDaoTableDef` nesnesi, nesneyi oluşturarak veritabanı nesnesine bir işaretçi geçirdiğinizde belirli bir nesneyle ilişkilendirilmeye neden olur.

İlgili bilgiler için DAO Yardım'daki "Silme Yöntemi" konusuna bakın.

## <a name="cdaodatabaseexecute"></a><a name="execute"></a>CDaoDatabase::Yürüt

Eylem sorgusu çalıştırmak veya veritabanında bir SQL deyimi yürütmek için bu üye işlevi arayın.

```
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Parametreler

*Lpszsql*<br/>
Yürütmek için geçerli bir SQL komutu içeren null-sonlandırılan dize işaretçisi.

*nSeçenekler*<br/>
Sorgunun bütünlüğüyle ilgili seçenekleri belirten bir sonsyon. Aşağıdaki sabitlerden herhangi birini birleştirmek için bitwise-OR işleci **(&#124;) **kullanabilirsiniz (kombinasyon mantıklı olması `dbInconsistent` `dbConsistent`koşuluyla — örneğin, birleşemezsiniz):

- `dbDenyWrite`Diğer kullanıcılara yazma izni verme.

- `dbInconsistent`(Varsayılan) Tutarsız güncelleştirmeler.

- `dbConsistent`Tutarlı güncellemeler.

- `dbSQLPassThrough`SQL geçiş. SQL deyiminin işlenmek üzere bir ODBC veri kaynağına geçirilmesine neden olur.

- `dbFailOnError`Bir hata oluşursa güncelleştirmeleri geri ala.

- `dbSeeChanges`Başka bir kullanıcı düzenlediğiniz verileri değiştiriyorsa çalışma zamanı hatası oluşturun.

> [!NOTE]
> Her `dbInconsistent` ikisi `dbConsistent` de ve dahil veya hiçbiri dahil değilse, sonuç varsayılandır. Bu sabitlerin açıklaması için DAO Help'deki "Yürütme Yöntemi" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

`Execute`yalnızca sonuç döndürmeyan eylem sorguları veya SQL geçiş sorguları için çalışır. Kayıtları döndüren belirli sorgular için çalışmaz.

Eylem sorguları hakkında bir tanım ve bilgi için DAO Yardımı'ndaki "Eylem Sorgusu" ve "Yürütme Yöntemi" konularına bakın.

> [!TIP]
> Sözdizimi olarak doğru bir SQL deyimi `Execute` ve uygun izinler göz önüne alındığında, tek bir satır değiştirilmese veya silinemese bile üye işlev başarısız olmaz. Bu nedenle, `dbFailOnError` bir güncelleştirmeyi `Execute` çalıştırmak veya sorguyu silmek için üye işlevini kullanırken her zaman seçeneği kullanın. Bu seçenek, MFC'nin [CDaoException](../../mfc/reference/cdaoexception-class.md) türünden bir özel durum almasına ve etkilenen kayıtlardan herhangi biri kilitlenirse ve güncelleştirilemiyorsa veya silinemiyorsa tüm başarılı değişiklikleri geri döndürmesine neden olur. Kaç kaydın etkilendiğini `GetRecordsAffected` görmek için her zaman arayabilirsiniz.

En son `Execute` çağrıdan etkilenen kayıt sayısını belirlemek için veritabanı nesnesinin [GetRecordsAffected](#getrecordsaffected) üye işlevini arayın. Örneğin, `GetRecordsAffected` bir eylem sorgusu yürütürürken silinen, güncelleştirilen veya eklenen kayıt sayısıyla ilgili bilgileri döndürür. Döndürülen sayım, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

`Execute`kayıt kümesi döndürmez. Kayıtları `Execute` seçen bir sorguda kullanmak, MFC'nin `CDaoException`bir özel durum almasına neden olur. (Benzer bir `ExecuteSQL` üye işlev `CDatabase::ExecuteSQL`yoktur.)

## <a name="cdaodatabasegetconnect"></a><a name="getconnect"></a>CDaoDatabase::GetConnect

Nesneyi ODBC veya ISAM veritabanına bağlamak için kullanılan bağlantı dizesini `CDaoDatabase` almak için bu üye işlevi arayın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ODBC veri kaynağında [Open](#open) başarıyla çağrıldıysa bağlantı dizesi; aksi takdirde, boş bir dize. Bir Microsoft Jet için (. MDB) veritabanında, [yürütme](#execute) üyesi işlevi ile kullanılan `dbSQLPassThrough` veya bir kayıt kümesinin açılmasında kullanılan seçenekle kullanıma ayarladığınız sürece dize her zaman boştur.

### <a name="remarks"></a>Açıklamalar

Dize, açık bir veritabanının veya geçiş sorgusunda kullanılan bir veritabanının kaynağı hakkında bilgi sağlar. Bağlantı dizesi, bir veritabanı türü belirtici ve sıfır veya daha fazla parametre yarım iki nokta ile ayrılmış oluşur.

> [!NOTE]
> ODBC üzerinden bir veri kaynağına bağlanmak için MFC DAO sınıflarını kullanmak, ekli bir tablo üzerinden bağlanmaktan daha az verimlidir.

> [!NOTE]
> Bağlantı dizesi, gerektiğinde ODBC'ye ve bazı ISAM sürücülerine ek bilgi aktarmak için kullanılır. Bu için kullanılmaz. MDB veritabanları. Microsoft Jet veritabanı taban tabloları için, bağlantı dizesi, yukarıda İade Değeri altında açıklandığı gibi bir SQL geçiş sorgusu için kullandığınız durumlar dışında boş bir dizedir ("") olur.

Bağlantı dizesinin nasıl oluşturulduğuna ilişkin bir açıklama için [Açık](#open) üye işlevine bakın. `Open` Bağlantı dizesi çağrıda ayarlandıktan sonra, veritabanının türünü, yolunu, kullanıcı kimliğini, Parolayı veya ODBC veri kaynağını belirlemek için ayarı denetlemek için daha sonra kullanabilirsiniz.

## <a name="cdaodatabasegetname"></a><a name="getname"></a>CDaoDatabase::GetName

Varolan bir veritabanı dosyasının adı veya kayıtlı bir ODBC veri kaynağının adı olan şu anda açık olan veritabanının adını almak için bu üye işlevini arayın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa veritabanının tam yol ve dosya adı; aksi takdirde, boş bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

Ağınız tek düzen adlandırma kuralını (UNC) destekliyorsa, bir\\\\\\ağ yolu\\da\\belirtebilirsiniz—örneğin, " \MYSERVER \MYSHARE \MYDIR\\\MYDB. MDB". (Çift backslashes dize literals\\gereklidir çünkü " " C++ kaçış karakteridir.)

Örneğin, bu adı bir başlıkta görüntülemek isteyebilirsiniz. Ad alınırken bir hata oluşursa, MFC [CDaoException](../../mfc/reference/cdaoexception-class.md)türünden bir özel durum oluşturur.

> [!NOTE]
> Dış veritabanlarına erişildiğinde daha iyi performans için, bir Microsoft Jet veritabanına (. MDB) yerine doğrudan veri kaynağına bağlanma.

Veritabanı türü, yolun işaret ettiği dosya veya dizin tarafından aşağıdaki gibi gösterilir:

|Pathname işaret ...|Veritabanı türü|
|--------------------------|-------------------|
|. MDB dosyası|Microsoft Jet veritabanı (Microsoft Access)|
|' yi içeren dizin. DBF dosya(lar)|dBASE veritabanı|
|' yi içeren dizin. XLS dosyası|Microsoft Excel veritabanı|
|' yi içeren dizin. PDX dosya(lar)|Paradoks veritabanı|
|Uygun biçimlendirilmiş metin veritabanı dosyalarını içeren dizin|Metin biçimi veritabanı|

SQL Server ve Oracle gibi ODBC veritabanları için veritabanının bağlantı dizesi, ODBC tarafından kayıtlı bir veri kaynağı adını (DSN) tanımlar.

## <a name="cdaodatabasegetquerydefcount"></a><a name="getquerydefcount"></a>CDaoDatabase::GetQueryDefCount

Veritabanının QueryDefs koleksiyonunda tanımlanan sorgu sayısını almak için bu üye işlevini arayın.

```
short GetQueryDefCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanında tanımlanan sorgu sayısı.

### <a name="remarks"></a>Açıklamalar

`GetQueryDefCount`QueryDefs koleksiyonundaki tüm querydefs üzerinden döngü gerekiyorsa yararlıdır. Koleksiyondaki belirli bir sorgu hakkında bilgi edinmek için [GetQueryDefInfo'ya](#getquerydefinfo)bakın.

## <a name="cdaodatabasegetquerydefinfo"></a><a name="getquerydefinfo"></a>CDaoDatabase::GetQueryDefInfo

Veritabanında tanımlanan bir sorgu hakkında çeşitli bilgiler elde etmek için bu üye işlevini arayın.

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

*Nındex*<br/>
Dizin tarafından arama için veritabanının QueryDefs koleksiyonunda önceden tanımlanmış sorgu dizini.

*querydefinfo*<br/>
İstenen bilgileri döndüren bir [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Kayıt kümesi hakkında hangi bilgilerin alınarak alınamasını belirten seçenekler. Kullanılabilir seçenekler, işlevin kayıt kümesi hakkında dönmesine neden olan larla birlikte burada listelenir:

- AFX_DAO_PRIMARY_INFO (Varsayılan) Adı, Türü

- AFX_DAO_SECONDARY_INFO Birincil bilgi artı: Oluşturulan Tarih, Son Güncelleştirme Tarihi, Kayıtları Döndürür, Güncel

- AFX_DAO_ALL_INFO Birincil ve ikincil bilgi artı: SQL, Connect, ODBCTimeout

*Lpszname*<br/>
Ada göre arama için veritabanında tanımlanan bir sorgunun adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

İşlevin iki sürümü sağlanır, böylece veritabanının QueryDefs koleksiyonunda dizin veya sorgunun adıyla bir sorgu seçebilirsiniz.

*Querydefinfo*döndürülen bilgilerin açıklaması için [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir bilgi düzeyi talep ederseniz, önceden de bilgi düzeyi alırsınız.

## <a name="cdaodatabasegetquerytimeout"></a><a name="getquerytimeout"></a>CDaoDatabase::GetQueryTimeout

Bağlı veritabanında sonraki işlemler zaman dolmadan önce izin vermek için geçerli saniye sayısını almak için bu üye işlevi arayın.

```
short GetQueryTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Saniye cinsinden zaman aşım değerini içeren kısa bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Ağ erişim sorunları, aşırı sorgu işlem süresi ve benzeri nedenler nedeniyle bir işlem zaman alabilir. Ayar etkin ken, bu `CDaoDatabase` nesne ile ilişkili herhangi bir kayıt kümesinde tüm açık, yeni ekleme, güncelleştirme ve silme işlemlerini etkiler. [SetQueryTimeout'u](#setquerytimeout)arayarak geçerli zaman ayarı değiştirebilirsiniz. Açıldıktan sonra bir kayıt kümesinin sorgu zaman anına değerini değiştirmek, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki [Taşı](../../mfc/reference/cdaorecordset-class.md#move) işlemleri yeni değeri kullanmaz. Veritabanı altyapısı başharfe atıldığında varsayılan değer başlangıçta ayarlanır.

Sorgu zaman zamanları için varsayılan değer Windows kayıt defterinden alınır. Kayıt defteri ayarı yoksa, varsayılan değer 60 saniyedir. Tüm veritabanları sorgu zaman anına değer ayarlama yeteneğini desteklemez. 0 sorgu zaman ödeme değeri ayarlarsanız, zaman ası oluşmaz; ve veritabanı ile iletişim yanıt durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir. Arama başarısız olursa, MFC [cdaoException](../../mfc/reference/cdaoexception-class.md)türübir özel durum atar.

İlgili bilgiler için DAO Yardım'daki "QueryTimeout Özelliği" konusuna bakın.

## <a name="cdaodatabasegetrecordsaffected"></a><a name="getrecordsaffected"></a>CDaoDatabase::GetRecordsAffected

[Yürüt](#execute) üye işlevinin en son çağrısından etkilenen kayıt sayısını belirlemek için bu üye işlevi arayın.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Dönüş Değeri

Etkilenen kayıt sayısını içeren uzun bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer, `Execute`'' ile çalıştırılan bir eylem sorgusu tarafından silinen, güncelleştirilen veya eklenen kayıt sayısını içerir. Döndürülen sayım, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

İlgili bilgiler için DAO Yardım'daki "RecordsAffected Property" konusuna bakın.

## <a name="cdaodatabasegetrelationcount"></a><a name="getrelationcount"></a>CDaoDatabase::GetRelationCount

Veritabanındaki tablolar arasında tanımlanan ilişki sayısını elde etmek için bu üye işlevi arayın.

```
short GetRelationCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanındaki tablolar arasında tanımlanan ilişki sayısı.

### <a name="remarks"></a>Açıklamalar

`GetRelationCount`veritabanının İlişkiler koleksiyonundaki tüm tanımlanmış ilişkileri döngüye almanız gerekiyorsa yararlıdır. Koleksiyondaki belirli bir ilişki hakkında bilgi edinmek için [GetRelationInfo'ya](#getrelationinfo)bakın.

İlişki kavramını göstermek için, bir-çok ilişkisi olabilecek bir Tedarikçiler tablosu ve Ürünler tablosunu düşünün. Bu ilişkide, bir tedarikçi birden fazla ürün tedarik edebilir. Diğer ilişkiler bire bir ve çok-çok.

## <a name="cdaodatabasegetrelationinfo"></a><a name="getrelationinfo"></a>CDaoDatabase::GetRelationInfo

Veritabanının İlişkiler koleksiyonunda belirtilen bir ilişki hakkında bilgi almak için bu üye işlevini arayın.

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

*Nındex*<br/>
Veritabanının İlişkiler koleksiyonundaki ilişki nesnesinin dizin, dizin tarafından arama için dizin.

*relinfo*<br/>
İstenen bilgileri döndüren bir [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Almak la ilişkisi hakkında hangi bilgileri belirten seçenekler. Kullanılabilir seçenekler, işlevin ilişki hakkında dönmesine neden olan larla birlikte burada listelenmiştir:

- AFX_DAO_PRIMARY_INFO (Varsayılan) Adı, Tablosu, Yabancı Tablo

- AFX_DAO_SECONDARY_INFO Özellikleri, Alan Bilgileri

Alan Bilgileri, ilişkide yer alan birincil tablodaki alanları içeren bir [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) nesnesidir.

*Lpszname*<br/>
Ada göre arama için ilişki nesnesinin adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Bu işlevin iki sürümü, dizin veya ada göre erişim sağlar. *Relinfo'da*döndürülen bilgilerin açıklaması için [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir düzeyde bilgi talep ederseniz, önceki düzeylerde de bilgi alırsınız.

> [!NOTE]
> İlişki nesnesinin özniteliklerini basamaklı işlemleri etkinleştirmek `dbRelationDeleteCascades`için ayarlarsanız (veya),`dbRelationUpdateCascades` Microsoft Jet veritabanı altyapısı, ilgili birincil anahtar tablolarında değişiklik yapıldığında bir veya daha fazla diğer tablodaki kayıtları otomatik olarak güncelleştirir veya siler. Örneğin, Müşteriler tablosu ile Siparişler tablosu arasında basamaklı silme ilişkisi oluşturduğunuzu varsayalım. Müşteriler tablosundaki kayıtları sildiğinizde, bu müşteriyle ilgili Siparişler tablosundaki kayıtlar da silinir. Ayrıca, Siparişler tablosu ile diğer tablolar arasında basamaklı silme ilişkileri kurarsanız, Müşteriler tablosundaki kayıtları sildiğinizde bu tablolardaki kayıtlar otomatik olarak silinir.

## <a name="cdaodatabasegettabledefcount"></a><a name="gettabledefcount"></a>CDaoDatabase::GetTableDefCount

Veritabanında tanımlanan tablo sayısını almak için bu üye işlevi arayın.

```
short GetTableDefCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanında tanımlanan tablo sayısı.

### <a name="remarks"></a>Açıklamalar

`GetTableDefCount`veritabanının TableDefs koleksiyonundaki tüm tabledefs üzerinden döngü gerekiyorsa yararlıdır. Koleksiyondaki belirli bir tablo hakkında bilgi edinmek için [GetTableDefInfo'ya](#gettabledefinfo)bakın.

## <a name="cdaodatabasegettabledefinfo"></a><a name="gettabledefinfo"></a>CDaoDatabase::GetTableDefInfo

Veritabanında tanımlanan bir tablo hakkında çeşitli bilgiler elde etmek için bu üye işlevi arayın.

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

*Nındex*<br/>
Dizin tarafından arama için veritabanının TableDefs koleksiyonundaki tabledef nesnesinin dizin.

*tabledefinfo*<br/>
İstenen bilgileri döndüren [bir CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Tablo hakkında hangi bilgilerin alınaaçık olduğunu belirten seçenekler. Kullanılabilir seçenekler, işlevin ilişki hakkında dönmesine neden olan larla birlikte burada listelenmiştir:

- AFX_DAO_PRIMARY_INFO (Varsayılan) Adı, Güncel, Öznitelik

- AFX_DAO_SECONDARY_INFO Birincil bilgi artı: Oluşturulan Tarih, Son Güncellenme Tarihi, Kaynak Tablo Adı, Bağlan

- AFX_DAO_ALL_INFO Temel ve ikincil bilgi artı: Doğrulama Kuralı, Doğrulama Metni, Kayıt Sayısı

*Lpszname*<br/>
Tablodef nesnesinin adı, ada göre arama için.

### <a name="remarks"></a>Açıklamalar

İşlevin iki sürümü sağlanır, böylece veritabanının TableDefs koleksiyonunda dizin veya tablonun adına bir tablo seçebilirsiniz.

*Tabledefinfo*döndürülen bilgilerin açıklaması için [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir düzeyde bilgi talep ederseniz, önceki düzeyler için de bilgi alırsınız.

> [!NOTE]
> AFX_DAO_ALL_INFO seçeneği, elde edilmesi yavaş olabilecek bilgiler sağlar. Bu durumda, tablodaki kayıtları saymak çok zaman alabilir, çok sayıda kayıt varsa.

## <a name="cdaodatabasegetversion"></a><a name="getversion"></a>CDaoDatabase::GetVersion

Microsoft Jet veritabanı dosyasının sürümünü belirlemek için bu üye işlevini arayın.

```
CString GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyle ilişkili veritabanı dosyasının sürümünü gösteren bir [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Açıklamalar

Döndürülen değer"major.minor" şeklindeki sürüm numarasını temsil eder; örneğin, "3.0". Ürün sürüm numarası (örneğin, 3.0) sürüm numarası (3), bir dönem ve sürüm numarasından (0) oluşur. Bugüne kadarki sürümler 1.0, 1.1, 2.0 ve 3.0'dır.

İlgili bilgiler için DAO Yardım'daki "Sürüm Özelliği" konusuna bakın.

## <a name="cdaodatabaseisopen"></a><a name="isopen"></a>CDaoDatabase::Açık

Nesnenin `CDaoDatabase` veritabanında şu anda açık olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne şu `CDaoDatabase` anda açıksa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaodatabasem_pdaodatabase"></a><a name="m_pdaodatabase"></a>CDaoVeritabanı::m_pDAODatabase

Nesnenin altında yatan DAO veritabanı nesnesi `CDaoDatabase` için OLE arabirimine bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

DAO arabirimine doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.

DOĞRUDAN DAO'u arama hakkında bilgi için [Teknik Not 54'e](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)bakın.

## <a name="cdaodatabasem_pworkspace"></a><a name="m_pworkspace"></a>CDaoVeritabanı::m_pWorkspace

Veritabanı nesnesini içeren [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Çalışma alanına doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın ( örneğin, çalışma alanının Veritabanları koleksiyonundaki diğer veritabanı nesnelerine işaretçiler edinin.

## <a name="cdaodatabaseopen"></a><a name="open"></a>CDaoDatabase::Aç

Varolan bir veritabanını temsil eden `CDaoDatabase` yeni oluşturulmuş bir nesneyi başlatmak için bu üye işlevi aramalısınız.

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Varolan bir Microsoft Jet'in adı olan dize ifadesi (. MDB) veritabanı dosyası. Dosya adının bir uzantısı varsa, bu gereklidir. Ağınız tek düzen adlandırma kuralını (UNC) destekliyorsa, "\\\\\\\MYSERVER \MYSHARE\\\\\\\MYDIR \MYDB gibi bir ağ yolu da belirtebilirsiniz. MDB". (Çift backslashes dize literals\\gereklidir çünkü " " C++ kaçış karakteridir.)

*LpszName*kullanırken bazı hususlar geçerlidir. Eğer:

- Başka bir kullanıcı tarafından özel erişim için zaten açık olan bir veritabanıanlamına gelir, MFC türü [CDaoException](../../mfc/reference/cdaoexception-class.md)bir özel durum atar. Kullanıcınıza veritabanının kullanılolmadığını bildirmek için bu özel durumu bindirme.

- Boş bir dize ("") ve *lpszConnect* "ODBC;", kullanıcı bir veritabanı seçebilirsiniz, böylece tüm kayıtlı ODBC veri kaynağı adları listeleyen bir iletişim kutusu. ODBC veri kaynaklarına doğrudan bağlantıyapmaktan kaçınmalısınız; bunun yerine ekli bir tablo kullanın.

- Aksi takdirde varolan bir veritabanı veya geçerli ODBC veri kaynağı adı `CDaoException`anlamına gelmez, MFC türübir özel durum atar.

> [!NOTE]
> DAO hata kodları hakkında ayrıntılı bilgi için DAOERR'a bakın. H dosyası. İlgili bilgiler için DAO Yardım'daki "Trappable Data Access Errors" konusuna bakın.

*bExclusive*<br/>
Veritabanı özel (paylaşılmayan) erişim için açılacaksa DOĞRU olan Boolean değeri ve veritabanı paylaşılan erişim için açılacaksa FALSE değeri. Bu bağımsız değişkeni atlarsanız, veritabanı paylaşılan erişim için açılır.

*bReadOnly*<br/>
Veritabanı salt okunur erişim için açılacaksa DOĞRU olan Boolean değeri ve veritabanı okuma/yazma erişimi için açılacaksa FALSE değeri. Bu bağımsız değişkeni atlarsanız, veritabanı okuma/yazma erişimi için açılır. Tüm bağımlı kayıt kümeleri bu özniteliği devralır.

*lpszConnect*<br/>
Veritabanını açmak için kullanılan bir dize ifadesi. Bu dize, ODBC bağlantı bağımsız değişkenlerini oluşturur. Kaynak dizesini sağlamak için özel ve salt okunur bağımsız değişkenleri sağlamanız gerekir. Veritabanı bir Microsoft Jet veritabanıise (. MDB), bu dize boş (""). Varsayılan değeriçin sözdizimi **-_T**("") - Unicode için taşınabilirliğin yanı sıra uygulamanızın ANSI yapılarını da sağlar.

### <a name="remarks"></a>Açıklamalar

`Open`veritabanını altta yatan DAO nesnesiyle ilişkilendirer. Baş harfe gelene kadar recordset, tabledef veya querydef nesnelerini oluşturmak için veritabanı nesnesini kullanamazsınız. `Open`veritabanı nesnesini ilişkili çalışma alanının Veritabanları koleksiyonuna ekler.

Parametreleri aşağıdaki gibi kullanın:

- Bir Microsoft Jet açıyorsanız (. MDB) veritabanı, *lpszName* parametresini kullanın ve *lpszConnect* parametresi için boş bir dize geçirin veya formun bir şifre dizesini geçirin "; PWD=password" veritabanı parola korumalı ise (. Yalnızca MDB veritabanları).

- Bir ODBC veri kaynağı açıyorsanız, *lpszConnect'te* geçerli bir ODBC bağlantı dizesi ve *lpszName'de*boş bir dize geçirin.

İlgili bilgiler için DAO Yardım'daki "OpenDatabase Method" konusuna bakın.

> [!NOTE]
> ISAM veritabanları ve ODBC veri kaynakları da dahil olmak üzere harici veritabanlarına erişirken daha iyi performans için, bir Microsoft Jet altyapısı veritabanına harici veritabanı tabloları eklemeniz önerilir (. MDB) yerine doğrudan veri kaynağına bağlanma.

Örneğin, DBMS ana bilgisayarı kullanılamıyorsa, bir bağlantı denemesinin zaman dışarı çıkması mümkündür. Bağlantı girişimi başarısız `Open` olursa, [cdaoException](../../mfc/reference/cdaoexception-class.md)türü bir özel durum atar.

Geri kalan açıklamalar yalnızca ODBC veritabanları için geçerlidir:

Veritabanı bir ODBC veritabanıysa ve aramanızdaki `Open` parametreler bağlantıyı oluşturmak için yeterli bilgi içermiyorsa, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açar. Bağlantı dizeniz `Open` *lpszConnect'i*aradığınızda özel olarak saklanır ve [GetConnect](#getconnect) üye işlevini arayarak kullanılabilir.

İsterseniz, parola gibi kullanıcıdan bilgi almak `Open` için aramadan önce kendi iletişim kutunuzu açabilir, ardından bu bilgileri `Open`geçtiğiniz bağlantı dizesine ekleyebilirsiniz. Veya geçtiğiniz bağlantı dizesini (belki de Windows kayıt defterinde) kaydetmek isteyebilirsiniz, böylece `Open` uygulamanız bir `CDaoDatabase` nesneyi bir sonraki aramada yeniden kullanabilirsiniz.

Bağlantı dizesini birden çok oturum açma yetkilendirme düzeyi (her biri farklı `CDaoDatabase` bir nesne için) veya veritabanına özgü diğer bilgileri iletmek için de kullanabilirsiniz.

## <a name="cdaodatabasesetquerytimeout"></a><a name="setquerytimeout"></a>CDaoDatabase::SetQueryTimeout

Bağlı veritabanı zaman önce sonraki işlemlere izin vermek için varsayılan saniye sayısını geçersiz kılmak için bu üye işlevi arayın.

```
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>Parametreler

*nSeconds*<br/>
Sorgu denemesi nden önce izin verilebilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Ağ erişim sorunları, aşırı sorgu işlem süresi ve benzeri nedenlerden dolayı bir işlem zaman alabilir. Kayıt `SetQueryTimeout` setinizi açmadan önce veya sorgu zaman önceliğini değiştirmek istiyorsanız kayıt setinin [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [Update](../../mfc/reference/cdaorecordset-class.md#update)veya [Delete](../../mfc/reference/cdaorecordset-class.md#delete) üye işlevlerini aramadan önce arayın. Ayar sonraki tüm [Open](../../mfc/reference/cdaorecordset-class.md#open)Açık `AddNew` `Update`etkiler `Delete` , , ve bu `CDaoDatabase` nesne ile ilişkili herhangi bir kayıt kümeleri çağırır. Açıldıktan sonra bir kayıt kümesinin sorgu zaman anına değerini değiştirmek, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki [Taşı](../../mfc/reference/cdaorecordset-class.md#move) işlemleri yeni değeri kullanmaz.

Sorgu zaman ları için varsayılan değer 60 saniyedir. Tüm veritabanları sorgu zaman anına değer ayarlama yeteneğini desteklemez. 0 sorgu zaman ödeme değeri ayarlarsanız, zaman ası oluşmaz; veritabanı ile iletişim yanıt durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir.

İlgili bilgiler için DAO Yardım'daki "QueryTimeout Özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoWorkspace Sınıf](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
