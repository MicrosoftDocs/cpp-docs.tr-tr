---
description: 'Daha fazla bilgi edinin: CDaoDatabase sınıfı'
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
ms.openlocfilehash: 2044f24c2485071e0fa8930956e8ea15753047ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250978"
---
# <a name="cdaodatabase-class"></a>CDaoDatabase sınıfı

Veri erişim nesneleri (DAO) kullanarak bir Access veritabanı bağlantısını temsil eder. DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

## <a name="syntax"></a>Syntax

```
class CDaoDatabase : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoDatabase:: CDaoDatabase](#cdaodatabase)|Bir `CDaoDatabase` nesnesi oluşturur. `Open`Nesneyi bir veritabanına bağlamak için çağırın.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoDatabase:: CanTransact](#cantransact)|Veritabanı işlemleri destekliyorsa sıfır dışında bir değer döndürür.|
|[CDaoDatabase:: CanUpdate](#canupdate)|`CDaoDatabase`Nesne güncelleştirilebilir ise (salt okunurdur) sıfır dışında bir değer döndürür.|
|[CDaoDatabase:: Close](#close)|Veritabanı bağlantısını kapatır.|
|[CDaoDatabase:: Create](#create)|Temel alınan DAO veritabanı nesnesini oluşturur ve nesnesini başlatır `CDaoDatabase` .|
|[CDaoDatabase:: CreateRelation](#createrelation)|Veritabanındaki tablolar arasında yeni bir ilişki tanımlar.|
|[CDaoDatabase::D eleteQueryDef](#deletequerydef)|Veritabanının QueryDefs koleksiyonunda kaydedilen bir QueryDef nesnesini siler.|
|[CDaoDatabase::D eleteRelation](#deleterelation)|Veritabanındaki tablolar arasında varolan bir ilişkiyi siler.|
|[CDaoDatabase::D eleteTableDef](#deletetabledef)|Veritabanındaki bir tablonun tanımını siler. Bu, gerçek tabloyu ve tüm verilerini siler.|
|[CDaoDatabase:: Execute](#execute)|Bir eylem sorgusu yürütür. `Execute`Sonuçlar döndüren bir sorgu için çağırmak özel durum oluşturur.|
|[CDaoDatabase:: GetConnect](#getconnect)|Nesneyi bir veritabanına bağlamak için kullanılan bağlantı dizesini döndürür `CDaoDatabase` . ODBC için kullanılır.|
|[CDaoDatabase:: GetName](#getname)|Kullanılmakta olan veritabanının adını döndürür.|
|[CDaoDatabase:: GetQueryDefCount](#getquerydefcount)|Veritabanı için tanımlanan sorguların sayısını döndürür.|
|[CDaoDatabase:: Getquerydefinınfo](#getquerydefinfo)|Veritabanında tanımlanan belirli bir sorgu hakkında bilgi döndürür.|
|[CDaoDatabase:: GetQueryTimeout](#getquerytimeout)|Veritabanı sorgusu işlemlerinin zaman aşımına geçmesi için geçmesi gereken saniye sayısını döndürür. Tüm sonraki açık, yeni, güncelleştirme ve düzenleme işlemlerini ve ODBC veri kaynaklarına (yalnızca) çağrı gibi diğer işlemleri etkiler `Execute` .|
|[CDaoDatabase:: Getrecordsabetkilenen](#getrecordsaffected)|Son güncelleştirme, düzenleme veya ekleme işleminden etkilenen kayıt sayısını ya da öğesine yapılan çağrıyı döndürür `Execute` .|
|[CDaoDatabase:: GetRelationCount](#getrelationcount)|Veritabanındaki tablolar arasında tanımlanan ilişki sayısını döndürür.|
|[CDaoDatabase:: GetRelationInfo](#getrelationinfo)|Veritabanındaki tablolar arasında tanımlanan belirli bir ilişki hakkındaki bilgileri döndürür.|
|[CDaoDatabase:: GetTableDefCount](#gettabledefcount)|Veritabanında tanımlanan tablo sayısını döndürür.|
|[CDaoDatabase:: Gettabledefinınfo](#gettabledefinfo)|Veritabanında belirtilen tablo hakkındaki bilgileri döndürür.|
|[CDaoDatabase:: GetVersion](#getversion)|Veritabanıyla ilişkili veritabanı altyapısının sürümünü döndürür.|
|[CDaoDatabase:: IsOpen](#isopen)|`CDaoDatabase`Nesne şu anda bir veritabanına bağlıysa sıfır olmayan bir değer döndürür.|
|[CDaoDatabase:: Open](#open)|Bir veritabanına bağlantı kurar.|
|[CDaoDatabase:: SetQueryTimeout](#setquerytimeout)|Veritabanı sorgusu işlemlerinin (yalnızca ODBC veri kaynaklarında) zaman aşımına uğrar olan saniye sayısını ayarlar. Sonraki açık, yeni, güncelleştirme ve silme işlemlerini etkiler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoDatabase:: m_pDAODatabase](#m_pdaodatabase)|Temel alınan DAO veritabanı nesnesine yönelik bir işaretçi.|
|[CDaoDatabase:: m_pWorkspace](#m_pworkspace)|Veritabanını içeren ve işlem alanını tanımlayan [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine yönelik bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Desteklenen veritabanı biçimleri hakkında daha fazla bilgi için bkz. [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) üye işlevi. Bir bir veya daha fazla `CDaoDatabase` nesneniz, belirli bir "çalışma alanında" bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesi tarafından temsil edilen bir anda etkin olabilir. Çalışma alanı, veritabanları koleksiyonu olarak adlandırılan açık veritabanı nesnelerinin bir koleksiyonunu tutar.

## <a name="usage"></a>Kullanım

Kayıt kümesi nesneleri oluştururken örtük olarak veritabanı nesneleri oluşturabilirsiniz. Ancak, açıkça veritabanı nesneleri de oluşturabilirsiniz. Var olan bir veritabanını ile açık olarak kullanmak için `CDaoDatabase` aşağıdakilerden birini yapın:

- Açık bir `CDaoDatabase` [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine işaretçi geçirerek bir nesne oluşturun.

- Ya da `CDaoDatabase` çalışma alanını belirtmeden bir nesne oluşturun (MFC geçici bir çalışma alanı nesnesi oluşturur).

Yeni bir Microsoft Jet (. MDB) veritabanı, bir `CDaoDatabase` nesne oluşturun ve üye [Oluştur](#create) işlevini çağırın. Sonrasında *çağırmayın* `Open` `Create` .

Var olan bir veritabanını açmak için bir `CDaoDatabase` nesne oluşturun ve [Açık](#open) üye işlevini çağırın.

Bu tekniklerin herhangi biri, DAO veritabanı nesnesini çalışma alanının veritabanları koleksiyonuna ekler ve verilere bir bağlantı açar. Daha sonra, bağlantılı veritabanında çalıştırmak üzere [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)veya [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesneleri oluşturduğunuzda, bu nesnelere yönelik oluşturucuları nesneniz için bir işaretçi geçirin `CDaoDatabase` . Bağlantıyı kullanmayı bitirdiğinizde, [Close](#close) üye işlevini çağırın ve nesneyi yok edin `CDaoDatabase` . `Close` daha önce kapatılmayan tüm kayıt kümelerini kapatır.

## <a name="transactions"></a>İşlemler

Veritabanı işlem işleme çalışma alanı düzeyinde sağlanır — sınıfının [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans)ve [Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) üye işlevlerine bakın `CDaoWorkspace` .

## <a name="odbc-connections"></a>ODBC Bağlantıları

ODBC veri kaynakları ile çalışmanın önerilen yolu, dış tabloları bir Microsoft Jet 'e eklemektir (. MDB) veritabanı.

## <a name="collections"></a>Koleksiyonlar

Her veritabanı kendi TableDef, QueryDef, Recordset ve Relation nesneleri koleksiyonlarını korur. Sınıfı, `CDaoDatabase` Bu nesneleri işlemek için üye işlevleri sağlar.

> [!NOTE]
> Nesneler, MFC veritabanı nesnesinde değil, DAO 'da depolanır. MFC, TableDef, QueryDef ve Recordset nesneleri için sınıflar sağlar ancak ilişki nesneleri için kullanmaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoDatabase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="cdaodatabasecantransact"></a><a name="cantransact"></a> CDaoDatabase:: CanTransact

Veritabanının işlemlere izin verip içermediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanı işlemleri destekliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlemler, veritabanının çalışma alanında yönetilir.

## <a name="cdaodatabasecanupdate"></a><a name="canupdate"></a> CDaoDatabase:: CanUpdate

Nesnenin güncelleştirmelere izin verip içermediğini öğrenmek için bu üye işlevi çağırın `CDaoDatabase` .

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoDatabase`Nesne güncelleştirmelere izin veriyorsa sıfır olmayan BIR değer; Aksi takdirde 0, nesneyi açtığınızda *bReadOnly* içinde doğru geçtiğini `CDaoDatabase` veya veritabanının kendisinin salt okunur olduğunu belirtir. [Açık](#open) üye işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Veritabanı güncellenebilirliği hakkında daha fazla bilgi için, DAO yardımı 'nda "güncelleştirilebilir özellik" konusuna bakın.

## <a name="cdaodatabasecdaodatabase"></a><a name="cdaodatabase"></a> CDaoDatabase:: CDaoDatabase

Bir `CDaoDatabase` nesnesi oluşturur.

```
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```

### <a name="parameters"></a>Parametreler

*pWorkspace*<br/>
`CDaoWorkspace`Yeni veritabanı nesnesini içerecek nesneye yönelik bir işaretçi. NULL varsayılan değerini kabul ediyorsanız, Oluşturucu `CDaoWorkspace` varsayılan DAO çalışma alanını kullanan geçici bir nesne oluşturur. [M_pWorkspace](#m_pworkspace) veri üyesi aracılığıyla çalışma alanı nesnesine bir işaretçi alabilirsiniz.

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, yeni bir Microsoft Jet (. MDB) veritabanı, nesnenin üye [Oluştur](#create) işlevini çağırın. Bunun yerine, var olan bir veritabanını açarak nesnenin [Açık](#open) üye işlevini çağırın.

Nesnesiyle bitirdiğinizde, [Close](#close) üye işlevini çağırmanız ve sonra nesneyi yok etmeniz gerekir `CDaoDatabase` .

Nesneyi belge sınıfınıza katıştırmayı kullanışlı bulabilirsiniz `CDaoDatabase` .

> [!NOTE]
> `CDaoDatabase`Varolan bir nesneye işaretçi geçirmeden bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi açarsanız, nesne de örtük olarak oluşturulur `CDaoDatabase` . Bu veritabanı nesnesi, kayıt kümesi nesnesini kapattığınızda kapatılır.

## <a name="cdaodatabaseclose"></a><a name="close"></a> CDaoDatabase:: Close

Bir veritabanının bağlantısını kesmek ve veritabanıyla ilişkili açık kayıt kümelerini, TableDefs ve QueryDefs 'leri kapatmak için bu üye işlevi çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırabilmeniz için bu nesneleri kendiniz kapatmak iyi bir uygulamadır. Bir `CDaoDatabase` nesnenin kapatılması, ilişkili [çalışma alanındaki](../../mfc/reference/cdaoworkspace-class.md)veritabanları koleksiyonundan kaldırılır. `Close`Nesneyi yok etmez `CDaoDatabase` , aynı veritabanını veya farklı bir veritabanını açarak nesneyi yeniden kullanabilirsiniz.

> [!CAUTION]
> [](../../mfc/reference/cdaorecordset-class.md#update) `Close` Bir veritabanını kapatmadan önce açık olan tüm kayıt kümesi nesnelerinde, Update member işlevini (bekleyen düzenlemeler varsa) ve üye işlevini çağırın. Yığın üzerinde [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) veya nesneleri bildiren bir işlevden çıkarsanız, `CDaoDatabase` veritabanı kapatılır, kaydedilmemiş değişiklikler kaybolur, bekleyen tüm işlemler geri alınır ve verilerinizde bekleyen tüm düzenlemeler kaybedilir.

> [!CAUTION]
> Herhangi bir kayıt kümesi nesnesi açıkken bir veritabanı nesnesini kapatmaya çalışırsanız veya belirli bir çalışma alanına ait herhangi bir veritabanı nesnesi açıkken bir çalışma alanı nesnesini kapatmaya çalışırsanız, bu kayıt kümesi nesneleri kapatılır ve bekleyen güncelleştirmeler veya düzenlemeler geri alınacaktır. Bir çalışma alanı nesnesini, kendisine ait herhangi bir veritabanı nesnesi açık durumdayken kapatmaya çalışırsanız, işlem söz konusu çalışma alanı nesnesine ait tüm veritabanı nesnelerini kapatır ve bu, kapatılmamış kayıt kümesi nesnelerinin kapatılmasına neden olabilir. Veritabanı nesneniz kapanmaz, MFC hata ayıklama yapılarında bir onaylama hatası bildiriyor.

Veritabanı nesnesi bir işlevin kapsamı dışında tanımlıysa ve işlevden çıkmadan çıkarsanız, açıkça kapatılana veya tanımlandığı modül kapsam dışına çıkana kadar veritabanı nesnesi açık kalır.

## <a name="cdaodatabasecreate"></a><a name="create"></a> CDaoDatabase:: Create

Yeni bir Microsoft Jet (. MDB) veritabanı, bir nesnesi oluşturduktan sonra bu üye işlevini çağırın `CDaoDatabase` .

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int dwOptions = 0);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Oluşturmakta olduğunuz veritabanı dosyasının adı olan bir dize ifadesi. "C: \Mydb" gibi tam yol ve dosya adı olabilir \\ . MDB ". Bir ad belirtmeniz gerekir. Bir dosya adı uzantısı belirtmezseniz,. MDB eklenir. Ağınız Tekdüzen adlandırma kuralını (UNC) destekliyorsa, " \\ \\ \\ \sunucum \\ \ myshare \\ \mydizinim \\ \mydb" gibi bir ağ yolu da belirtebilirsiniz. Yalnızca Microsoft Jet (. MDB) veritabanı dosyaları, bu üye işlevi kullanılarak oluşturulabilir. ("" C++ kaçış karakteri olduğundan, dize değişmez değerlerinde çift ters eğik çizgiler gereklidir \\ .)

*lpszLocale*<br/>
Veritabanı oluşturmak için harmanlama sırasını belirtmek için kullanılan bir dize ifadesi. `dbLangGeneral` varsayılan değerdir. Olası değerler şunlardır:

- `dbLangGeneral` İngilizce, Almanca, Fransızca, Portekizce, Italyanca ve modern Ispanyolca

- `dbLangArabic` Arapça

- `dbLangCyrillic` Rusça

- `dbLangCzech` Çekçe

- `dbLangDutch` Hollanda dili

- `dbLangGreek` Yunanca

- `dbLangHebrew` İbranice

- `dbLangHungarian` Macarca

- `dbLangIcelandic` İzlanda dili

- `dbLangNordic` İskandinav dilleri (yalnızca Microsoft Jet veritabanı altyapısı sürüm 1,0)

- `dbLangNorwdan` Norveççe ve Danca

- `dbLangPolish` Lehçe

- `dbLangSpanish` Geleneksel Ispanyolca

- `dbLangSwedfin` İsveççe ve Fince

- `dbLangTurkish` Türkçe

*dwOptions*<br/>
Bir veya daha fazla seçeneği belirten tamsayı. Olası değerler şunlardır:

- `dbEncrypt` Şifrelenmiş bir veritabanı oluşturun.

- `dbVersion10` Microsoft Jet veritabanı sürüm 1,0 ile bir veritabanı oluşturun.

- `dbVersion11` Microsoft Jet veritabanı sürüm 1,1 ile bir veritabanı oluşturun.

- `dbVersion20` Microsoft Jet veritabanı sürüm 2,0 ile bir veritabanı oluşturun.

- `dbVersion30` Microsoft Jet veritabanı sürüm 3,0 ile bir veritabanı oluşturun.

Şifreleme sabitini atlarsanız, şifrelenmemiş bir veritabanı oluşturulur. Yalnızca bir sürüm sabiti belirtebilirsiniz. Bir sürüm sabitini atlarsanız, Microsoft Jet veritabanı sürüm 3,0 ' ı kullanan bir veritabanı oluşturulur.

> [!CAUTION]
> Bir veritabanı şifrelenmemişse, veritabanını oluşturan ikili disk dosyasını doğrudan okumak için Kullanıcı/parola güvenliği uygulasanız bile mümkündür.

### <a name="remarks"></a>Açıklamalar

`Create` veritabanı dosyasını ve temel alınan DAO veritabanı nesnesini oluşturur ve C++ nesnesini başlatır. Nesne, ilişkili çalışma alanının veritabanları koleksiyonuna eklenir. Veritabanı nesnesi açık durumda; sonrasında çağırmayın `Open*` `Create` .

> [!NOTE]
> İle `Create` , yalnızca Microsoft Jet (. MDB) veritabanları. ISAM veritabanları veya ODBC veritabanları oluşturamazsınız.

## <a name="cdaodatabasecreaterelation"></a><a name="createrelation"></a> CDaoDatabase:: CreateRelation

Veritabanındaki birincil tablodaki bir veya daha fazla alan ile yabancı tablodaki bir veya daha fazla alan arasında bir ilişki oluşturmak için bu üye işlevini çağırın (veritabanındaki başka bir tablo).

```cpp
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
İlişkide yabancı tablonun adı. Tablo yoksa, MFC türünde bir özel durum oluşturur `CDaoException` .

*lAttributes*<br/>
İlişki türü hakkında bilgi içeren uzun bir değer. Bu değeri, diğer şeyler arasında başvurusal bütünlüğü zorlamak için kullanabilirsiniz. Aşağıdaki değerlerden herhangi birini birleştirmek için bit düzeyinde OR işlecini ( **&#124;**) kullanabilirsiniz (bileşim anlamlı olduğu sürece):

- `dbRelationUnique` İlişki bire bir.

- `dbRelationDontEnforce` İlişki zorlanmaz (başvurusal bütünlük yok).

- `dbRelationInherited` İlişki, iki bağlantılı tabloyu içeren geçerli olmayan bir veritabanında bulunuyor.

- `dbRelationUpdateCascade` Güncelleştirmeler basamaklandıralınacaktır (daha fazla bilgi için bkz. açıklamalar).

- `dbRelationDeleteCascade` Silme işlemleri basamaklandıracaktır.

*lpszField*<br/>
Birincil tablodaki bir alanın adını içeren, null ile sonlandırılmış bir dize işaretçisi ( *lpszTable* tarafından adlandırılır).

*lpszForeignField*<br/>
Yabancı tablodaki bir alanın adını içeren, null ile sonlandırılmış bir dize işaretçisi ( *lpszForeignTable* tarafından adlandırılır).

*relinfo*<br/>
Oluşturmak istediğiniz ilişki hakkında bilgi içeren bir [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

İlişki, bir sorgu veya bir dış veritabanından ekli tablo içeremez.

İlişki iki tablonun her birinde bir alan içeriyorsa, işlevin ilk sürümünü kullanın. İlişki birden çok alan içeriyorsa ikinci sürümü kullanın. Bir ilişkide en fazla alan sayısı 14 ' dir.

Bu eylem, temeldeki bir DAO ilişki nesnesi oluşturur, ancak MFC 'nin ilişki nesnelerinin kapsüllenmesi sınıfının içinde bulunduğundan bu bir MFC Uygulama ayrıntısıdır `CDaoDatabase` . MFC, ilişkiler için bir sınıf sağlamaz.

Cascade işlemlerini etkinleştirmek için Relation nesnesinin özniteliklerini ayarlarsanız, ilgili birincil anahtar tablolarında değişiklik yapıldığında veritabanı altyapısı bir veya daha fazla tablodaki kayıtları otomatik olarak güncelleştirir veya siler.

Örneğin, bir müşteriler tablosu ve Siparişler tablosu arasında basamaklı bir silme ilişkisi oluşturduğunuzu varsayalım. Müşteriler tablosundan kayıtları sildiğinizde, bu müşteriyle ilgili Siparişler tablosundaki kayıtlar da silinir. Ayrıca, Siparişler tablosu ve diğer tablolar arasında basamaklı silme ilişkileri oluşturursanız, müşteriler tablosundan kayıtları sildiğinizde bu tablolardan kayıtlar otomatik olarak silinir.

İlgili bilgiler için, DAO yardımı 'nda "CreateRelation Yöntemi" konusuna bakın.

## <a name="cdaodatabasedeletequerydef"></a><a name="deletequerydef"></a> CDaoDatabase::D eleteQueryDef

Nesnenin QueryDefs koleksiyonundan belirtilen QueryDef (kaydedilmiş sorgu) öğesini silmek için bu üye işlevi çağırın `CDaoDatabase` .

```cpp
void DeleteQueryDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Silinecek kaydedilen sorgunun adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, bu sorgu artık veritabanında tanımlı değildir.

QueryDef nesneleri oluşturma hakkında daha fazla bilgi için bkz. Class [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Nesne oluşturduğunuzda bir QueryDef nesnesi belirli bir nesneyle ilişkili hale gelir `CDaoDatabase` `CDaoQueryDef` .

## <a name="cdaodatabasedeleterelation"></a><a name="deleterelation"></a> CDaoDatabase::D eleteRelation

Veritabanı nesnesinin Ilişkiler koleksiyonundan varolan bir ilişkiyi silmek için bu üye işlevi çağırın.

```cpp
void DeleteRelation(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Silinecek ilişkinin adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, ilişki artık mevcut değildir.

İlgili bilgiler için, DAO yardımında "Yöntem silme" konusuna bakın.

## <a name="cdaodatabasedeletetabledef"></a><a name="deletetabledef"></a> CDaoDatabase::D eleteTableDef

Belirtilen tabloyu ve tüm verilerini nesnenin TableDefs koleksiyonundan silmek için bu üye işlevi çağırın `CDaoDatabase` .

```cpp
void DeleteTableDef(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Silinecek TableDef 'in adı.

### <a name="remarks"></a>Açıklamalar

Daha sonra, bu tablo artık veritabanında tanımlı değildir.

> [!NOTE]
> Sistem tablolarını silmemeye dikkat edin.

TableDef nesneleri oluşturma hakkında daha fazla bilgi için bkz. Class [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Bir TableDef nesnesi, nesneyi oluşturduğunuzda belirli bir nesneyle ilişkili hale gelir `CDaoDatabase` `CDaoTableDef` ve bunu veritabanı nesnesine bir işaretçi geçirerek.

İlgili bilgiler için, DAO yardımında "Yöntem silme" konusuna bakın.

## <a name="cdaodatabaseexecute"></a><a name="execute"></a> CDaoDatabase:: Execute

Bir eylem sorgusu çalıştırmak veya veritabanında bir SQL ifadesini yürütmek için bu üye işlevi çağırın.

```cpp
void Execute(
    LPCTSTR lpszSQL,
    int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Parametreler

*lpszSQL*<br/>
Yürütülecek geçerli bir SQL komutu içeren null ile sonlandırılmış bir dize işaretçisi.

*Önemli seçenekler*<br/>
Sorgunun bütünlüğüyle ilgili seçenekleri belirten bir tamsayı. Aşağıdaki sabitlerden herhangi birini birleştirmek için bit düzeyinde OR işlecini ( **&#124;**) kullanabilirsiniz (örneğin, birlikte birleştirmenize gerek kalmadan `dbInconsistent` `dbConsistent` ):

- `dbDenyWrite` Diğer kullanıcılara yazma iznini reddetme.

- `dbInconsistent` Varsayılanını Tutarsız güncelleştirmeler.

- `dbConsistent` Tutarlı güncelleştirmeler.

- `dbSQLPassThrough` SQL geçişli. SQL ifadesinin işlenmek üzere bir ODBC veri kaynağına geçirilmesine neden olur.

- `dbFailOnError` Bir hata oluşursa güncelleştirmeleri geri alın.

- `dbSeeChanges` Düzenlediğiniz verileri başka bir Kullanıcı değiştiriyor ise, bir çalışma zamanı hatası oluşturun.

> [!NOTE]
> Her ikisi `dbInconsistent` de `dbConsistent` dahil edildiğinde veya belirtilmemişse, sonuç varsayılandır. Bu sabitlerin açıklaması için, DAO yardımı 'nda "yöntemi yürütme" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

`Execute` yalnızca eylem sorguları veya sonuç döndürmeyen SQL geçişli sorguları için geçerlidir. Kayıtları döndüren seçme sorguları için çalışmaz.

Eylem sorgularıyla ilgili bir tanım ve bilgiler için, DAO yardımı 'nda "eylem sorgusu" ve "çalıştırma yöntemi" konularına bakın.

> [!TIP]
> Sözdizimi doğru SQL bildirisini ve uygun izinleri verildiğinde, `Execute` tek bir satır değiştirilmeyebilir veya silinebilse bile üye işlevi başarısız olmaz. Bu nedenle, `dbFailOnError` `Execute` bir güncelleştirme veya silme sorgusunu çalıştırmak için üye işlevini kullanırken her zaman seçeneğini kullanın. Bu seçenek, MFC 'nin [CDaoException](../../mfc/reference/cdaoexception-class.md) türünde bir özel durum oluşturmasını ve etkilenen kayıtlardan herhangi biri kilitliyse veya silinemediği takdirde tüm başarılı değişiklikleri geri kaydetmesine neden olur. `GetRecordsAffected`Kaç kaydın etkilendiğini görmek için her zaman çağırabileceğinizi unutmayın.

En son çağrıdan etkilenen kayıt sayısını öğrenmek için veritabanı nesnesinin [Getrecordsaetkilenmember](#getrecordsaffected) işlevini çağırın `Execute` . Örneğin, `GetRecordsAffected` bir eylem sorgusu yürütürken silinen, güncellenen veya yerleştirilen kayıt sayısı hakkında bilgi döndürür. Döndürülen sayı, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

`Execute` bir kayıt kümesi döndürmez. `Execute`Kayıtları seçen bir sorgu üzerinde kullanmak, MFC 'nin türünde bir özel durum oluşturmasına neden olur `CDaoException` . ( `ExecuteSQL` Öğesine benzer bir üye işlevi yok `CDatabase::ExecuteSQL` .)

## <a name="cdaodatabasegetconnect"></a><a name="getconnect"></a> CDaoDatabase:: GetConnect

`CDaoDatabase`Nesneyi BIR ODBC veya ISAM veritabanına bağlamak için kullanılan bağlantı dizesini almak için bu üye işlevi çağırın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

ODBC veri kaynağında [açma](#open) başarıyla çağrılırsa bağlantı dizesi. Aksi takdirde, boş bir dize. Bir Microsoft Jet (. MDB) veritabanı, onu `dbSQLPassThrough` [Execute](#execute) veya bir kayıt kümesi açma bölümünde kullanılan seçenekle kullanılmak üzere ayarlamadığınız müddetçe, dize her zaman boştur.

### <a name="remarks"></a>Açıklamalar

Dize, açık bir veritabanının kaynağı veya doğrudan geçiş sorgusunda kullanılan bir veritabanı hakkında bilgi sağlar. Bağlantı dizesi, bir veritabanı türü belirticisinden ve noktalı virgülle ayrılmış sıfır veya daha fazla parametreden oluşur.

> [!NOTE]
> ODBC aracılığıyla bir veri kaynağına bağlanmak için MFC DAO sınıflarını kullanmak, ekli tablo aracılığıyla bağlanılarak daha az verimlidir.

> [!NOTE]
> Bağlantı dizesi, gereken şekilde ODBC ve belirli ISAM sürücülerine ek bilgi geçirmek için kullanılır. İçin kullanılmaz. MDB veritabanları. Microsoft Jet veritabanı temel tabloları için bağlantı dizesi, yukarıdaki dönüş değeri altında açıklandığı gibi bir SQL geçişli sorgu için kullandığınız durumlar haricinde boş bir dizedir ("").

Bağlantı dizesinin nasıl oluşturulduğuna ilişkin bir açıklama için bkz. [Açık](#open) üye işlevi. Çağrıda bağlantı dizesi ayarlandıktan sonra `Open` , bu ayarı daha sonra kullanarak veritabanının türünü, yolunu, Kullanıcı kimliğini, parolasını veya ODBC veri kaynağını belirleme ayarını denetleyebilirsiniz.

## <a name="cdaodatabasegetname"></a><a name="getname"></a> CDaoDatabase:: GetName

Mevcut bir veritabanı dosyasının adı veya kayıtlı bir ODBC veri kaynağı adı olan açık olan veritabanının adını almak için bu üye işlevi çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa veritabanının tam yolu ve dosya adı; Aksi halde boş bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

Ağınız Tekdüzen adlandırma kuralını (UNC) destekliyorsa, bir ağ yolu da belirtebilirsiniz — Örneğin, " \\ \\ \\ \sunucum \\ \ myshare \\ \mydizinim \\ \mydb. MDB ". ("" C++ kaçış karakteri olduğundan, dize değişmez değerlerinde çift ters eğik çizgiler gereklidir \\ .)

Örneğin, bu adı bir başlıkta göstermek isteyebilirsiniz. Ad alınırken bir hata oluşursa, MFC, [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur.

> [!NOTE]
> Dış veritabanlarına erişildiğinde daha iyi performans için, dış veritabanı tablolarını bir Microsoft Jet veritabanına iliştirmenizi öneririz (. MDB) veri kaynağına doğrudan bağlanmak yerine.

Veritabanı türü, yolun gösterdiği dosya veya dizin tarafından aşağıdaki gibi belirtilir:

|Yol adı işaret eder..|Veritabanı türü|
|--------------------------|-------------------|
|. MDB dosyası|Microsoft Jet veritabanı (Microsoft Access)|
|İçeren dizin. DBF dosyaları|dBASE veritabanı|
|İçeren dizin. XLS dosyası|Microsoft Excel veritabanı|
|İçeren dizin. PDX dosyası (ler)|Paradox veritabanı|
|Uygun şekilde biçimlendirilen metin veritabanı dosyalarını içeren dizin|Metin biçimi veritabanı|

SQL Server ve Oracle gibi ODBC veritabanlarında, veritabanının bağlantı dizesi ODBC tarafından kaydedilen bir veri kaynağı adı 'nı (DSN) tanımlar.

## <a name="cdaodatabasegetquerydefcount"></a><a name="getquerydefcount"></a> CDaoDatabase:: GetQueryDefCount

Veritabanının QueryDefs koleksiyonunda tanımlanan sorguların sayısını almak için bu üye işlevi çağırın.

```
short GetQueryDefCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanında tanımlanan sorgu sayısı.

### <a name="remarks"></a>Açıklamalar

`GetQueryDefCount` QueryDefs koleksiyonundaki tüm QueryDefs 'ler aracılığıyla döngü uygulamanız gerekiyorsa yararlıdır. Koleksiyonda verilen bir sorgu hakkında bilgi edinmek için bkz. [Getquerydefinınfo](#getquerydefinfo).

## <a name="cdaodatabasegetquerydefinfo"></a><a name="getquerydefinfo"></a> CDaoDatabase:: Getquerydefinınfo

Veritabanında tanımlı bir sorgu hakkında çeşitli bilgiler almak için bu üye işlevini çağırın.

```cpp
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

*Querydefinınfo* içinde döndürülen bilgilerin açıklaması Için, [cdaoquerydefinınfo](../../mfc/reference/cdaoquerydefinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions* açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzey bilgi istemeniz durumunda daha önceki bilgi seviyeleri de alırsınız.

## <a name="cdaodatabasegetquerytimeout"></a><a name="getquerytimeout"></a> CDaoDatabase:: GetQueryTimeout

Bağlı veritabanındaki sonraki işlemler zaman aşımına uğramadan önce izin verilen geçerli saniye sayısını almak için bu üye işlevini çağırın.

```
short GetQueryTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Saniye cinsinden zaman aşımı değerini içeren kısa bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Ağ erişimi sorunları, aşırı sorgu işleme süresi vb. nedeniyle bir işlem zaman aşımına uğrar. Ayar etkin olsa da, bu nesneyle ilişkili tüm kayıt kümelerinde tüm açık, yeni, güncelleştirme ve silme işlemlerini etkiler `CDaoDatabase` . [SetQueryTimeout](#setquerytimeout)öğesini çağırarak geçerli zaman aşımı ayarını değiştirebilirsiniz. Açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirme, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki [taşıma](../../mfc/reference/cdaorecordset-class.md#move) işlemleri yeni değeri kullanmaz. Varsayılan değer Başlangıçta veritabanı altyapısı başlatıldığında ayarlanır.

Sorgu zaman aşımları için varsayılan değer Windows kayıt defterinden alınır. Kayıt defteri ayarı yoksa, varsayılan değer 60 saniyedir. Tüm veritabanları bir sorgu zaman aşımı değeri ayarlama yeteneğini desteklemez. 0 ' ın bir sorgu zaman aşımı değeri ayarlarsanız zaman aşımı oluşmaz; ve veritabanıyla iletişim vermeyi durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir. Çağrı başarısız olursa, MFC, [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur.

İlgili bilgiler için, DAO yardımı 'nda "QueryTimeout özelliği" konusuna bakın.

## <a name="cdaodatabasegetrecordsaffected"></a><a name="getrecordsaffected"></a> CDaoDatabase:: Getrecordsabetkilenen

[Execute](#execute) member işlevinin en son çağrısından etkilenen kayıt sayısını öğrenmek için bu üye işlevi çağırın.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Dönüş Değeri

Etkilenen kayıt sayısını içeren uzun bir tamsayı.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer, ile birlikte çalıştırılan bir eylem sorgusunun silindiği, güncelleştirildiği veya eklediği kayıt sayısını içerir `Execute` . Döndürülen sayı, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

İlgili bilgiler için, DAO yardımı 'nda "Recordsaetkilenözelliği" konusuna bakın.

## <a name="cdaodatabasegetrelationcount"></a><a name="getrelationcount"></a> CDaoDatabase:: GetRelationCount

Veritabanındaki tablolar arasında tanımlanan ilişkilerin sayısını almak için bu üye işlevi çağırın.

```
short GetRelationCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanındaki tablolar arasında tanımlanan ilişki sayısı.

### <a name="remarks"></a>Açıklamalar

`GetRelationCount` veritabanının Ilişkiler koleksiyonundaki tüm tanımlı ilişkiler aracılığıyla döngü uygulamanız gerekiyorsa yararlıdır. Koleksiyonda belirli bir ilişki hakkında bilgi edinmek için bkz. [GetRelationInfo](#getrelationinfo).

Bir ilişki kavramını göstermek için bir Tedarikçiler tablosu ve bir Products tablosu düşünün ve bu, bire çok ilişkisine sahip olabilir. Bu ilişkide bir tedarikçi birden fazla ürün sağlayabilir. Diğer ilişkiler bire bir ve çoktan çoğa.

## <a name="cdaodatabasegetrelationinfo"></a><a name="getrelationinfo"></a> CDaoDatabase:: GetRelationInfo

Veritabanının Ilişkiler koleksiyonunda belirtilen ilişki hakkında bilgi edinmek için bu üye işlevini çağırın.

```cpp
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

Bu işlevin iki sürümü dizin ya da ada göre erişim sağlar. *Relinınfo*'da döndürülen bilgilerin açıklaması Için, [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions* açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bilgileri tek bir düzeyde istemeniz durumunda, önceki düzeylerin de bilgilerini de alabilirsiniz.

> [!NOTE]
> Cascade işlemlerini etkinleştirmek için Relation nesnesinin özniteliklerini ayarlarsanız ( `dbRelationUpdateCascades` veya `dbRelationDeleteCascades` ), ilgili birincil anahtar tablolarında değişiklik yapıldığında Microsoft Jet veritabanı altyapısı bir veya daha fazla tablodaki kayıtları otomatik olarak güncelleştirir veya siler. Örneğin, bir müşteriler tablosu ve Siparişler tablosu arasında basamaklı bir silme ilişkisi oluşturduğunuzu varsayalım. Müşteriler tablosundan kayıtları sildiğinizde, bu müşteriyle ilgili Siparişler tablosundaki kayıtlar da silinir. Ayrıca, Siparişler tablosu ve diğer tablolar arasında basamaklı silme ilişkileri oluşturursanız, müşteriler tablosundan kayıtları sildiğinizde bu tablolardan kayıtlar otomatik olarak silinir.

## <a name="cdaodatabasegettabledefcount"></a><a name="gettabledefcount"></a> CDaoDatabase:: GetTableDefCount

Veritabanında tanımlı tablo sayısını almak için bu üye işlevini çağırın.

```
short GetTableDefCount();
```

### <a name="return-value"></a>Dönüş Değeri

Veritabanında tanımlanan tabledefs sayısı.

### <a name="remarks"></a>Açıklamalar

`GetTableDefCount` veritabanının TableDefs koleksiyonundaki tüm TableDefs aracılığıyla döngü uygulamanız gerekiyorsa yararlıdır. Koleksiyonda verilen bir tablo hakkında bilgi edinmek için bkz. [Gettabledefinınfo](#gettabledefinfo).

## <a name="cdaodatabasegettabledefinfo"></a><a name="gettabledefinfo"></a> CDaoDatabase:: Gettabledefinınfo

Veritabanında tanımlı bir tablo hakkında çeşitli bilgi türlerini almak için bu üye işlevini çağırın.

```cpp
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

*Tabledefinınfo*'da döndürülen bilgilerin açıklaması Için, [cdaotabledefinınfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions* açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istemeniz durumunda, önceki tüm düzeyler için de bilgi alırsınız.

> [!NOTE]
> AFX_DAO_ALL_INFO seçeneği elde etmek için yavaş olabilecek bilgiler sağlar. Bu durumda, çok sayıda kayıt varsa tablodaki kayıtların sayımı çok zaman alabilir.

## <a name="cdaodatabasegetversion"></a><a name="getversion"></a> CDaoDatabase:: GetVersion

Microsoft Jet veritabanı dosyasının sürümünü öğrenmek için bu üye işlevi çağırın.

```
CString GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnesiyle ilişkili veritabanı dosyasının sürümünü belirten bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Döndürülen değer "ana. ikincil" biçiminde sürüm numarasını temsil eder; Örneğin, "3,0". Ürün sürüm numarası (örneğin, 3,0) sürüm numarasından (3), bir noktayla ve yayın numarasından (0) oluşur. Güncel sürümler 1,0, 1,1, 2,0 ve 3,0.

İlgili bilgiler için, DAO yardımı 'nda "sürüm özelliği" konusuna bakın.

## <a name="cdaodatabaseisopen"></a><a name="isopen"></a> CDaoDatabase:: IsOpen

`CDaoDatabase`Nesnenin şu anda bir veritabanında açık olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoDatabase`Nesne şu anda açıksa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaodatabasem_pdaodatabase"></a><a name="m_pdaodatabase"></a> CDaoDatabase:: m_pDAODatabase

Nesneyi temel alan DAO veritabanı nesnesi için OLE arabirimine yönelik bir işaretçi içerir `CDaoDatabase` .

### <a name="remarks"></a>Açıklamalar

DAO arabirimine doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.

DAO 'YU doğrudan çağırma hakkında daha fazla bilgi için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

## <a name="cdaodatabasem_pworkspace"></a><a name="m_pworkspace"></a> CDaoDatabase:: m_pWorkspace

Veritabanı nesnesini içeren [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Çalışma alanına doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın — örneğin, çalışma alanının veritabanları koleksiyonundaki diğer veritabanı nesnelerine işaretçiler elde etmek için.

## <a name="cdaodatabaseopen"></a><a name="open"></a> CDaoDatabase:: Open

`CDaoDatabase`Var olan bir veritabanını temsil eden yeni oluşturulmuş bir nesneyi başlatmak için bu üye işlevini çağırmanız gerekir.

```
virtual void Open(
    LPCTSTR lpszName,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T(""));
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Var olan bir Microsoft Jet 'in adı olan bir dize ifadesi (. MDB) veritabanı dosyası. Dosya adının bir uzantısı varsa, bu gereklidir. Ağınız Tekdüzen adlandırma kuralını (UNC) destekliyorsa, " \\ \\ \\ \sunucum \\ \ myshare \\ \ mydizinim \\ \ mydbgibi bir ağ yolu da belirtebilirsiniz. MDB ". ("" C++ kaçış karakteri olduğundan, dize değişmez değerlerinde çift ters eğik çizgiler gereklidir \\ .)

*LpszName* kullanılırken bazı konular geçerlidir. Eğer:

- Başka bir kullanıcı tarafından özel erişim için zaten açık olan bir veritabanını ifade eder, MFC, [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur. Kullanıcının veritabanının kullanılamadığını bilmesini sağlamak için bu özel durumu yakalar.

- Boş bir dizedir ("") ve *lpszConnect* "ODBC;" ise, kullanıcının bir veritabanı seçmesini sağlamak için tüm kayıtlı ODBC veri kaynağı adlarını listelerken bir iletişim kutusu görüntülenir. ODBC veri kaynaklarına doğrudan bağlantıları kullanmaktan kaçının; Bunun yerine eklenmiş bir tablo kullanın.

- Aksi halde, var olan bir veritabanına veya geçerli ODBC veri kaynağı adına başvurmaz, MFC türünde bir özel durum oluşturur `CDaoException` .

> [!NOTE]
> DAO hata kodları hakkında daha fazla bilgi için bkz. DAOERR. H dosyası. İlgili bilgiler için, DAO yardımı 'nda "Yakalanabilir veri erişim hataları" konusuna bakın.

*bExclusive*<br/>
Veritabanı özel (paylaşılmayan) erişim için açılabiliyorsa TRUE, veritabanı paylaşılan erişim için açılacaksa FALSE olan bir Boolean değeri. Bu bağımsız değişkeni atlarsanız, veritabanı paylaşılan erişim için açılır.

*bReadOnly*<br/>
Veritabanı salt okuma erişimi için açılacaksa TRUE, veritabanı okuma/yazma erişimi için açılacaksa FALSE değeri. Bu bağımsız değişkeni atlarsanız, veritabanı okuma/yazma erişimi için açılır. Tüm bağımlı kayıt kümeleri bu özniteliği devralınır.

*lpszConnect*<br/>
Veritabanını açmak için kullanılan bir dize ifadesi. Bu dize ODBC bağlantı bağımsız değişkenlerini oluşturur. Kaynak dize sağlamak için özel ve salt okunurdur bağımsız değişkenlerini sağlamalısınız. Veritabanı bir Microsoft Jet veritabanı (. MDB), bu dize boş (""). Varsayılan değerin sözdizimi — **_T**("") — Unicode için taşınabilirlik ve uygulamanızın ANSI derlemeleri sağlar.

### <a name="remarks"></a>Açıklamalar

`Open` veritabanını temel alınan DAO nesnesiyle ilişkilendirir. Veritabanı nesnesini, başlatılana kadar kayıt kümesi, TableDef veya QueryDef nesneleri oluşturmak için kullanamazsınız. `Open` veritabanı nesnesini ilişkili çalışma alanının veritabanları koleksiyonuna ekler.

Parametreleri aşağıdaki gibi kullanın:

- Bir Microsoft Jet (. MDB) veritabanı, *lpszName* parametresini kullanın ve *lpszConnect* parametresi için boş bir dize geçirin veya formun parola dizesini geçirin "; PWD = Password, veritabanı parola korumalıysa (. Yalnızca MDB veritabanları).

- ODBC veri kaynağını açarsanız, *lpszConnect* içinde GEÇERLI bir ODBC bağlantı dizesi geçirin ve *lpszName*'de boş bir dize geçirin.

İlgili bilgiler için, DAO yardımı 'nda "OpenDatabase yöntemi" konusuna bakın.

> [!NOTE]
> ISAM veritabanları ve ODBC veri kaynakları dahil olmak üzere dış veritabanlarına erişirken daha iyi performans sağlamak için, dış veritabanı tablolarını bir Microsoft Jet Engine veritabanına (. MDB) veri kaynağına doğrudan bağlanmak yerine.

Örneğin, DBMS ana bilgisayarı kullanılamadığında bir bağlantı girişimi zaman aşımına uğrar. Bağlantı girişimi başarısız olursa, `Open` [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur.

Geri kalan açıklamalar yalnızca ODBC veritabanları için geçerlidir:

Veritabanı bir ODBC veritabanısa ve `Open` çağrınızdan parametreler bağlantıyı oluşturmak için yeterli bilgi içermiyorsa, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açar. ' İ çağırdığınızda, `Open` bağlantı dizeniz *lpszConnect*, özel olarak depolanır ve [GetConnect](#getconnect) üye işlevi çağırarak kullanılabilir.

İsterseniz, kullanıcıdan bir parola gibi bilgi almak için çağrı yapmadan önce kendi iletişim kutusunu açabilir `Open` ve sonra bu bilgileri geçirdiğiniz bağlantı dizesine ekleyebilirsiniz `Open` . Ya da geçirdiğiniz bağlantı dizesini (Belki de Windows kayıt defterinde) kaydederek uygulamanızın bir dahaki sefer bir nesne aradığında yeniden kullanabilmek isteyebilirsiniz `Open` `CDaoDatabase` .

Bağlantı dizesini birden fazla oturum açma yetkilendirmesi (her biri farklı bir `CDaoDatabase` nesne için) veya veritabanına özgü diğer bilgileri iletmek için de kullanabilirsiniz.

## <a name="cdaodatabasesetquerytimeout"></a><a name="setquerytimeout"></a> CDaoDatabase:: SetQueryTimeout

Bağlı veritabanındaki sonraki işlemlerin süresi geçmeden önce izin verilecek varsayılan saniye sayısını geçersiz kılmak için bu üye işlevi çağırın.

```cpp
void SetQueryTimeout(short nSeconds);
```

### <a name="parameters"></a>Parametreler

*nSaniye*<br/>
Sorgu girişiminden zaman aşımına uğramadan önce izin verilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Ağ erişim sorunları, aşırı sorgu işleme süresi vb. nedeniyle bir işlem zaman aşımına uğrar. `SetQueryTimeout`Sorgu zaman aşımı değerini değiştirmek istiyorsanız kayıt kümenizin önüne veya kayıt kümesinin [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [Update](../../mfc/reference/cdaorecordset-class.md#update)veya [Delete](../../mfc/reference/cdaorecordset-class.md#delete) üye işlevlerini çağırmadan önce çağırın. Bu ayar sonraki [Açık](../../mfc/reference/cdaorecordset-class.md#open), `AddNew` , `Update` , ve `Delete` Bu nesneyle ilişkili tüm kayıt kümelerine yapılan çağrıları etkiler `CDaoDatabase` . Açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirme, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki [taşıma](../../mfc/reference/cdaorecordset-class.md#move) işlemleri yeni değeri kullanmaz.

Sorgu zaman aşımları için varsayılan değer 60 saniyedir. Tüm veritabanları bir sorgu zaman aşımı değeri ayarlama yeteneğini desteklemez. 0 ' ın bir sorgu zaman aşımı değeri ayarlarsanız zaman aşımı oluşmaz; veritabanıyla iletişim yanıt vermeyi durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir.

İlgili bilgiler için, DAO yardımı 'nda "QueryTimeout özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CDaoException sınıfı](../../mfc/reference/cdaoexception-class.md)
