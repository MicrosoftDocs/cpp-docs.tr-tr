---
title: CDaoDatabase sınıfı
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
ms.openlocfilehash: 4c594b1ddfc1464417506557bb8743c4979be677
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304289"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase sınıfı

Veri erişim nesneleri (DAO) kullanarak bir Access veritabanı bağlantısını temsil eder. DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CDaoDatabase:: CDaoDatabase](#cdaodatabase)|`CDaoDatabase` nesnesi oluşturur. Nesneyi bir veritabanına bağlamak için `Open` çağırın.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CDaoDatabase:: CanTransact](#cantransact)|Veritabanı işlemleri destekliyorsa sıfır dışında bir değer döndürür.|
|[CDaoDatabase:: CanUpdate](#canupdate)|`CDaoDatabase` nesnesi güncelleştirilebilir ise (salt okunurdur) sıfır olmayan bir değer döndürür.|
|[CDaoDatabase:: Close](#close)|Veritabanı bağlantısını kapatır.|
|[CDaoDatabase:: Create](#create)|Temel alınan DAO veritabanı nesnesini oluşturur ve `CDaoDatabase` nesnesini başlatır.|
|[CDaoDatabase:: CreateRelation](#createrelation)|Veritabanındaki tablolar arasında yeni bir ilişki tanımlar.|
|[CDaoDatabase::D eleteQueryDef](#deletequerydef)|Veritabanının QueryDefs koleksiyonunda kaydedilen bir QueryDef nesnesini siler.|
|[CDaoDatabase::D eleteRelation](#deleterelation)|Veritabanındaki tablolar arasında varolan bir ilişkiyi siler.|
|[CDaoDatabase::D eleteTableDef](#deletetabledef)|Veritabanındaki bir tablonun tanımını siler. Bu, gerçek tabloyu ve tüm verilerini siler.|
|[CDaoDatabase:: Execute](#execute)|Bir eylem sorgusu yürütür. Sonuçlar döndüren bir sorgu için `Execute` çağırmak özel durum oluşturur.|
|[CDaoDatabase:: GetConnect](#getconnect)|`CDaoDatabase` nesnesini bir veritabanına bağlamak için kullanılan bağlantı dizesini döndürür. ODBC için kullanılır.|
|[CDaoDatabase:: GetName](#getname)|Kullanılmakta olan veritabanının adını döndürür.|
|[CDaoDatabase:: GetQueryDefCount](#getquerydefcount)|Veritabanı için tanımlanan sorguların sayısını döndürür.|
|[CDaoDatabase:: Getquerydefinınfo](#getquerydefinfo)|Veritabanında tanımlanan belirli bir sorgu hakkında bilgi döndürür.|
|[CDaoDatabase:: GetQueryTimeout](#getquerytimeout)|Veritabanı sorgusu işlemlerinin zaman aşımına geçmesi için geçmesi gereken saniye sayısını döndürür. Tüm sonraki açık, yeni, güncelleştirme ve düzenleme işlemlerini ve ODBC veri kaynaklarına (yalnızca `Execute` çağrıları gibi diğer işlemleri) etkiler.|
|[CDaoDatabase:: Getrecordsabetkilenen](#getrecordsaffected)|Son güncelleştirme, düzenleme veya ekleme işleminden etkilenen kayıt sayısını veya `Execute`çağrısı ile döndürür.|
|[CDaoDatabase:: GetRelationCount](#getrelationcount)|Veritabanındaki tablolar arasında tanımlanan ilişki sayısını döndürür.|
|[CDaoDatabase:: GetRelationInfo](#getrelationinfo)|Veritabanındaki tablolar arasında tanımlanan belirli bir ilişki hakkındaki bilgileri döndürür.|
|[CDaoDatabase:: GetTableDefCount](#gettabledefcount)|Veritabanında tanımlanan tablo sayısını döndürür.|
|[CDaoDatabase:: Gettabledefinınfo](#gettabledefinfo)|Veritabanında belirtilen tablo hakkındaki bilgileri döndürür.|
|[CDaoDatabase:: GetVersion](#getversion)|Veritabanıyla ilişkili veritabanı altyapısının sürümünü döndürür.|
|[CDaoDatabase:: IsOpen](#isopen)|`CDaoDatabase` nesnesi şu anda bir veritabanına bağlıysa sıfır olmayan bir değer döndürür.|
|[CDaoDatabase:: Open](#open)|Bir veritabanına bağlantı kurar.|
|[CDaoDatabase:: SetQueryTimeout](#setquerytimeout)|Veritabanı sorgusu işlemlerinin (yalnızca ODBC veri kaynaklarında) zaman aşımına uğrar olan saniye sayısını ayarlar. Sonraki açık, yeni, güncelleştirme ve silme işlemlerini etkiler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Name|Açıklama|
|----------|-----------------|
|[CDaoDatabase:: m_pDAODatabase](#m_pdaodatabase)|Temel alınan DAO veritabanı nesnesine yönelik bir işaretçi.|
|[CDaoDatabase:: m_pWorkspace](#m_pworkspace)|Veritabanını içeren ve işlem alanını tanımlayan [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine yönelik bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Desteklenen veritabanı biçimleri hakkında daha fazla bilgi için bkz. [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) üye işlevi. Bir bir veya daha fazla `CDaoDatabase` nesnesini, belirli bir "çalışma alanında" bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesi tarafından temsil edilen bir anda etkin durumda olabilir. Çalışma alanı, veritabanları koleksiyonu olarak adlandırılan açık veritabanı nesnelerinin bir koleksiyonunu tutar.

## <a name="usage"></a>Kullanım

Kayıt kümesi nesneleri oluştururken örtük olarak veritabanı nesneleri oluşturabilirsiniz. Ancak, açıkça veritabanı nesneleri de oluşturabilirsiniz. Mevcut bir veritabanını `CDaoDatabase`açık olarak kullanmak için aşağıdakilerden birini yapın:

- Açık bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine bir işaretçi geçirerek bir `CDaoDatabase` nesnesi oluşturun.

- Ya da çalışma alanını belirtmeden bir `CDaoDatabase` nesnesi oluşturun (MFC geçici bir çalışma alanı nesnesi oluşturur).

Yeni bir Microsoft Jet (. MDB) veritabanı, bir `CDaoDatabase` nesnesi oluşturun ve üye [Oluştur](#create) işlevini çağırın. `Create`sonra *`Open` çağırmayın* .

Var olan bir veritabanını açmak için bir `CDaoDatabase` nesnesi oluşturun ve [Açık](#open) üye işlevini çağırın.

Bu tekniklerin herhangi biri, DAO veritabanı nesnesini çalışma alanının veritabanları koleksiyonuna ekler ve verilere bir bağlantı açar. Daha sonra, bağlantılı veritabanında çalıştırmak üzere [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)veya [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesneleri oluşturduğunuzda, bu nesnelere yönelik oluşturucuları, `CDaoDatabase` nesneniz için bir işaretçi olarak geçirin. Bağlantıyı kullanmayı bitirdiğinizde, [Close](#close) üye işlevini çağırın ve `CDaoDatabase` nesnesini yok edin. `Close`, daha önce kapatılmayan tüm kayıt kümelerini kapatır.

## <a name="transactions"></a>İşlemler

Veritabanı işlem işleme çalışma alanı düzeyinde sağlanır — `CDaoWorkspace`sınıfının [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans)ve [Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) üye işlevlerine bakın.

## <a name="odbc-connections"></a>ODBC Bağlantıları

ODBC veri kaynakları ile çalışmanın önerilen yolu, dış tabloları bir Microsoft Jet 'e eklemektir (. MDB) veritabanı.

## <a name="collections"></a>Koleksiyonlar

Her veritabanı kendi TableDef, QueryDef, Recordset ve Relation nesneleri koleksiyonlarını korur. Sınıf `CDaoDatabase`, bu nesneleri işlemek için üye işlevleri sağlar.

> [!NOTE]
>  Nesneler, MFC veritabanı nesnesinde değil, DAO 'da depolanır. MFC, TableDef, QueryDef ve Recordset nesneleri için sınıflar sağlar ancak ilişki nesneleri için kullanmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

##  <a name="cantransact"></a>CDaoDatabase:: CanTransact

Veritabanının işlemlere izin verip içermediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanı işlemleri destekliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlemler, veritabanının çalışma alanında yönetilir.

##  <a name="canupdate"></a>CDaoDatabase:: CanUpdate

`CDaoDatabase` nesnesinin güncelleştirmelere izin verip içermediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoDatabase` nesnesi güncelleştirmelere izin veriyorsa sıfır dışında; Aksi takdirde 0, `CDaoDatabase` nesnesini açtığınızda *bReadOnly* içinde doğru geçtiğini veya veritabanının kendisinin salt okunur olduğunu belirtir. [Açık](#open) üye işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veritabanı güncellenebilirliği hakkında daha fazla bilgi için, DAO yardımı 'nda "güncelleştirilebilir özellik" konusuna bakın.

##  <a name="cdaodatabase"></a>CDaoDatabase:: CDaoDatabase

`CDaoDatabase` nesnesi oluşturur.

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>Parametreler

*pWorkspace*<br/>
Yeni veritabanı nesnesini içerecek `CDaoWorkspace` nesnesine yönelik bir işaretçi. NULL varsayılan değerini kabul ediyorsanız, Oluşturucu varsayılan DAO çalışma alanını kullanan geçici bir `CDaoWorkspace` nesnesi oluşturur. [M_pWorkspace](#m_pworkspace) veri üyesi aracılığıyla çalışma alanı nesnesine bir işaretçi alabilirsiniz.

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, yeni bir Microsoft Jet (. MDB) veritabanı, nesnenin üye [Oluştur](#create) işlevini çağırın. Bunun yerine, var olan bir veritabanını açarak nesnenin [Açık](#open) üye işlevini çağırın.

Nesnesiyle bitirdiğinizde, [Close](#close) üye işlevini çağırmanız ve sonra `CDaoDatabase` nesnesini yok etmeniz gerekir.

`CDaoDatabase` nesnesini belge sınıfınıza katıştırmayı kullanışlı bulabilirsiniz.

> [!NOTE]
>  Bir `CDaoDatabase` nesnesi, var olan bir `CDaoDatabase` nesnesine işaretçi geçirmeden bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi açarsanız örtülü olarak da oluşturulur. Bu veritabanı nesnesi, kayıt kümesi nesnesini kapattığınızda kapatılır.

##  <a name="close"></a>CDaoDatabase:: Close

Bir veritabanının bağlantısını kesmek ve veritabanıyla ilişkili açık kayıt kümelerini, TableDefs ve QueryDefs 'leri kapatmak için bu üye işlevi çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırabilmeniz için bu nesneleri kendiniz kapatmak iyi bir uygulamadır. Bir `CDaoDatabase` nesnenin kapatılması, ilişkili [çalışma alanındaki](../../mfc/reference/cdaoworkspace-class.md)veritabanları koleksiyonundan kaldırılır. `Close` `CDaoDatabase` nesnesini yok etmez, aynı veritabanını veya farklı bir veritabanını açarak nesneyi yeniden kullanabilirsiniz.

> [!CAUTION]
>  Bir veritabanını kapatmadan önce tüm açık kayıt kümesi nesnelerinde [`Close` üye işlevini](../../mfc/reference/cdaorecordset-class.md#update) (bekleyen düzenlemeler varsa) ve üye işlevini çağırın. Yığın üzerinde [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) veya `CDaoDatabase` nesneleri bildiren bir işlevden çıkarsanız, veritabanı kapatılır, kaydedilmeyen tüm değişiklikler kaybolur, bekleyen tüm işlemler geri alınır ve verilerinizde bekleyen tüm düzenlemeler kaybedilir.

> [!CAUTION]
>  Herhangi bir kayıt kümesi nesnesi açıkken bir veritabanı nesnesini kapatmaya çalışırsanız veya ilgili çalışma alanına ait herhangi bir veritabanı nesnesi açıkken bir çalışma alanı nesnesini kapatmaya çalışırsanız, bu kayıt kümesi nesneleri kapatılır ve bekleyen güncelleştirmeler veya düzenlemeler olur geri alındı. Bir çalışma alanı nesnesini, kendisine ait herhangi bir veritabanı nesnesi açık durumdayken kapatmaya çalışırsanız, işlem söz konusu çalışma alanı nesnesine ait tüm veritabanı nesnelerini kapatır ve bu, kapatılmamış kayıt kümesi nesnelerinin kapatılmasına neden olabilir. Veritabanı nesneniz kapanmaz, MFC hata ayıklama yapılarında bir onaylama hatası bildiriyor.

Veritabanı nesnesi bir işlevin kapsamı dışında tanımlıysa ve işlevden çıkmadan çıkarsanız, açıkça kapatılana veya tanımlandığı modül kapsam dışına çıkana kadar veritabanı nesnesi açık kalır.

##  <a name="create"></a>CDaoDatabase:: Create

Yeni bir Microsoft Jet (. MDB) veritabanı, bir `CDaoDatabase` nesnesi oluşturduktan sonra bu üye işlevini çağırın.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Oluşturmakta olduğunuz veritabanı dosyasının adı olan bir dize ifadesi. "C:\\\MYDB" gibi tam yol ve dosya adı olabilir. MDB ". Bir ad belirtmeniz gerekir. Bir dosya adı uzantısı belirtmezseniz,. MDB eklenir. Ağınız Tekdüzen adlandırma kuralını (UNC) destekliyorsa, "\\\\\\\SUNUCUM\\\MYSHARE\\\MYDIR\\\MYDB" gibi bir ağ yolu da belirtebilirsiniz. Yalnızca Microsoft Jet (. MDB) veritabanı dosyaları, bu üye işlevi kullanılarak oluşturulabilir. ("\\" C++ kaçış karakteri olduğundan, dize sabit değerlerinde çift ters eğik çizgiler gereklidir.)

*lpszLocale*<br/>
Veritabanı oluşturmak için harmanlama sırasını belirtmek için kullanılan bir dize ifadesi. Varsayılan değer `dbLangGeneral` şeklindedir. Olası değerler şunlardır:

- `dbLangGeneral` Ingilizce, Almanca, Fransızca, Portekizce, Italyanca ve modern Ispanyolca

- `dbLangArabic` Arapça

- `dbLangCyrillic` Rusça

- `dbLangCzech` Çekçe

- `dbLangDutch` Hollanda dili

- `dbLangGreek` Yunanca

- `dbLangHebrew` Ibranice

- `dbLangHungarian` Macarca

- `dbLangIcelandic` Izlanda dili

- `dbLangNordic` Iskandinav dilleri (yalnızca Microsoft Jet veritabanı altyapısı sürüm 1,0)

- `dbLangNorwdan` Norveççe ve Danca

- `dbLangPolish` Lehçe

- `dbLangSpanish` geleneksel Ispanyolca

- `dbLangSwedfin` Isveççe ve Fince

- `dbLangTurkish` Türkçe

*dwOptions*<br/>
Bir veya daha fazla seçeneği belirten tamsayı. Olası değerler şunlardır:

- `dbEncrypt` şifrelenmiş bir veritabanı oluşturun.

- `dbVersion10` Microsoft Jet veritabanı sürüm 1,0 ile veritabanı oluşturma.

- `dbVersion11` Microsoft Jet veritabanı sürüm 1,1 ile veritabanı oluşturma.

- `dbVersion20` Microsoft Jet veritabanı sürüm 2,0 ile veritabanı oluşturma.

- `dbVersion30` Microsoft Jet veritabanı sürüm 3,0 ile veritabanı oluşturma.

Şifreleme sabitini atlarsanız, şifrelenmemiş bir veritabanı oluşturulur. Yalnızca bir sürüm sabiti belirtebilirsiniz. Bir sürüm sabitini atlarsanız, Microsoft Jet veritabanı sürüm 3,0 ' ı kullanan bir veritabanı oluşturulur.

> [!CAUTION]
>  Bir veritabanı şifrelenmemişse, veritabanını oluşturan ikili disk dosyasını doğrudan okumak için Kullanıcı/parola güvenliği uygulasanız bile mümkündür.

### <a name="remarks"></a>Açıklamalar

`Create` veritabanı dosyasını ve temel alınan DAO veritabanı nesnesini oluşturur ve C++ nesneyi başlatır. Nesne, ilişkili çalışma alanının veritabanları koleksiyonuna eklenir. Veritabanı nesnesi açık durumda; `Create`sonra `Open*` çağırmayın.

> [!NOTE]
>  `Create`ile yalnızca Microsoft Jet (. MDB) veritabanları. ISAM veritabanları veya ODBC veritabanları oluşturamazsınız.

##  <a name="createrelation"></a>CDaoDatabase:: CreateRelation

Veritabanındaki birincil tablodaki bir veya daha fazla alan ile yabancı tablodaki bir veya daha fazla alan arasında bir ilişki oluşturmak için bu üye işlevini çağırın (veritabanındaki başka bir tablo).

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
İlişki nesnesinin benzersiz adı. Ad bir harfle başlamalı ve en fazla 40 karakter içerebilir. Sayılar ve alt çizgi karakterlerini içerebilir, ancak noktalama veya boşluk içeremez.

*lpszTable*<br/>
İlişkide birincil tablonun adı. Tablo yoksa, MFC, [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur.

*lpszForeignTable*<br/>
İlişkide yabancı tablonun adı. Tablo yoksa, MFC `CDaoException`türünde bir özel durum oluşturur.

*lAttributes*<br/>
İlişki türü hakkında bilgi içeren uzun bir değer. Bu değeri, diğer şeyler arasında başvurusal bütünlüğü zorlamak için kullanabilirsiniz. Aşağıdaki değerlerden herhangi birini birleştirmek için bit düzeyinde OR **&#124;** işlecini () kullanabilirsiniz (bileşim mantıklı olduğu sürece):

- `dbRelationUnique` Ilişki bire bir.

- `dbRelationDontEnforce` Ilişki zorlanmaz (başvurusal bütünlük yoktur).

- `dbRelationInherited` Ilişki, iki ekli tabloyu içeren geçerli olmayan bir veritabanında bulunuyor.

- `dbRelationUpdateCascade` güncelleştirmeler basamaklandıralınacaktır (daha fazla bilgi için bkz. açıklamalar).

- `dbRelationDeleteCascade` silme Işlemleri basamaklandıracaktır.

*lpszField*<br/>
Birincil tablodaki bir alanın adını içeren, null ile sonlandırılmış bir dize işaretçisi ( *lpszTable*tarafından adlandırılır).

*lpszForeignField*<br/>
Yabancı tablodaki bir alanın adını içeren, null ile sonlandırılmış bir dize işaretçisi ( *lpszForeignTable*tarafından adlandırılır).

*relinfo*<br/>
Oluşturmak istediğiniz ilişki hakkında bilgi içeren bir [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

İlişki, bir sorgu veya bir dış veritabanından ekli tablo içeremez.

İlişki iki tablonun her birinde bir alan içeriyorsa, işlevin ilk sürümünü kullanın. İlişki birden çok alan içeriyorsa ikinci sürümü kullanın. Bir ilişkide en fazla alan sayısı 14 ' dir.

Bu eylem, temeldeki bir DAO ilişki nesnesi oluşturur, ancak MFC 'nin ilişki nesnelerinin kapsüllenmesi `CDaoDatabase`sınıfında bulunduğundan bu bir MFC Uygulama ayrıntısıdır. MFC, ilişkiler için bir sınıf sağlamaz.

Cascade işlemlerini etkinleştirmek için Relation nesnesinin özniteliklerini ayarlarsanız, ilgili birincil anahtar tablolarında değişiklik yapıldığında veritabanı altyapısı bir veya daha fazla tablodaki kayıtları otomatik olarak güncelleştirir veya siler.

Örneğin, bir müşteriler tablosu ve Siparişler tablosu arasında basamaklı bir silme ilişkisi oluşturduğunuzu varsayalım. Müşteriler tablosundan kayıtları sildiğinizde, bu müşteriyle ilgili Siparişler tablosundaki kayıtlar da silinir. Ayrıca, Siparişler tablosu ve diğer tablolar arasında basamaklı silme ilişkileri oluşturursanız, müşteriler tablosundan kayıtları sildiğinizde bu tablolardan kayıtlar otomatik olarak silinir.

İlgili bilgiler için, DAO yardımı 'nda "CreateRelation Yöntemi" konusuna bakın.

##  <a name="deletequerydef"></a>CDaoDatabase::D eleteQueryDef

`CDaoDatabase` nesnenin QueryDefs koleksiyonundan belirtilen QueryDef (kaydedilmiş sorgu) öğesini silmek için bu üye işlevi çağırın.

```
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Silinecek kaydedilen sorgunun adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, bu sorgu artık veritabanında tanımlı değildir.

QueryDef nesneleri oluşturma hakkında daha fazla bilgi için bkz. Class [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Bir QueryDef nesnesi, `CDaoQueryDef` nesnesini oluşturduğunuzda, veritabanı nesnesine bir işaretçi geçirerek belirli bir `CDaoDatabase` nesnesiyle ilişkili hale gelir.

##  <a name="deleterelation"></a>CDaoDatabase::D eleteRelation

Veritabanı nesnesinin Ilişkiler koleksiyonundan varolan bir ilişkiyi silmek için bu üye işlevi çağırın.

```
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Silinecek ilişkinin adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, ilişki artık mevcut değildir.

İlgili bilgiler için, DAO yardımında "Yöntem silme" konusuna bakın.

##  <a name="deletetabledef"></a>CDaoDatabase::D eleteTableDef

Belirtilen tabloyu ve tüm verilerini `CDaoDatabase` nesnenin TableDefs koleksiyonundan silmek için bu üye işlevi çağırın.

```
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Silinecek TableDef 'in adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, bu tablo artık veritabanında tanımlı değildir.

> [!NOTE]
>  Sistem tablolarını silmemeye dikkat edin.

TableDef nesneleri oluşturma hakkında daha fazla bilgi için bkz. Class [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Bir TableDef nesnesi, `CDaoTableDef` nesnesini oluşturduğunuzda, veritabanı nesnesine bir işaretçi geçirerek belirli bir `CDaoDatabase` nesnesiyle ilişkili hale gelir.

İlgili bilgiler için, DAO yardımında "Yöntem silme" konusuna bakın.

##  <a name="execute"></a>CDaoDatabase:: Execute

Bir eylem sorgusu çalıştırmak veya veritabanında bir SQL ifadesini yürütmek için bu üye işlevi çağırın.

```
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Parametreler

*lpszSQL*<br/>
Yürütülecek geçerli bir SQL komutu içeren null ile sonlandırılmış bir dize işaretçisi.

*Önemli seçenekler*<br/>
Sorgunun bütünlüğüyle ilgili seçenekleri belirten bir tamsayı. Aşağıdaki sabitlerden herhangi birini birleştirmek için bit düzeyinde **&#124;** or işlecini () kullanabilirsiniz (örneğin, `dbInconsistent` `dbConsistent`ile birleştirmeyin):

- diğer kullanıcılara yazma iznini reddetme `dbDenyWrite`.

- `dbInconsistent` (varsayılan) tutarsız güncelleştirmeler.

- Tutarlı güncelleştirmeler `dbConsistent`.

- SQL geçişli `dbSQLPassThrough`. SQL ifadesinin işlenmek üzere bir ODBC veri kaynağına geçirilmesine neden olur.

- bir hata oluşursa güncelleştirmeleri geri alma `dbFailOnError`.

- `dbSeeChanges` başka bir Kullanıcı düzenlemekte olduğunuz verileri değiştirirken bir çalışma zamanı hatası oluşturur.

> [!NOTE]
>  `dbInconsistent` ve `dbConsistent` her ikisi de dahil edildiğinde veya belirtilmemişse, sonuç varsayılandır. Bu sabitlerin açıklaması için, DAO yardımı 'nda "yöntemi yürütme" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

`Execute` yalnızca eylem sorguları veya sonuç döndürmeyen SQL geçişli sorguları için geçerlidir. Kayıtları döndüren seçme sorguları için çalışmaz.

Eylem sorgularıyla ilgili bir tanım ve bilgiler için, DAO yardımı 'nda "eylem sorgusu" ve "çalıştırma yöntemi" konularına bakın.

> [!TIP]
>  Sözdizimi doğru SQL bildirisini ve uygun izinleri verildiğinde, tek bir satır değiştirilip değiştirilemediği veya silinebilse bile `Execute` üye işlevi başarısız olmaz. Bu nedenle, bir Update veya DELETE sorgusu çalıştırmak için `Execute` member işlevini kullanırken her zaman `dbFailOnError` seçeneğini kullanın. Bu seçenek, MFC 'nin [CDaoException](../../mfc/reference/cdaoexception-class.md) türünde bir özel durum oluşturmasını ve etkilenen kayıtlardan herhangi biri kilitliyse veya silinemediği takdirde tüm başarılı değişiklikleri geri kaydetmesine neden olur. Kaç kaydın etkilendiğini görmek için `GetRecordsAffected` her zaman çağırabileceğinizi unutmayın.

En son `Execute` çağrısından etkilenen kayıt sayısını öğrenmek için veritabanı nesnesinin [Getrecordsaetkilenmember](#getrecordsaffected) işlevini çağırın. Örneğin `GetRecordsAffected`, bir eylem sorgusu yürütürken silinen, güncellenen veya yerleştirilen kayıt sayısı hakkında bilgi döndürür. Döndürülen sayı, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

`Execute` bir kayıt kümesi döndürmez. Kayıtları seçen bir sorgu üzerinde `Execute` kullanmak, MFC 'nin `CDaoException`türünde bir özel durum oluşturmasına neden olur. (`CDatabase::ExecuteSQL`benzer bir `ExecuteSQL` üye işlevi yoktur.)

##  <a name="getconnect"></a>CDaoDatabase:: GetConnect

`CDaoDatabase` nesnesini bir ODBC veya ISAM veritabanına bağlamak için kullanılan bağlantı dizesini almak için bu üye işlevi çağırın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

ODBC veri kaynağında [açma](#open) başarıyla çağrılırsa bağlantı dizesi. Aksi takdirde, boş bir dize. Bir Microsoft Jet (. MDB) veritabanı ' nı kullanarak, üyeyi [Execute](#execute) işleviyle kullanılan `dbSQLPassThrough` seçeneği ile kullanmak üzere ayarlamadığınız veya bir kayıt kümesi açma bölümünde kullanılan dize her zaman boştur.

### <a name="remarks"></a>Açıklamalar

Dize, açık bir veritabanının kaynağı veya doğrudan geçiş sorgusunda kullanılan bir veritabanı hakkında bilgi sağlar. Bağlantı dizesi, bir veritabanı türü belirticisinden ve noktalı virgülle ayrılmış sıfır veya daha fazla parametreden oluşur.

> [!NOTE]
>  ODBC aracılığıyla bir veri kaynağına bağlanmak için MFC DAO sınıflarını kullanmak, ekli tablo aracılığıyla bağlanılarak daha az verimlidir.

> [!NOTE]
>  Bağlantı dizesi, gereken şekilde ODBC ve belirli ISAM sürücülerine ek bilgi geçirmek için kullanılır. İçin kullanılmaz. MDB veritabanları. Microsoft Jet veritabanı temel tabloları için bağlantı dizesi, yukarıdaki dönüş değeri altında açıklandığı gibi bir SQL geçişli sorgu için kullandığınız durumlar haricinde boş bir dizedir ("").

Bağlantı dizesinin nasıl oluşturulduğuna ilişkin bir açıklama için bkz. [Açık](#open) üye işlevi. `Open` çağrısında bağlantı dizesi ayarlandıktan sonra, veritabanının türünü, yolunu, kullanıcı KIMLIĞINI, parolasını veya ODBC veri kaynağını belirleme ayarını denetlemek için bunu daha sonra kullanabilirsiniz.

##  <a name="getname"></a>CDaoDatabase:: GetName

Mevcut bir veritabanı dosyasının adı veya kayıtlı bir ODBC veri kaynağı adı olan açık olan veritabanının adını almak için bu üye işlevi çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa veritabanının tam yolu ve dosya adı; Aksi halde boş bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

Ağınız Tekdüzen adlandırma kuralını (UNC) destekliyorsa, bir ağ yolu da belirtebilirsiniz — Örneğin, "\\\\\\\SUNUCUM\\\MYSHARE\\\MYDIR\\\MYDB. MDB ". ("\\" C++ kaçış karakteri olduğundan, dize sabit değerlerinde çift ters eğik çizgiler gereklidir.)

Örneğin, bu adı bir başlıkta göstermek isteyebilirsiniz. Ad alınırken bir hata oluşursa, MFC, [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur.

> [!NOTE]
>  Dış veritabanlarına erişildiğinde daha iyi performans için, dış veritabanı tablolarını bir Microsoft Jet veritabanına iliştirmenizi öneririz (. MDB) veri kaynağına doğrudan bağlanmak yerine.

Veritabanı türü, yolun gösterdiği dosya veya dizin tarafından aşağıdaki gibi belirtilir:

|Yol adı işaret eder..|Veritabanı türü|
|--------------------------|-------------------|
|. MDB dosyası|Microsoft Jet veritabanı (Microsoft Access)|
|İçeren dizin. DBF dosyaları|dBASE veritabanı|
|İçeren dizin. XLS dosyası|Microsoft Excel veritabanı|
|İçeren dizin. PDX dosyası (ler)|Paradox veritabanı|
|Uygun şekilde biçimlendirilen metin veritabanı dosyalarını içeren dizin|Metin biçimi veritabanı|

SQL Server ve Oracle gibi ODBC veritabanlarında, veritabanının bağlantı dizesi ODBC tarafından kaydedilen bir veri kaynağı adı 'nı (DSN) tanımlar.

##  <a name="getquerydefcount"></a>CDaoDatabase:: GetQueryDefCount

Veritabanının QueryDefs koleksiyonunda tanımlanan sorguların sayısını almak için bu üye işlevi çağırın.

```
short GetQueryDefCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanında tanımlanan sorgu sayısı.

### <a name="remarks"></a>Açıklamalar

`GetQueryDefCount`, QueryDefs koleksiyonundaki tüm QueryDefs 'ler aracılığıyla döngü uygulamanız gerekiyorsa yararlıdır. Koleksiyonda verilen bir sorgu hakkında bilgi edinmek için bkz. [Getquerydefinınfo](#getquerydefinfo).

##  <a name="getquerydefinfo"></a>CDaoDatabase:: Getquerydefinınfo

Veritabanında tanımlı bir sorgu hakkında çeşitli bilgiler almak için bu üye işlevini çağırın.

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

*nDizin*<br/>
Dizine göre arama için veritabanının QueryDefs koleksiyonundaki önceden tanımlanmış sorgunun dizini.

*querydefinınfo*<br/>
İstenen bilgileri döndüren bir [Cdaoquerydefinınfo](../../mfc/reference/cdaoquerydefinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Alınacak kayıt kümesiyle ilgili bilgileri belirleyen seçenekler. Kullanılabilir seçenekler, işlevin kayıt kümesi hakkında döndürmesine neden olan ile birlikte aşağıda listelenmiştir:

- AFX_DAO_PRIMARY_INFO (varsayılan) ad, tür

- AFX_DAO_SECONDARY_INFO birincil bilgileri Plus: Oluşturulma tarihi, son güncelleştirme tarihi, kayıtları döndüren kayıtlar, güncelleştirilebilir

- Birincil ve ikincil bilgileri AFX_DAO_ALL_INFO ve: SQL, Connect, ODBCTimeout

*lpszName*<br/>
Ada göre arama için veritabanında tanımlanmış bir sorgunun adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

İşlevin iki sürümü sağlanır, böylece veritabanının QueryDefs koleksiyonunda veya sorgunun adına göre bir sorgu seçebilirsiniz.

*Querydefinınfo*içinde döndürülen bilgilerin açıklaması Için, [cdaoquerydefinınfo](../../mfc/reference/cdaoquerydefinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions*açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzey bilgi istemeniz durumunda daha önceki bilgi seviyeleri de alırsınız.

##  <a name="getquerytimeout"></a>CDaoDatabase:: GetQueryTimeout

Bağlı veritabanındaki sonraki işlemler zaman aşımına uğramadan önce izin verilen geçerli saniye sayısını almak için bu üye işlevini çağırın.

```
short GetQueryTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Saniye cinsinden zaman aşımı değerini içeren kısa bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Ağ erişimi sorunları, aşırı sorgu işleme süresi vb. nedeniyle bir işlem zaman aşımına uğrar. Ayar etkin olsa da, bu `CDaoDatabase` nesnesiyle ilişkili tüm kayıt kümelerine açık, yeni, güncelleştirme ve silme işlemlerini etkiler. [SetQueryTimeout](#setquerytimeout)öğesini çağırarak geçerli zaman aşımı ayarını değiştirebilirsiniz. Açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirme, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki [taşıma](../../mfc/reference/cdaorecordset-class.md#move) işlemleri yeni değeri kullanmaz. Varsayılan değer Başlangıçta veritabanı altyapısı başlatıldığında ayarlanır.

Sorgu zaman aşımları için varsayılan değer Windows kayıt defterinden alınır. Kayıt defteri ayarı yoksa, varsayılan değer 60 saniyedir. Tüm veritabanları bir sorgu zaman aşımı değeri ayarlama yeteneğini desteklemez. 0 ' ın bir sorgu zaman aşımı değeri ayarlarsanız zaman aşımı oluşmaz; ve veritabanıyla iletişim vermeyi durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir. Çağrı başarısız olursa, MFC, [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur.

İlgili bilgiler için, DAO yardımı 'nda "QueryTimeout özelliği" konusuna bakın.

##  <a name="getrecordsaffected"></a>CDaoDatabase:: Getrecordsabetkilenen

[Execute](#execute) member işlevinin en son çağrısından etkilenen kayıt sayısını öğrenmek için bu üye işlevi çağırın.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Dönüş Değeri

Etkilenen kayıt sayısını içeren uzun bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer, `Execute`birlikte çalıştırılan bir eylem sorgusunun silindiği, güncelleştirildiği veya eklediği kayıt sayısını içerir. Döndürülen sayı, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

İlgili bilgiler için, DAO yardımı 'nda "Recordsaetkilenözelliği" konusuna bakın.

##  <a name="getrelationcount"></a>CDaoDatabase:: GetRelationCount

Veritabanındaki tablolar arasında tanımlanan ilişkilerin sayısını almak için bu üye işlevi çağırın.

```
short GetRelationCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanındaki tablolar arasında tanımlanan ilişki sayısı.

### <a name="remarks"></a>Açıklamalar

`GetRelationCount`, veritabanının Ilişkiler koleksiyonundaki tüm tanımlı ilişkilerce döngü oluşturmanız gerekiyorsa yararlıdır. Koleksiyonda belirli bir ilişki hakkında bilgi edinmek için bkz. [GetRelationInfo](#getrelationinfo).

Bir ilişki kavramını göstermek için bir Tedarikçiler tablosu ve bir Products tablosu düşünün ve bu, bire çok ilişkisine sahip olabilir. Bu ilişkide bir tedarikçi birden fazla ürün sağlayabilir. Diğer ilişkiler bire bir ve çoktan çoğa.

##  <a name="getrelationinfo"></a>CDaoDatabase:: GetRelationInfo

Veritabanının Ilişkiler koleksiyonunda belirtilen ilişki hakkında bilgi edinmek için bu üye işlevini çağırın.

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

*nDizin*<br/>
Dizine göre arama için veritabanının Ilişkiler koleksiyonundaki ilişki nesnesinin dizini.

*relinfo*<br/>
İstenen bilgileri döndüren bir [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Alınacak ilişki hakkındaki bilgileri belirten seçenekler. Kullanılabilir seçenekler, işlevin ilişki hakkında döndürmesine neden olan ile birlikte aşağıda listelenmiştir:

- AFX_DAO_PRIMARY_INFO (varsayılan) ad, tablo, yabancı tablo

- AFX_DAO_SECONDARY_INFO öznitelikleri, alan bilgileri

Alan bilgileri, ilişkide yer alan birincil tablodaki alanları içeren bir [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) nesnesidir.

*lpszName*<br/>
Ada göre arama için Relation nesnesinin adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Bu işlevin iki sürümü dizin ya da ada göre erişim sağlar. *Relinınfo*'da döndürülen bilgilerin açıklaması Için, [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions*açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bilgileri tek bir düzeyde istemeniz durumunda, önceki düzeylerin de bilgilerini de alabilirsiniz.

> [!NOTE]
>  Cascade işlemlerini etkinleştirmek için Relation nesnesinin özniteliklerini ayarlarsanız (`dbRelationUpdateCascades` veya `dbRelationDeleteCascades`), ilgili birincil anahtar tablolarında değişiklik yapıldığında Microsoft Jet veritabanı altyapısı bir veya daha fazla tablodaki kayıtları otomatik olarak güncelleştirir veya siler. Örneğin, bir müşteriler tablosu ve Siparişler tablosu arasında basamaklı bir silme ilişkisi oluşturduğunuzu varsayalım. Müşteriler tablosundan kayıtları sildiğinizde, bu müşteriyle ilgili Siparişler tablosundaki kayıtlar da silinir. Ayrıca, Siparişler tablosu ve diğer tablolar arasında basamaklı silme ilişkileri oluşturursanız, müşteriler tablosundan kayıtları sildiğinizde bu tablolardan kayıtlar otomatik olarak silinir.

##  <a name="gettabledefcount"></a>CDaoDatabase:: GetTableDefCount

Veritabanında tanımlı tablo sayısını almak için bu üye işlevini çağırın.

```
short GetTableDefCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanında tanımlanan tabledefs sayısı.

### <a name="remarks"></a>Açıklamalar

`GetTableDefCount`, veritabanının TableDefs koleksiyonundaki tüm TableDefs aracılığıyla döngü uygulamanız gerekiyorsa yararlıdır. Koleksiyonda verilen bir tablo hakkında bilgi edinmek için bkz. [Gettabledefinınfo](#gettabledefinfo).

##  <a name="gettabledefinfo"></a>CDaoDatabase:: Gettabledefinınfo

Veritabanında tanımlı bir tablo hakkında çeşitli bilgi türlerini almak için bu üye işlevini çağırın.

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

*nDizin*<br/>
Dizine göre arama için veritabanının TableDefs koleksiyonunda bulunan TableDef nesnesinin dizini.

*tabledefinfo*<br/>
İstenen bilgileri döndüren bir [Cdaotabledefinınfo](../../mfc/reference/cdaotabledefinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Alınacak tablo hakkındaki bilgileri belirten seçenekler. Kullanılabilir seçenekler, işlevin ilişki hakkında döndürmesine neden olan ile birlikte aşağıda listelenmiştir:

- AFX_DAO_PRIMARY_INFO (varsayılan) ad, güncelleştirilebilir, öznitelikler

- AFX_DAO_SECONDARY_INFO birincil bilgileri Plus: Oluşturulma tarihi, son tarih güncelleme, kaynak tablo adı, bağlanma

- Birincil ve ikincil bilgileri ve AFX_DAO_ALL_INFO: doğrulama kuralı, doğrulama metni, kayıt sayısı

*lpszName*<br/>
Ada göre arama için TableDef nesnesinin adı.

### <a name="remarks"></a>Açıklamalar

İşlevin iki sürümü sağlanır, böylece veritabanının TableDefs koleksiyonunda veya tablo adıyla bir tablo seçebilirsiniz.

*Tabledefinınfo*'da döndürülen bilgilerin açıklaması Için, [cdaotabledefinınfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions*açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istemeniz durumunda, önceki tüm düzeyler için de bilgi alırsınız.

> [!NOTE]
>  AFX_DAO_ALL_INFO seçeneği elde etmek için yavaş olabilecek bilgiler sağlar. Bu durumda, çok sayıda kayıt varsa tablodaki kayıtların sayımı çok zaman alabilir.

##  <a name="getversion"></a>CDaoDatabase:: GetVersion

Microsoft Jet veritabanı dosyasının sürümünü öğrenmek için bu üye işlevi çağırın.

```
CString GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnesiyle ilişkili veritabanı dosyasının sürümünü belirten bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Döndürülen değer "ana. ikincil" biçiminde sürüm numarasını temsil eder; Örneğin, "3,0". Ürün sürüm numarası (örneğin, 3,0) sürüm numarasından (3), bir noktayla ve yayın numarasından (0) oluşur. Güncel sürümler 1,0, 1,1, 2,0 ve 3,0.

İlgili bilgiler için, DAO yardımı 'nda "sürüm özelliği" konusuna bakın.

##  <a name="isopen"></a>CDaoDatabase:: IsOpen

`CDaoDatabase` nesnesinin bir veritabanında açık olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoDatabase` nesnesi şu anda açıksa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_pdaodatabase"></a>CDaoDatabase:: m_pDAODatabase

`CDaoDatabase` nesnesini temel alan DAO veritabanı nesnesi için OLE arabirimine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

DAO arabirimine doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.

DAO 'YU doğrudan çağırma hakkında daha fazla bilgi için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

##  <a name="m_pworkspace"></a>CDaoDatabase:: m_pWorkspace

Veritabanı nesnesini içeren [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Çalışma alanına doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın — örneğin, çalışma alanının veritabanları koleksiyonundaki diğer veritabanı nesnelerine işaretçiler elde etmek için.

##  <a name="open"></a>CDaoDatabase:: Open

Var olan bir veritabanını temsil eden yeni oluşturulmuş bir `CDaoDatabase` nesnesini başlatmak için bu üye işlevini çağırmanız gerekir.

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Var olan bir Microsoft Jet 'in adı olan bir dize ifadesi (. MDB) veritabanı dosyası. Dosya adının bir uzantısı varsa, bu gereklidir. Ağınız, Tekdüzen adlandırma kuralı 'nı (UNC) destekliyorsa, "\\\\\\\SUNUCUM\\\MYSHARE\\\ mydir\\\MYDBGIBI bir ağ yolu da belirtebilirsiniz. MDB ". ("\\" C++ kaçış karakteri olduğundan, dize sabit değerlerinde çift ters eğik çizgiler gereklidir.)

*LpszName*kullanılırken bazı konular geçerlidir. Eğer:

- Başka bir kullanıcı tarafından özel erişim için zaten açık olan bir veritabanını ifade eder, MFC, [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur. Kullanıcının veritabanının kullanılamadığını bilmesini sağlamak için bu özel durumu yakalar.

- Boş bir dizedir ("") ve *lpszConnect* "ODBC;" ise, kullanıcının bir veritabanı seçmesini sağlamak için tüm kayıtlı ODBC veri kaynağı adlarını listelerken bir iletişim kutusu görüntülenir. ODBC veri kaynaklarına doğrudan bağlantıları kullanmaktan kaçının; Bunun yerine eklenmiş bir tablo kullanın.

- Aksi halde, var olan bir veritabanına veya geçerli ODBC veri kaynağı adına başvurmaz, MFC `CDaoException`türünde bir özel durum oluşturur.

> [!NOTE]
>  DAO hata kodları hakkında daha fazla bilgi için bkz. DAOERR. H dosyası. İlgili bilgiler için, DAO yardımı 'nda "Yakalanabilir veri erişim hataları" konusuna bakın.

*bExclusive*<br/>
Veritabanı özel (paylaşılmayan) erişim için açılabiliyorsa TRUE, veritabanı paylaşılan erişim için açılacaksa FALSE olan bir Boolean değeri. Bu bağımsız değişkeni atlarsanız, veritabanı paylaşılan erişim için açılır.

*bReadOnly*<br/>
Veritabanı salt okuma erişimi için açılacaksa TRUE, veritabanı okuma/yazma erişimi için açılacaksa FALSE değeri. Bu bağımsız değişkeni atlarsanız, veritabanı okuma/yazma erişimi için açılır. Tüm bağımlı kayıt kümeleri bu özniteliği devralınır.

*lpszConnect*<br/>
Veritabanını açmak için kullanılan bir dize ifadesi. Bu dize ODBC bağlantı bağımsız değişkenlerini oluşturur. Kaynak dize sağlamak için özel ve salt okunurdur bağımsız değişkenlerini sağlamalısınız. Veritabanı bir Microsoft Jet veritabanı (. MDB), bu dize boş (""). Varsayılan değerin sözdizimi — **_T**("") — Unicode için taşınabilirlik ve uygulamanızın ANSI derlemeleri sağlar.

### <a name="remarks"></a>Açıklamalar

`Open`, veritabanını temel alınan DAO nesnesiyle ilişkilendirir. Veritabanı nesnesini, başlatılana kadar kayıt kümesi, TableDef veya QueryDef nesneleri oluşturmak için kullanamazsınız. `Open` veritabanı nesnesini ilişkili çalışma alanının veritabanları koleksiyonuna ekler.

Parametreleri aşağıdaki gibi kullanın:

- Bir Microsoft Jet (. MDB) veritabanı, *lpszName* parametresini kullanın ve *lpszConnect* parametresi için boş bir dize geçirin veya formun parola dizesini geçirin "; PWD = Password, veritabanı parola korumalıysa (. Yalnızca MDB veritabanları).

- ODBC veri kaynağını açarsanız, *lpszConnect* içinde GEÇERLI bir ODBC bağlantı dizesi geçirin ve *lpszName*'de boş bir dize geçirin.

İlgili bilgiler için, DAO yardımı 'nda "OpenDatabase yöntemi" konusuna bakın.

> [!NOTE]
>  ISAM veritabanları ve ODBC veri kaynakları dahil olmak üzere dış veritabanlarına erişirken daha iyi performans sağlamak için, dış veritabanı tablolarını bir Microsoft Jet Engine veritabanına (. MDB) veri kaynağına doğrudan bağlanmak yerine.

Örneğin, DBMS ana bilgisayarı kullanılamadığında bir bağlantı girişimi zaman aşımına uğrar. Bağlantı girişimi başarısız olursa, `Open` [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur.

Geri kalan açıklamalar yalnızca ODBC veritabanları için geçerlidir:

Veritabanı bir ODBC veritabanısa ve `Open` çağrındaki parametreler bağlantıyı oluşturmak için yeterli bilgi içermiyorsa, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açar. `Open`çağırdığınızda, bağlantı dizeniz *lpszConnect*, özel olarak depolanır ve [GetConnect](#getconnect) üye işlevi çağırarak kullanılabilir.

İsterseniz, kullanıcıdan bir parola gibi bilgileri almak için `Open` çağırmadan önce kendi iletişim kutusunu açabilir, ardından bu bilgileri `Open`geçirdiğiniz bağlantı dizesine ekleyebilirsiniz. Ya da geçirdiğiniz bağlantı dizesini (Belki de Windows kayıt defterinde) kaydederek uygulamanızın bir `CDaoDatabase` nesnesi üzerinde `Open` çağırdığı bir sonraki sefer yeniden kullanabilmek isteyebilirsiniz.

Bağlantı dizesini birden fazla oturum açma yetkilendirmesi (her biri farklı bir `CDaoDatabase` nesnesi için) veya veritabanına özgü diğer bilgileri iletmek için de kullanabilirsiniz.

##  <a name="setquerytimeout"></a>CDaoDatabase:: SetQueryTimeout

Bağlı veritabanındaki sonraki işlemlerin süresi geçmeden önce izin verilecek varsayılan saniye sayısını geçersiz kılmak için bu üye işlevi çağırın.

```
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>Parametreler

*nSaniye*<br/>
Sorgu girişiminden zaman aşımına uğramadan önce izin verilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Ağ erişim sorunları, aşırı sorgu işleme süresi vb. nedeniyle bir işlem zaman aşımına uğrar. Sorgu zaman aşımı değerini değiştirmek istiyorsanız kayıt kümenizin önüne veya kayıt kümenizin [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [Update](../../mfc/reference/cdaorecordset-class.md#update)veya [Delete](../../mfc/reference/cdaorecordset-class.md#delete) üye işlevlerini çağırmadan önce `SetQueryTimeout` çağırın. Bu ayar, bu `CDaoDatabase` nesnesiyle ilişkili herhangi bir kayıt kümesi için sonraki [Açık](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`, `Update`ve `Delete` çağrılarını etkiler. Açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirme, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki [taşıma](../../mfc/reference/cdaorecordset-class.md#move) işlemleri yeni değeri kullanmaz.

Sorgu zaman aşımları için varsayılan değer 60 saniyedir. Tüm veritabanları bir sorgu zaman aşımı değeri ayarlama yeteneğini desteklemez. 0 ' ın bir sorgu zaman aşımı değeri ayarlarsanız zaman aşımı oluşmaz; veritabanıyla iletişim yanıt vermeyi durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir.

İlgili bilgiler için, DAO yardımı 'nda "QueryTimeout özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoWorkspace Sınıfı](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
