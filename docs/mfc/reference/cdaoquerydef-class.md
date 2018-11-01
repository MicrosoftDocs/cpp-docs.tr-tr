---
title: CDaoQueryDef sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
helpviewer_keywords:
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
ms.openlocfilehash: 07c508dcf4bd57855d09be5a305847d0b2981305
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664535"
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef sınıfı

Bir sorgu tanımını veya "querydef" genellikle bir bir veritabanında kayıtlı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Oluşturur bir `CDaoQueryDef` nesne. Sonraki çağrı `Open` veya `Create`gereksinimlerinize bağlı olarak.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoQueryDef::Append](#append)|Querydef veritabanının QueryDefs koleksiyonu olarak kaydedilmiş bir sorgu ekler.|
|[CDaoQueryDef::CanUpdate](#canupdate)|Sorgu veritabanı güncelleştirebilirsiniz, sıfır döndürür.|
|[CDaoQueryDef::Close](#close)|QueryDefs kapatır. İle işiniz bittiğinde, C++ nesne yok.|
|[CDaoQueryDef::Create](#create)|DAO querydef nesnesini oluşturur. Bir geçici sorgu veya çağrı querydef kullanmak `Append` veritabanına kaydetmek için.|
|[CDaoQueryDef::Execute](#execute)|QueryDefs tarafından tanımlanan sorguyu yürütür.|
|[CDaoQueryDef::GetConnect](#getconnect)|Querydef ile ilişkili bağlantı dizesini döndürür. Veri kaynağı bağlantı dizesini tanımlar. (SQL için doğrudan Aksi takdirde boş bir dize sorgular.)|
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Kaydedilen sorgu oluşturulduğu tarihi döndürür.|
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Kaydedilen sorgu en son güncelleştirildiği tarihi döndürür.|
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Querydef tarafından tanımlanan alanların sayısını döndürür.|
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Sorguda tanımlanan belirtilen bir alan hakkında bilgi döndürür.|
|[CDaoQueryDef::GetName](#getname)|Querydef adını döndürür.|
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|(ODBC sorgu için) ODBC tarafından kullanılan zaman aşımı değerini döndürür querydef zaman yürütülür. Bu sorgunun eylemi için izin vermek ne kadar süreyle belirler.|
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Sorgu için tanımlanan parametrelerin sayısını döndürür.|
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Sorgu için belirtilen parametre hakkında bilgi döndürür.|
|[CDaoQueryDef::GetParamValue](#getparamvalue)|Sorgu için belirtilen parametre değeri döndürür.|
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Bir eylem sorgu tarafından etkilenen kayıtların sayısını döndürür.|
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Kayıtları querydef tarafından tanımlanan sorgu döndürmesi durumunda sıfır döndürür.|
|[CDaoQueryDef::GetSQL](#getsql)|Querydef tarafından tanımlanan sorgu belirten SQL dizesi döndürür.|
|[CDaoQueryDef::GetType](#gettype)|Sorgu türünü döndürür: silme, güncelleştirme, ekleme, tablo oluşturma ve benzeri.|
|[CDaoQueryDef::IsOpen](#isopen)|Querydef açıksa ve yürütülebilecek sıfır döndürür.|
|[CDaoQueryDef::Open](#open)|Veritabanının QueryDefs koleksiyonu içinde depolandığında var olan bir querydef açılır.|
|[CDaoQueryDef::SetConnect](#setconnect)|Bir ODBC veri kaynağında bir SQL sorgusunu doğrudan bağlantı dizesini ayarlar.|
|[CDaoQueryDef::SetName](#setname)|Querydef oluşturulduğunda adıyla değiştirerek kaydedilmiş sorgu adını ayarlar.|
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|Zaman aşımı değerini (ODBC sorgu için) ODBC tarafından kullanılan ayarlar querydef zaman yürütülür.|
|[CDaoQueryDef::SetParamValue](#setparamvalue)|Sorgu için belirtilen parametre değerini ayarlar.|
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Querydef kayıtları döndürüp döndürmeyeceğini belirtir. Bu özniteliği TRUE olarak ayarlamak yalnızca doğrudan SQL sorguları için geçerlidir.|
|[CDaoQueryDef::SetSQL](#setsql)|Querydef tarafından tanımlanan sorgu belirten SQL dizesini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|DAO querydef nesnesini OLE arabirimi için bir işaretçi.|
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Bir işaretçi `CDaoDatabase` querydef olduğu ilişkili nesne. Querydef veritabanında veya kaydedilmiş olabilir.|

## <a name="remarks"></a>Açıklamalar

Bir sorgu ve "Oluşturma tarihi" ve "ODBC zaman aşımı." gibi özelliklerini açıklayan SQL deyimi içeren bir veri erişim nesnesi bir querydef olduğu Kaydetmeden geçici querydef nesneleri oluşturabilirsiniz, ancak uygun olan — ve çok daha verimli — yaygın olarak kaydetmek için bir veritabanı sorguları yeniden kullanılabilir. A [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne tutar, kaydedilmiş querydefs içeren QueryDefs koleksiyonu adlı bir koleksiyon.

> [!NOTE]
>  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) üzerinde göre MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile ODBC veri kaynaklarına erişim yine de kullanabilirsiniz. Genel olarak, üzerinde DAO göre MFC sınıflarını ODBC tabanlı MFC sınıfları daha yetenekli; DAO dayalı sınıflar kendi veritabanı altyapısı aracılığıyla ODBC sürücüleri dahil olmak üzere, verilere erişebilir. DAO dayalı sınıflar da DAO doğrudan çağırmak zorunda kalmadan tablo sınıfları aracılığıyla ekleme gibi veri tanımlama dili (DDL) işlemleri destekler.

## <a name="usage"></a>Kullanım

QueryDef nesneleri ya da bir sorgu kaydedilen varolan ile çalışmak için veya yeni bir sorgu veya geçici bir sorgu kaydedilen kullanın:

1. Her durumda, ilk oluşturmak bir `CDaoQueryDef` nesne, işaretçi sağlayan [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) sorgunun ait olduğu nesne.

1. Ardından istediğinize bağlı olarak aşağıdakileri yapın:

   - Mevcut bir sorgu kaydedilen kullanmak için querydef nesnesinin çağrı [açık](#open) üye işlevi, kaydedilmiş sorgu adını belirtin.

   - Yeni kaydedilmiş bir sorgu oluşturmak için querydef nesnesinin çağrı [Oluştur](#create) üye işlevi, sorgunun adını belirtin. Ardından çağırın [ekleme](#append) veritabanının QueryDefs koleksiyonu için ekleyerek sorguyu kaydetmek için. `Create` querydef açık bir duruma koyar arama sonra bunu `Create` çağrılmayan `Open`.

   - Bir sorgudaki çağrısı `Create`. Sorgu adı için boş bir dize olarak geçirin. Çağırmayın `Append`.

QueryDefs kullanmayı bitirdiğinizde, arama, [Kapat](#close) üye işlev; ardından QueryDefs yok.

> [!TIP]
>  Kaydedilmiş sorgular oluşturmak için en kolay yolu, bunları oluşturabilir ve bunları Microsoft Access kullanarak veritabanınızda depolamak sağlamaktır. Ardından açın ve bunları MFC kodunuzda kullanın.

## <a name="purposes"></a>Amaçları

QueryDefs herhangi biri aşağıdaki amaçlar için kullanabilirsiniz:

- Oluşturmak için bir `CDaoRecordset` nesnesi

- Nesnenin çağrılacak `Execute` doğrudan eylem sorgusu veya doğrudan bir SQL sorgusunu yürütmek için üye işlevi

Sorgu seçme, eylem, çapraz, silme, güncelleştirme dahil olmak üzere, her tür için QueryDefs kullanın, ekleme, tablo oluşturma, veri tanımı, doğrudan SQL, UNION ve sorguları toplu. Sorgu türü sağladığınız SQL deyimini içeriğini tarafından belirlenir. Sorgu türleri hakkında daha fazla bilgi için bkz. `Execute` ve [GetType](#gettype) üye işlevleri. Kayıt kümeleri, satır döndürmek için yaygın olarak kullanılır, genellikle kullananlar sorgular **seçin... GELEN** anahtar sözcükleri. `Execute` toplu işlemleri için en yaygın olarak kullanılır. Daha fazla bilgi için [yürütme](#execute) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

## <a name="querydefs-and-recordsets"></a>QueryDefs ve kayıt kümeleri

QueryDefs oluşturmak için kullanılacak bir `CDaoRecordset` nesne, genellikle oluşturun veya yukarıda açıklanan şekilde bir querydef açın. Ardından çağırdığınızda querydef nesneniz için bir işaretçi işleve bir kayıt kümesi nesnesi oluşturmak [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Geçirdiğiniz querydef açık durumda olması gerekir. Daha fazla bilgi için bkz. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Açık durumda olmadığı sürece bir kayıt kümesi (bir querydef en yaygın kullanımı) oluşturmak için bir querydef kullanamazsınız. Ya da çağırarak querydef açık olmayan bir duruma yerleştirmek `Open` veya `Create`.

## <a name="external-databases"></a>Dış veritabanları

QueryDef nesneleri, bir dış veritabanı altyapısı'nın yerel SQL diyalekti kullanmak için tercih edilen yoludur. Örneğin, (Microsoft SQL Server üzerinde kullanılan gibi) bir Transact SQL sorgusu oluşturun ve querydef nesnesi içinde depolamak. Microsoft Jet veritabanı altyapısını temel alan olmayan bir SQL sorgusu kullanmanın gerektiğinde, dış veri kaynağına işaret eden bir bağlantı dizesi sağlamanız gerekir. Geçerli bağlantı dizelerini sorgularla veritabanı altyapısı atlamak ve işleme için dış veritabanı sunucusu için doğrudan sorgu geçirin.

> [!TIP]
>  ODBC tabloları ile çalışmak için tercih edilen yol için bir Microsoft Jet eklenecek olan (. MDB) veritabanı.

İlgili bilgiler için "QueryDef nesne", "QueryDefs koleksiyonu" ve "CdbDatabase nesne" DAO SDK konulara bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="append"></a>  CDaoQueryDef::Append

Çağırdıktan sonra bu üye işlevi çağrısı [Oluştur](#create) yeni QueryDefs oluşturmak için.

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

`Append` querydef veritabanının QueryDefs koleksiyonu için nesne ekleyerek veritabanına kaydeder. Ekleme olmadan, geçici bir nesne olarak querydef kullanabilirsiniz, ancak kalıcı hale getirmek istiyorsanız, çağırmalıdır `Append`.

Geçici QueryDefs eklenecek çalışırsanız, MFC türünde bir özel durum oluşturur. [CDaoException](../../mfc/reference/cdaoexception-class.md).

##  <a name="canupdate"></a>  CDaoQueryDef::CanUpdate

Querydef değişiklik olup olmadığını belirlemek için bu üye işlevi çağrısı — adını veya SQL dizesi değiştirme gibi.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef değiştirmek için izin verilen olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa querydef değiştirebilirsiniz:

- Bu salt okunur açık bir veritabanını temel alan değil.

- Veritabanı Güncelleştirme izinlerine sahip olduğunuz.

   Bu, güvenlik özellikleri olup uyguladıysanız üzerinde bağlıdır. MFC güvenlik için destek sağlamaz; bunu kendiniz DAO'yu doğrudan çağırma veya Microsoft Access kullanarak uygulamanız gerekir. DAO Yardımı'nda "izinleri özelliği" konusuna bakın.

##  <a name="cdaoquerydef"></a>  CDaoQueryDef::CDaoQueryDef

Oluşturur bir `CDaoQueryDef` nesne.

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Açık bir işaretçiye [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Nesne, veritabanının QueryDefs koleksiyonu, koleksiyonda depolanacak yeni bir sorgu veya değil depolanması için bir geçici sorgu depolanan var olan bir querydef temsil edebilir. Sonraki adımınız querydef türüne bağlıdır:

- Mevcut bir querydef nesneyi temsil ediyorsa, nesnenin çağrı [açık](#open) başlatmak üzere üye işlevi.

- Kaydedilecek yeni bir querydef nesneyi temsil ediyorsa, nesnenin çağrı [Oluştur](#create) üye işlevi. Bu veritabanının QueryDefs koleksiyonu için nesneye ekler. Ardından çağırın `CDaoQueryDef` üye işlevleri nesnenin özniteliklerini ayarlayın. Son olarak, çağrı [ekleme](#append).

- Nesne geçici bir querydef (veritabanında kaydedilecek değil) temsil ediyorsa, çağrı `Create`, sorgunun adı için boş bir dizeye geçiliyor. Arama sonra `Create`, querydef doğrudan özniteliklerini ayarlayarak başlatın. Çağırmayın `Append`.

Querydef özniteliklerini ayarlamak için kullanabileceğiniz [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout)ve [SetReturnsRecords](#setreturnsrecords) üye işlevleri.

QueryDefs ile işiniz bittiğinde, arama, [Kapat](#close) üye işlevi. Querydef işaretçiniz varsa, kullanmak **Sil** işlecini C++ nesne yok.

##  <a name="close"></a>  CDaoQueryDef::Close

QueryDefs kullanmayı bitirdiğinizde, bu üye işlevini çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

DAO nesnesini serbest ancak kaydedilen DAO QueryDefs ya da C++ silmiyor querydef kapatma `CDaoQueryDef` nesne. Bu aynı değil [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), veritabanının QueryDefs koleksiyonu DAO (geçici querydef değilse), gelen querydef silen.

##  <a name="create"></a>  CDaoQueryDef::Create

Yeni kaydedilmiş bir sorgu veya yeni bir geçici sorgu oluşturmak için bu üye işlevini çağırın.

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Veritabanında kayıtlı sorgu benzersiz adı. Dize hakkında daha fazla ayrıntı için DAO Yardımı'nda "CreateQueryDef yöntemi" konusuna bakın. Varsayılan değer, boş bir dize kabul ederseniz, geçici bir querydef oluşturulur. Böyle bir sorguyu QueryDefs koleksiyonu kaydedilmez.

*lpszSQL*<br/>
Sorgu tanımlar SQL dizesi. NULL varsayılan değeri kabul ederseniz, daha sonra çağırmalısınız [SetSQL](#setsql) dize ayarlamak için. O zamana kadar sorgu tanımsızdır. Ancak, bir kayıt kümesi açmak için tanımlanmamış sorgu kullanabilirsiniz; Açıklamalar, Ayrıntılar için bkz. SQL deyimi querydef QueryDefs koleksiyonu için eklemeden önce tanımlanmalıdır.

### <a name="remarks"></a>Açıklamalar

Bir ad geçirirseniz *lpszName*, ardından çağırabilirsiniz [ekleme](#append) querydef veritabanının QueryDefs koleksiyonu kaydedilecek. Aksi takdirde, nesne geçici bir querydef ve kaydedilmez. Her iki durumda da querydef bir açık durumda ve ya da bunu oluşturmak için kullanabileceğiniz bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesne veya querydef ait arama [yürütme](#execute) üye işlevi.

Bir SQL deyiminde sağlamazsanız *lpszSQL*, sorgu ile çalıştıramazsınız `Execute` ancak bir kayıt kümesi oluşturmak için kullanabilirsiniz. Bu durumda, MFC, kayıt kümesinin varsayılan SQL deyimini kullanır.

##  <a name="execute"></a>  CDaoQueryDef::Execute

QueryDefs tarafından tanımlanan sorguyu çalıştırmak için bu üye işlevini çağırın.

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Parametreler

*nOptions*<br/>
Sorgu özelliklerini belirleyen bir tamsayı. İlgili bilgiler için DAO Yardımı'nda "yöntemi Çalıştır" konusuna bakın. Bit düzeyinde OR işleci kullanabilirsiniz ( **&#124;**) bu bağımsız değişkeni aşağıdaki sabitler birleştirmek için:

- `dbDenyWrite` Diğer kullanıcılara yazma izni reddetme.

- `dbInconsistent` Tutarsız güncelleştirmeler.

- `dbConsistent` Tutarlı güncelleştirmeler.

- `dbSQLPassThrough` SQL doğrudan. İşleme için bir ODBC veritabanı için geçirilecek SQL deyimi neden olur.

- `dbFailOnError` Varsayılan değer. Kullanıcıya bir hata oluşursa güncelleştirmeleri ve hata rapor geri alma.

- `dbSeeChanges` Düzenlemekte olduğunuz veri başka bir kullanıcı değişiyorsa, bir çalışma zamanı hatası oluşturur.

> [!NOTE]
>  Koşulları için bir açıklama "tutarsız" ve "tutarlı," DAO Yardımı'nda "yöntemi Çalıştır" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Bu şekilde yürütme için kullanılan Querydef nesneleri aşağıdaki sorgu türlerinden birini temsil edebilir:

- Eylem sorguları

- Doğrudan SQL sorguları

`Execute` select sorgusu gibi bir kayıt döndüren sorgular için çalışmaz. `Execute` Toplu işlem sorguları için aşağıdaki gibi yaygın olarak kullanılan **güncelleştirme**, **Ekle**, veya **SELECT INTO**, ya da veri tanım dili (DDL) işlemleri.

> [!TIP]
>  ODBC veri kaynakları ile çalışmak için tercih edilen yol için bir Microsoft Jet tablo eklemektir (. MDB) veritabanı. Daha fazla bilgi için "Erişim dış veritabanları ile DAO'da" DAO Yardım konusuna bakın.

Çağrı [GetRecordsAffected](#getrecordsaffected) üye işlevinin en son tarafından etkilenen kayıtların sayısını belirlemek için QueryDefs `Execute` çağırın. Örneğin, `GetRecordsAffected` silindi, güncelleştirilen veya bir eylem sorgu yürütülürken eklenen kayıtlar sayısı hakkında bilgi döndürür. Bu sayı, döndürülen cascade güncelleştirir veya sildiğinde ilişkili tablolardaki değişiklikleri yürürlükte olan yansıtmaz.

Her ikisi de dahil ederseniz `dbInconsistent` ve `dbConsistent` veya hiçbiri eklerseniz, varsayılan sonucudur `dbInconsistent`.

`Execute` bir kayıt kümesi döndürmüyor. Kullanarak `Execute` kayıtları seçen bir sorgu üzerinde MFC özel durum türü neden [CDaoException](../../mfc/reference/cdaoexception-class.md).

##  <a name="getconnect"></a>  CDaoQueryDef::GetConnect

Querydef ait veri kaynağı ile ilişkili bağlantı dizesini almak için bu üye işlevini çağırın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) querydef bağlantı dizesini içeren.

### <a name="remarks"></a>Açıklamalar

Bu işlev, yalnızca ODBC veri kaynakları ve belirli ISAM sürücüleri ile kullanılır. Microsoft Jet ile kullanılmaz (. MDB) veritabanları; Bu durumda, `GetConnect` boş bir dize döndürür. Daha fazla bilgi için [SetConnect](#setconnect).

> [!TIP]
>  Bunları eklemek için ODBC tabloları ile çalışmak için tercih edilen yol olduğundan bir. MDB Veritabanı. Daha fazla bilgi için "Erişim dış veritabanları ile DAO'da" DAO Yardım konusuna bakın.

Bağlantı dizeleri hakkında daha fazla bilgi için DAO Yardımı'nda "özelliği Bağlan" konusuna bakın.

##  <a name="getdatecreated"></a>  CDaoQueryDef::GetDateCreated

QueryDefs oluşturulduğu tarihi almak için bu üye işlevini çağırın.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) querydef oluşturulduğu saat ve tarihi içeren nesne.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

##  <a name="getdatelastupdated"></a>  CDaoQueryDef::GetDateLastUpdated

QueryDefs tarih almak için bu üye işlevi son güncelleştirildi çağrı — zaman özelliklerinden birini değiştirildi, adını, kendi SQL dizesi ya da kendi bağlantı dizesi gibi.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) querydef son güncelleştirme saati ve tarihi içeren nesne.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

##  <a name="getfieldcount"></a>  CDaoQueryDef::GetFieldCount

Sorgu alanları sayısını almak için bu üye işlevini çağırın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Sorguda tanımlanan alanların sayısı.

### <a name="remarks"></a>Açıklamalar

`GetFieldCount` Tüm alanlarda querydef döngü için kullanışlıdır. Bu amaçla kullanabileceğiniz `GetFieldCount` birlikte [GetFieldInfo](#getfieldinfo).

##  <a name="getfieldinfo"></a>  CDaoQueryDef::GetFieldInfo

Çeşitli querydef içinde tanımlı bir alan hakkında bilgi edinmek için bu üye işlevini çağırın.

```
void GetFieldInfo(
    int nIndex,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetFieldInfo(
    LPCTSTR lpszName,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
İstenen dizine göre arama için querydef ait alanlar koleksiyonu alanında sıfır tabanlı dizini.

*FieldInfo*<br/>
Bir başvuru bir `CDaoFieldInfo` nesnesini istenen bilgileri döndürür.

*dwInfoOptions*<br/>
Hangi bilgilerin alınacağı alan hakkında belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların döndüren işlev neden yanı sıra aşağıda listelenmiştir:

- (Varsayılan) AFX_DAO_PRIMARY_INFO adı, türü, boyut öznitelikleri

- Artı AFX_DAO_SECONDARY_INFO birincil bilgileri: gerekli sıra konumu, sıfır uzunluk izni, kaynak alan, yabancı adı, kaynak tablosunda, harmanlama sırası

- AFX_DAO_ALL_INFO birincil ve ikincil bilgi artı: varsayılan değer, doğrulama metin doğrulama kuralı

*lpszName*<br/>
Ada göre arama için istenen alanın adını içeren bir dize. Kullanabileceğiniz bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

Döndürülen bilgilerin açıklamasını *FieldInfo*, bkz: [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Açıklayıcı bilgileri altında karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions* yukarıda. Bir düzey bilgilerin istenmişse bilgilerini de önceki tüm düzeylerini alın.

##  <a name="getname"></a>  CDaoQueryDef::GetName

Querydef tarafından temsil edilen bir sorgu adını almak için bu üye işlevini çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Sorgu adı.

### <a name="remarks"></a>Açıklamalar

Kullanıcı tanımlı benzersiz adlar QueryDef adlarıdır. Querydef adları hakkında daha fazla bilgi için "Name özelliği" DAO Yardım konusuna bakın.

##  <a name="getodbctimeout"></a>  CDaoQueryDef::GetODBCTimeout

ODBC veri kaynağı için bir sorgu zaman aşımına uğramadan önce geçerli süre almak için bu üye işlevini çağırın.

```
short GetODBCTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Saniye cinsinden sorgu önce zaman aşımına uğradı.

### <a name="remarks"></a>Açıklamalar

Bu süre hakkında daha fazla bilgi için DAO Yardımı'nda "ODBCTimeout özelliği" konusuna bakın.

> [!TIP]
>  ODBC tabloları ile çalışmak için tercih edilen yol için bir Microsoft Jet eklenecek olan (. MDB) veritabanı. Daha fazla bilgi için "Erişim dış veritabanları ile DAO'da" DAO Yardım konusuna bakın.

##  <a name="getparametercount"></a>  CDaoQueryDef::GetParameterCount

Kaydedilen sorgu parametrelerinde sayısını almak için bu üye işlevini çağırın.

```
short GetParameterCount();
```

### <a name="return-value"></a>Dönüş Değeri

Sorguda tanımlanan parametrelerin sayısı.

### <a name="remarks"></a>Açıklamalar

`GetParameterCount` tüm parametreleri querydef döngü için kullanışlıdır. Bu amaçla kullanabileceğiniz `GetParameterCount` birlikte [Getparameterınfo](#getparameterinfo).

İlgili bilgiler için "Parametresi nesne", "Parametre koleksiyonunu" ve "parametre bildirimi (SQL)" DAO Yardımı'ndaki konulara bakın.

##  <a name="getparameterinfo"></a>  CDaoQueryDef::GetParameterInfo

Querydef içinde tanımlanmış bir parametre hakkında bilgi edinmek için bu üye işlevini çağırın.

```
void GetParameterInfo(
    int nIndex,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetParameterInfo(
    LPCTSTR lpszName,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dizine göre arama için querydef ait parametre koleksiyonunu istenen parametreyi sıfır tabanlı dizini.

*paramınfo*<br/>
Bir başvuru bir [Cdaoparameterınfo](../../mfc/reference/cdaoparameterinfo-structure.md) nesnesini istenen bilgileri döndürür.

*dwInfoOptions*<br/>
Alınacak parametresi ile ilgili bilgileri belirtmenize seçenekleri. Seçenek ne döndürmek işlev neden yanı sıra burada listelenir:

- (Varsayılan) AFX_DAO_PRIMARY_INFO adı, türü

*lpszName*<br/>
Ada göre arama için istenen parametre adını içeren bir dize. Kullanabileceğiniz bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

Döndürülen bilgilerin açıklamasını *paramınfo*, bkz: [Cdaoparameterınfo](../../mfc/reference/cdaoparameterinfo-structure.md) yapısı. Açıklayıcı bilgileri altında karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions* yukarıda.

İlgili bilgiler için "PARAMETRELER bildirimi (SQL)" DAO Yardım konusuna bakın.

##  <a name="getparamvalue"></a>  CDaoQueryDef::GetParamValue

Belirtilen parametre querydef's parametreleri koleksiyonu içinde depolandığında geçerli değerini almak için bu üye işlevini çağırın.

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Değer için ada göre arama, istediğiniz parametrenin adı.

*nIndex*<br/>
Dizine göre arama için querydef ait parametre koleksiyonuna parametre sıfır tabanlı dizini. Bu değer çağrılarıyla elde edebilirsiniz [GetParameterCount](#getparametercount) ve [Getparameterınfo](#getparameterinfo).

### <a name="return-value"></a>Dönüş Değeri

Sınıfın bir nesnesi [COleVariant](../../mfc/reference/colevariant-class.md) içeren parametrenin değeri.

### <a name="remarks"></a>Açıklamalar

Parametre adını veya koleksiyon içindeki sıralı konumu erişebilirsiniz.

İlgili bilgiler için "PARAMETRELER bildirimi (SQL)" DAO Yardım konusuna bakın.

##  <a name="getrecordsaffected"></a>  CDaoQueryDef::GetRecordsAffected

Kaç tane kaydın son çağrı tarafından etkilendiğini belirlemek için bu üye işlevini çağırın [yürütme](#execute).

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Dönüş Değeri

Etkilenen kayıtların sayısı.

### <a name="remarks"></a>Açıklamalar

Bu sayı, döndürülen cascade güncelleştirir veya sildiğinde ilişkili tablolardaki değişiklikleri yürürlükte olan yansıtmaz.

İlgili bilgiler için DAO Yardımı'nda "RecordsAffected özelliği" konusuna bakın.

##  <a name="getreturnsrecords"></a>  CDaoQueryDef::GetReturnsRecords

Querydef kayıtlar döndüren bir sorguyu temel alan olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıtları döndürür querydef bir sorguyu temel alan olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca doğrudan SQL sorguları için kullanılır. SQL sorguları hakkında daha fazla bilgi için bkz. [yürütme](#execute) üye işlevi. Doğrudan SQL sorguları ile çalışma hakkında daha fazla bilgi için bkz. [SetReturnsRecords](#setreturnsrecords) üye işlevi.

İlgili bilgiler için DAO Yardımı'nda "ReturnsRecords özelliğini" konusuna bakın.

##  <a name="getsql"></a>  CDaoQueryDef::GetSQL

Querydef temel alır bir sorguyu tanımlayan SQL deyimini almak için bu üye işlevini çağırın.

```
CString GetSQL();
```

### <a name="return-value"></a>Dönüş Değeri

SQL deyimini querydef dayandığı sorgu tanımlar.

### <a name="remarks"></a>Açıklamalar

Dize anahtar sözcükler, tablo adları ve benzeri için büyük olasılıkla ayrıştırma.

İlgili bilgiler için "SQL özellik", "Karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL" ve "Sorgulama bir veritabanı ile SQL, kodu" DAO Yardımı'ndaki konulara bakın.

##  <a name="gettype"></a>  CDaoQueryDef::GetType

Querydef sorgu türünü belirlemek için bu üye işlevini çağırın.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef tarafından tanımlanan sorgu türü. Değerler için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

Sorgu türü querydef oluşturduğunuzda veya var olan bir querydef's çağrısı ne querydef'ın SQL dizesi içinde belirttiğiniz tarafından ayarlanmış [SetSQL](#setsql) üye işlevi. Bu işlev tarafından döndürülen sorgu türü aşağıdaki değerlerden biri olabilir:

- `dbQSelect` Seçin

- `dbQAction` Eylem

- `dbQCrosstab` Çapraz

- `dbQDelete` DELETE

- `dbQUpdate` Güncelleştirme

- `dbQAppend` Ekleme

- `dbQMakeTable` Tablo oluşturma

- `dbQDDL` Veri tanımı

- `dbQSQLPassThrough` geçiş

- `dbQSetOperation` birleşim

- `dbQSPTBulk` İle kullanılan `dbQSQLPassThrough` kayıtları döndürmeyen bir sorgu belirtmek için.

> [!NOTE]
>  SQL doğrudan sorgu oluşturmak için ayarlamamanız `dbSQLPassThrough` sabit. QueryDefs oluştururken ve bağlantı dizesini ayarlayalım bu Microsoft Jet veritabanı altyapısı tarafından otomatik olarak ayarlanır.

SQL dizeleri hakkında daha fazla bilgi için bkz. [GetSQL](#getsql). Sorgu türleri hakkında daha fazla bilgi için bkz. [yürütme](#execute).

##  <a name="isopen"></a>  CDaoQueryDef::IsOpen

Belirlemek için bu üye işlevi çağrısı olup olmadığını `CDaoQueryDef` nesne şu anda açık değil.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `CDaoQueryDef` nesnedir açık; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırmak için kullanmadan önce bir querydef açık durumda olmalıdır [yürütme](#execute) veya oluşturmak için bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesne. Bir querydef ya da bir açık duruma çağrı yerleştirmek için [Oluştur](#create) (için yeni bir querydef) veya [açın](#open) (için mevcut bir querydef).

##  <a name="m_pdatabase"></a>  CDaoQueryDef::m_pDatabase

Bir işaretçi içeren [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) querydef nesnesiyle ilişkili nesne.

### <a name="remarks"></a>Açıklamalar

Veritabanına doğrudan erişim gerekiyorsa, bu işaretçi kullanın; örneğin, diğer querydef ya da kayıt işaretçileri almak için nesneleri veritabanının koleksiyonlarında.

##  <a name="m_pdaoquerydef"></a>  CDaoQueryDef::m_pDAOQueryDef

DAO querydef nesnesini OLE arabirimi için bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

This işaretçisi, bütünlük ve diğer sınıflar ile tutarlılık sağlanır. MFC DAO querydefs yerine tam olarak kapsülleyen olduğundan, ancak, ihtiyaç duyduğunuz düşüktür. Kullanıyorsanız, bunu dikkatli biçimde yapın — ne yaptığınızı bilmiyorsanız işaretçinin değerini özellikle değiştirmeyin.

##  <a name="open"></a>  CDaoQueryDef::Open

Veritabanının QueryDefs koleksiyonu daha önce kaydettiğiniz bir querydef açmak için bu üye işlevini çağırın.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Açmak için kaydedilen querydef adını içeren bir dize. Kullanabileceğiniz bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

Querydef açıldıktan sonra çağırabilirsiniz kendi [yürütme](#execute) üye işlevini veya kullanım querydef oluşturmak için bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesne.

##  <a name="setconnect"></a>  CDaoQueryDef::SetConnect

Querydef nesnenin bağlantı dizesini ayarlamak için bu üye işlevini çağırın.

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Parametreler

*lpszConnect*<br/>
İlişkili bir bağlantı dizesi içeren bir dize [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Bağlantı dizesi, ODBC ve gerektiğinde belirli ISAM sürücüleri için ek bilgiler iletmek için kullanılır. Microsoft Jet için kullanılmayan (. MDB) veritabanları.

> [!TIP]
>  Bunları eklemek için ODBC tabloları ile çalışmak için tercih edilen yol olduğundan bir. MDB Veritabanı.

SQL doğrudan sorgu için ODBC veri kaynağını temsil eden bir querydef yürütmeden önce ile bağlantı dizesini ayarlayalım `SetConnect` ve çağrı [SetReturnsRecords](#setreturnsrecords) sorgu kayıt döndürüp döndürmediğini belirtmek için.

Bağlantı dizesinin yapısı ve bağlantı dizesini bileşenlerinin örnekleri hakkında daha fazla bilgi için DAO Yardımı'nda "özelliği Bağlan" konusuna bakın.

##  <a name="setname"></a>  CDaoQueryDef::SetName

Geçici olmayan bir querydef adını değiştirmek istiyorsanız, bu üye işlevini çağırın.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
İlişkili kalıcı bir sorgu için yeni adı içeren bir dize [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

QueryDef adları benzersiz, kullanıcı tanımlı adlarıdır. Çağırabilirsiniz `SetName` querydef önce nesne QueryDefs koleksiyona eklenir.

##  <a name="setodbctimeout"></a>  CDaoQueryDef::SetODBCTimeout

ODBC veri kaynağı için bir sorgu zaman aşımına uğramadan önce zaman sınırını ayarlamak için bu üye işlevini çağırın.

```
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>Parametreler

*nODBCTimeout*<br/>
Saniye cinsinden sorgu önce zaman aşımına uğradı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi bağlı veri kaynağı "zaman aşımına uğradı." sonraki işlemleri önce varsayılan saniyeyi geçersiz kılmanıza olanak tanır. Bir işlem nedeniyle ağ erişim sorunları, aşırı miktarda sorgu işleme süresi ve benzeri zaman. Çağrı `SetODBCTimeout` sorgu zaman aşımı değerini değiştirmek istiyorsanız önce bu querydef içeren bir sorgu yürütme. (ODBC bağlantıları kullanır, zaman aşımı değeri aynı bağlantı üzerinde tüm istemciler için aynıdır.)

Sorgu zaman aşımı için'varsayılan değer 60 saniyedir.

##  <a name="setparamvalue"></a>  CDaoQueryDef::SetParamValue

Bir parametrenin değeri, çalışma zamanında querydef içinde ayarlamak için bu üye işlevini çağırın.

```
virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Değer, ayarlamak istediğiniz parametrenin adı.

*varValue*<br/>
Ayarlanacak değer; Açıklamalara bakın.

*nIndex*<br/>
Parametre querydef ait parametre koleksiyonunda sıralı konumu. Bu değer çağrılarıyla elde edebilirsiniz [GetParameterCount](#getparametercount) ve [Getparameterınfo](#getparameterinfo).

### <a name="remarks"></a>Açıklamalar

Parametre zaten querydef'ın SQL dizesi bir parçası olarak kurulmuş gerekir. Parametre adını veya koleksiyon içindeki sıralı konumu erişebilirsiniz.

Değeri olarak ayarlamak için belirtin bir `COleVariant` nesne. İstenen değeri ve türü ayarlama hakkında bilgi için `COleVariant` nesne, sınıfına bakın [COleVariant](../../mfc/reference/colevariant-class.md).

##  <a name="setreturnsrecords"></a>  CDaoQueryDef::SetReturnsRecords

Harici bir veritabanına doğrudan geçirilen bir SQL sorgu ayarlama işleminin bir parçası olarak bu üye işlevini çağırın.

```
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>Parametreler

*bReturnsRecords*<br/>
Bir dış veritabanında sorgu kayıtları döndürürse TRUE geçirin; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Böyle bir durumda, querydef oluşturmalı ve diğer kullanarak onun özelliklerini ayarlarsınız `CDaoQueryDef` üye işlevleri. Dış veritabanlarını açıklaması için bkz: [SetConnect](#setconnect).

##  <a name="setsql"></a>  CDaoQueryDef::SetSQL

Querydef yürütür SQL deyimi ayarlamak için bu üye işlevini çağırın.

```
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Parametreler

*lpszSQL*<br/>
Bir tam SQL deyimi yürütme için uygun içeren bir dize. Bu dize söz dizimi üzerinde DBMS bağlıdır, sorgu hedeflerinizi. Microsoft Jet veritabanı altyapısı, kullanılan söz dizimi ile ilgili tartışma için "Yapı SQL deyimleri içinde kodu" DAO Yardım konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Tipik bir kullanımı, `SetSQL` QueryDefs kullanılmak üzere bir SQL sorgusunu doğrudan yukarı ayardır. (Doğrudan SQL sorguları, hedefte DBMS sözdizimi, DBMS belgelerine bakın.)

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
