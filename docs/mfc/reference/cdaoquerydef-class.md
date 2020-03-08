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
ms.openlocfilehash: 08fb2909a4fd2e5bda3dfc63d19224a515c7c699
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883895"
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef sınıfı

Genellikle bir veritabanına kaydedilmiş bir sorgu tanımını veya "QueryDef" öğesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoQueryDef:: CDaoQueryDef](#cdaoquerydef)|`CDaoQueryDef` nesnesi oluşturur. Gereksinimlerinize bağlı olarak bir sonraki `Open` veya `Create`çağırın.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoQueryDef:: Append](#append)|QueryDef ' i veritabanının QueryDefs koleksiyonuna kayıtlı bir sorgu olarak ekler.|
|[CDaoQueryDef:: CanUpdate](#canupdate)|Sorgu veritabanını güncelleştirebiliyorsanız sıfır dışında bir değer döndürür.|
|[CDaoQueryDef:: Close](#close)|QueryDef nesnesini kapatır. İle bitirdiğinizde C++ nesneyi yok edin.|
|[CDaoQueryDef:: Create](#create)|Temel alınan DAO QueryDef nesnesini oluşturur. QueryDef 'i geçici bir sorgu olarak kullanın veya veritabanına kaydetmek için `Append` çağırın.|
|[CDaoQueryDef:: Execute](#execute)|QueryDef nesnesi tarafından tanımlanan sorguyu yürütür.|
|[CDaoQueryDef:: GetConnect](#getconnect)|QueryDef ile ilişkili bağlantı dizesini döndürür. Bağlantı dizesi, veri kaynağını tanımlar. (Yalnızca SQL geçişli sorgular için; Aksi takdirde boş bir dize.)|
|[CDaoQueryDef:: GetDateCreated](#getdatecreated)|Kaydedilen sorgunun oluşturulduğu tarihi döndürür.|
|[CDaoQueryDef:: GetDateLastUpdated](#getdatelastupdated)|Kaydedilen sorgunun son güncelleştirilme tarihini döndürür.|
|[CDaoQueryDef:: GetFieldCount](#getfieldcount)|QueryDef tarafından tanımlanan alan sayısını döndürür.|
|[CDaoQueryDef:: GetFieldInfo](#getfieldinfo)|Sorguda tanımlanan belirli bir alan hakkında bilgi döndürür.|
|[CDaoQueryDef:: GetName](#getname)|QueryDef adını döndürür.|
|[CDaoQueryDef:: GetODBCTimeout](#getodbctimeout)|QueryDef yürütüldüğünde ODBC tarafından kullanılan zaman aşımı değerini döndürür (bir ODBC sorgusu için). Bu, sorgunun eyleminin tamamlanmasına ne kadar süreyle izin verileceğini belirler.|
|[CDaoQueryDef:: GetParameterCount](#getparametercount)|Sorgu için tanımlanan parametrelerin sayısını döndürür.|
|[CDaoQueryDef:: GetParameterInfo](#getparameterinfo)|Sorguya belirtilen bir parametre hakkında bilgi döndürür.|
|[CDaoQueryDef:: GetParamValue](#getparamvalue)|Sorguya belirtilen parametrenin değerini döndürür.|
|[CDaoQueryDef:: Getrecordsabetkilenen](#getrecordsaffected)|Bir eylem sorgusundan etkilenen kayıt sayısını döndürür.|
|[CDaoQueryDef:: GetReturnsRecords](#getreturnsrecords)|QueryDef tarafından tanımlanan sorgu kayıtları döndürürse, sıfır dışında bir değer döndürür.|
|[CDaoQueryDef:: GetSQL](#getsql)|QueryDef tarafından tanımlanan sorguyu belirten SQL dizesini döndürür.|
|[CDaoQueryDef:: GetType](#gettype)|Sorgu türünü döndürür: delete, Update, Append, Make-table vb.|
|[CDaoQueryDef:: IsOpen](#isopen)|QueryDef açıksa ve yürütülürse sıfır olmayan bir değer döndürür.|
|[CDaoQueryDef:: Open](#open)|Veritabanının QueryDefs koleksiyonunda depolanan mevcut bir QueryDef öğesini açar.|
|[CDaoQueryDef:: SetConnect](#setconnect)|ODBC veri kaynağındaki bir SQL geçişli sorgu için bağlantı dizesini ayarlar.|
|[CDaoQueryDef:: SetName](#setname)|QueryDef oluşturulduğu sırada kullanılan adı değiştirerek kaydedilen sorgunun adını ayarlar.|
|[CDaoQueryDef:: SetODBCTimeout](#setodbctimeout)|QueryDef yürütüldüğünde ODBC tarafından kullanılan zaman aşımı değerini ayarlar (ODBC sorgusu için).|
|[CDaoQueryDef:: SetParamValue](#setparamvalue)|Sorgu için belirtilen parametrenin değerini ayarlar.|
|[CDaoQueryDef:: SetReturnsRecords](#setreturnsrecords)|QueryDef 'in kayıtları döndürüp döndürmeyeceğini belirtir. Bu özniteliğin TRUE olarak ayarlanması yalnızca SQL geçiş sorguları için geçerlidir.|
|[CDaoQueryDef:: SetSQL](#setsql)|QueryDef tarafından tanımlanan sorguyu belirten SQL dizesini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoQueryDef:: m_pDAOQueryDef](#m_pdaoquerydef)|Temel alınan DAO QueryDef nesnesi için OLE arabirimine yönelik bir işaretçi.|
|[CDaoQueryDef:: m_pDatabase](#m_pdatabase)|QueryDef 'in ilişkilendirildiği `CDaoDatabase` nesnesine yönelik bir işaretçi. QueryDef veritabanına kaydedilebilir veya değil.|

## <a name="remarks"></a>Açıklamalar

QueryDef, bir sorguyu açıklayan SQL ifadesini ve "Tarih oluşturma" ve "ODBC zaman aşımı" gibi özellikleri içeren bir veri erişim nesnesidir. Ayrıca, bir veritabanında yaygın olarak kullanılan sorguları kaydetmek için, daha kolay ve çok daha verimli bir şekilde, bu nesneleri kaydetmeden geçici QueryDef nesneleri de oluşturabilirsiniz. Bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi, kayıtlı QueryDefs öğesini Içeren QueryDefs koleksiyonu adlı bir koleksiyonu tutar.

> [!NOTE]
>  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adlarında "CDao" öneki vardır. ODBC veri kaynaklarına, DAO sınıflarıyla erişmeye devam edebilirsiniz. Genel olarak, DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıflarından daha sahiptir; DAO tabanlı sınıflar, ODBC sürücüleri dahil olmak üzere verilere kendi veritabanı altyapıları aracılığıyla erişebilir. DAO tabanlı sınıflar, DAO 'YU doğrudan çağırmak zorunda kalmadan, sınıflar aracılığıyla tablo ekleme gibi veri tanımlama dili (DDL) işlemlerini de destekler.

## <a name="usage"></a>Kullanım

Varolan kayıtlı bir sorgu ile çalışmak veya kaydedilmiş yeni bir sorgu ya da geçici sorgu oluşturmak için, QueryDef nesneleri kullanın:

1. Her durumda, ilk olarak sorgunun ait olduğu [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine bir işaretçi sağlayan bir `CDaoQueryDef` nesnesi oluşturun.

1. Ardından, istediğiniz seçeneğe bağlı olarak aşağıdakileri yapın:

   - Varolan bir kayıtlı sorguyu kullanmak için, kayıtlı sorgunun adını sağlayarak querydef nesnesinin [Open](#open) üye işlevini çağırın.

   - Yeni bir kaydedilmiş sorgu oluşturmak için, sorgu adı sağlayarak querydef nesnesinin üye [Oluştur](#create) işlevini çağırın. Sonra veritabanını veritabanının QueryDefs koleksiyonuna ekleyerek sorguyu kaydetmek için [append](#append) çağrısı yapın. `Create`, QueryDef 'i açık duruma geçirir, bu nedenle `Create` çağrıldıktan sonra `Open`çağırmayın.

   - Geçici bir QueryDef oluşturmak için `Create`çağırın. Sorgu adı için boş bir dize geçirin. `Append`çağırmayın.

Bir QueryDef nesnesi kullanmayı bitirdiğinizde, [Close](#close) üye işlevini çağırın; ardından QueryDef nesnesini yok edin.

> [!TIP]
>  Kayıtlı sorguları oluşturmanın en kolay yolu, bunları oluşturmak ve Microsoft Access 'i kullanarak veritabanınızda depolamalardır. Bu durumda, MFC kodunuzda açabilir ve kullanabilirsiniz.

## <a name="purposes"></a>Çalışmaları

Aşağıdaki amaçlardan herhangi biri için bir QueryDef nesnesi kullanabilirsiniz:

- `CDaoRecordset` nesnesi oluşturmak için

- Bir eylem sorgusunu veya bir SQL geçişli sorguyu doğrudan yürütmek üzere nesnenin `Execute` üye işlevini çağırmak için

Seçme, eylem, çapraz, silme, güncelleştirme, ekleme, oluşturma-tablo, veri tanımı, SQL geçişli, birleşim ve toplu sorgular dahil olmak üzere herhangi bir tür sorgu için bir QueryDef nesnesi kullanabilirsiniz. Sorgunun türü, sağladığınız SQL ifadesinin içeriğine göre belirlenir. Sorgu türleri hakkında daha fazla bilgi için bkz. `Execute` ve [GetType](#gettype) üye işlevleri. Kayıt kümeleri genellikle Select... öğesini kullanan satır döndüren sorgular için kullanılır **. Anahtar sözcüklerden** . `Execute` en yaygın olarak toplu işlemler için kullanılır. Daha fazla bilgi için bkz. [Execute](#execute) and [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

## <a name="querydefs-and-recordsets"></a>QueryDefs ve kayıt kümeleri

Bir `CDaoRecordset` nesnesi oluşturmak için bir QueryDef nesnesi kullanmak için, genellikle yukarıda açıklanan şekilde bir QueryDef oluşturun veya açarsınız. Ardından, [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)' ı çağırdığınızda QueryDef nesneniz için bir işaretçi geçirerek bir kayıt kümesi nesnesi oluşturun. Geçirdiğiniz querydef açık durumda olmalıdır. Daha fazla bilgi için bkz. Class [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Açık durumda olmadığı müddetçe bir kayıt kümesi (bir QueryDef için en yaygın kullanım) oluşturmak için bir QueryDef kullanamazsınız. `Open` veya `Create`çağırarak QueryDef 'i açık duruma getirin.

## <a name="external-databases"></a>Dış veritabanları

QueryDef nesneleri, dış veritabanı altyapısının yerel SQL lehçini kullanmanın tercih edilen yoludur. Örneğin, bir Transact SQL sorgusu (Microsoft SQL Server için kullanılan) oluşturabilir ve bunu bir QueryDef nesnesinde saklayabilirsiniz. Microsoft Jet veritabanı altyapısını temel alan bir SQL sorgusu kullanmanız gerektiğinde, dış veri kaynağına işaret eden bir bağlantı dizesi sağlamalısınız. Geçerli bağlantı dizelerine sahip sorgular veritabanı altyapısını atlar ve işleme için sorguyu doğrudan dış veritabanı sunucusuna iletir.

> [!TIP]
>  ODBC tabloları ile çalışmanın tercih edilen yolu, bunları bir Microsoft Jet 'e eklemektir (. MDB) veritabanı.

İlgili bilgiler için, DAO SDK 'sında "QueryDef Object", "QueryDefs Collection" ve "CdbDatabase Object" konularına bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

##  <a name="append"></a>CDaoQueryDef:: Append

Yeni bir QueryDef nesnesi oluşturmak için [Oluştur](#create) ' a çağrı yaptıktan sonra bu üye işlevini çağırın.

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

`Append`, nesneyi veritabanının QueryDefs koleksiyonuna ekleyerek querydef ' i veritabanına kaydeder. QueryDef ' i, eklemeden geçici bir nesne olarak kullanabilirsiniz, ancak devam etmek istiyorsanız, `Append`çağırmanız gerekir.

Geçici bir QueryDef nesnesi eklemeye çalışırsanız, MFC, [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturur.

##  <a name="canupdate"></a>CDaoQueryDef:: CanUpdate

QueryDef ' i değiştirip değiştiremeyeceğinizi (örneğin, adını veya SQL dizesini değiştirme) öğrenmek için bu üye işlevini çağırın.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

QueryDef ' i değiştirmenize izin verirseniz sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Şu durumlarda QueryDef 'i değiştirebilirsiniz:

- Salt okunurdur açık olan bir veritabanını temel değildir.

- Veritabanı için Güncelleştirme izinleriniz var.

   Bu, güvenlik özellikleri uygulamış olmanıza bağlı olarak değişir. MFC güvenlik için destek sağlamaz; doğrudan DAO 'YU çağırarak veya Microsoft Access 'i kullanarak kendiniz uygulamanız gerekir. DAO yardımı 'nda "Izinler özelliği" konusuna bakın.

##  <a name="cdaoquerydef"></a>CDaoQueryDef:: CDaoQueryDef

`CDaoQueryDef` nesnesi oluşturur.

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Açık bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesnesi, veritabanının QueryDefs koleksiyonunda depolanan mevcut bir QueryDef ' i, koleksiyonda depolanacak yeni bir sorgu ya da depolanmayacak geçici bir sorgu temsil edebilir. Sonraki adımınız, QueryDef türüne bağlıdır:

- Nesne varolan bir QueryDef öğesini temsil ediyorsa, uygulamayı başlatmak için nesnenin [Açık](#open) üye işlevini çağırın.

- Nesne, kaydedilecek yeni bir QueryDef öğesini temsil ediyorsa, nesnenin üye [Oluştur](#create) işlevini çağırın. Bu, nesneyi veritabanının QueryDefs koleksiyonuna ekler. Sonra nesne özniteliklerini ayarlamak için `CDaoQueryDef` üye işlevlerini çağırın. Son olarak, [append](#append)çağrısı yapın.

- Nesne geçici bir QueryDef ' i (veritabanına kaydedilmez) temsil ediyorsa, sorgunun adı için boş bir dize geçirerek `Create`çağırın. `Create`çağrıldıktan sonra, özniteliklerini doğrudan ayarlayarak querydef ' i başlatın. `Append`çağırmayın.

QueryDef özniteliklerini ayarlamak için, [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout)ve [SetReturnsRecords](#setreturnsrecords) üye işlevlerini kullanabilirsiniz.

QueryDef nesnesiyle bitirdiğinizde, [Close](#close) üye işlevini çağırın. QueryDef işaretçisine sahipseniz, C++ nesneyi yok etmek için **Delete** işlecini kullanın.

##  <a name="close"></a>CDaoQueryDef:: Close

QueryDef nesnesini kullanmayı bitirdiğinizde bu üye işlevini çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

QueryDef ' in kapatılması temeldeki DAO nesnesini yayınlar, ancak kaydedilen DAO QueryDef nesnesini veya C++ `CDaoQueryDef` nesnesini yok etmez. Bu, CDaoDatabase ile aynı değildir [::D eleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef). Bu, QueryDef ' i, DAO 'daki (geçici bir QueryDef değilse) veritabanının QueryDefs koleksiyonundan siler.

##  <a name="create"></a>CDaoQueryDef:: Create

Yeni bir kaydedilmiş sorgu veya yeni bir geçici sorgu oluşturmak için bu üye işlevini çağırın.

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Veritabanına kaydedilen sorgunun benzersiz adı. Dize hakkındaki ayrıntılar için, DAO yardımı 'nda "CreateQueryDef Yöntemi" konusuna bakın. Boş bir dize olan varsayılan değeri kabul ediyorsanız geçici bir QueryDef oluşturulur. Bu tür bir sorgu QueryDefs koleksiyonuna kaydedilmez.

*lpszSQL*<br/>
Sorguyu tanımlayan SQL dizesi. NULL varsayılan değerini kabul ediyorsanız, daha sonra dizeyi ayarlamak için [SetSQL](#setsql) ' i çağırmanız gerekir. Bundan sonra sorgu tanımsızdır. Ancak, tanımsız sorgu kullanarak bir kayıt kümesi açabilirsiniz; Ayrıntılar için bkz. açıklamalar. QueryDef ' i QueryDefs koleksiyonuna ekleyebilmeniz için önce SQL ifadesinin tanımlanması gerekir.

### <a name="remarks"></a>Açıklamalar

*LpszName*' e bir ad geçirirseniz, daha sonra querydef ' i [çağırıp veritabanının](#append) QueryDefs koleksiyonuna kaydedebilirsiniz. Aksi halde, nesne geçici bir QueryDef ' dir ve kaydedilmez. Her iki durumda da, querydef açık durumdadır ve bunu kullanarak bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturabilir veya QueryDef 'in [Execute](#execute) üye işlevini çağırabilirsiniz.

*LpszSQL*'de bir SQL ifadesini belirtmezseniz, sorguyu `Execute` ile çalıştıramazsınız, ancak bir kayıt kümesi oluşturmak için kullanabilirsiniz. Bu durumda, MFC kayıt kümesinin varsayılan SQL ifadesini kullanır.

##  <a name="execute"></a>CDaoQueryDef:: Execute

QueryDef nesnesi tarafından tanımlanan sorguyu çalıştırmak için bu üye işlevini çağırın.

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Parametreler

*Önemli seçenekler*<br/>
Sorgunun özelliklerini belirleyen bir tamsayı. İlgili bilgiler için, DAO yardımı 'nda "yöntemi yürütme" konusuna bakın. Bu bağımsız değişken için aşağıdaki sabitleri birleştirmek için bit **&#124;** düzeyinde OR işleci () kullanabilirsiniz:

- diğer kullanıcılara yazma iznini reddetme `dbDenyWrite`.

- Tutarsız güncelleştirmeler `dbInconsistent`.

- Tutarlı güncelleştirmeler `dbConsistent`.

- SQL geçişli `dbSQLPassThrough`. SQL ifadesinin işlenmek üzere bir ODBC veritabanına geçirilmesine neden olur.

- `dbFailOnError` varsayılan değer. Bir hata oluşursa güncelleştirmeleri geri alın ve hatayı kullanıcıya bildirin.

- `dbSeeChanges` başka bir Kullanıcı düzenlemekte olduğunuz verileri değiştirirken bir çalışma zamanı hatası oluşturur.

> [!NOTE]
>  "Tutarsız" ve "tutarlı" terimleri hakkında bir açıklama için, DAO yardımı 'nda "Yöntem yürütme" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Bu şekilde yürütme için kullanılan QueryDef nesneleri yalnızca aşağıdaki sorgu türlerinden birini temsil edebilir:

- Eylem sorguları

- SQL geçişli sorgular

`Execute`, sorguları Seç gibi kayıtlar döndüren sorgular için çalışmaz. `Execute`, genellikle **güncelleştirme**, **ekleme**veya **seçme**veya veri tanımlama dili (ddl) işlemleri gibi toplu işlem sorguları için kullanılır.

> [!TIP]
>  ODBC veri kaynaklarıyla çalışmak için tercih edilen yöntem, tabloları Microsoft Jet 'e eklemektir (. MDB) veritabanı. Daha fazla bilgi için, DAO yardımı 'nda "DAO ile dış veritabanlarına erişme" konusuna bakın.

En son `Execute` çağrısından etkilenen kayıt sayısını öğrenmek için, QueryDef nesnesinin [Getrecordsaetkilenmember](#getrecordsaffected) işlevini çağırın. Örneğin `GetRecordsAffected`, bir eylem sorgusu yürütürken silinen, güncellenen veya yerleştirilen kayıt sayısı hakkında bilgi döndürür. Döndürülen sayı, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

Hem `dbInconsistent` hem de `dbConsistent` dahil ederseniz veya hiçbir ikisini de eklerseniz, sonuç varsayılan olarak `dbInconsistent`.

`Execute` bir kayıt kümesi döndürmez. Kayıtları seçen bir sorgu üzerinde `Execute` kullanmak MFC 'nin [CDaoException](../../mfc/reference/cdaoexception-class.md)türünde bir özel durum oluşturmasına neden olur.

##  <a name="getconnect"></a>CDaoQueryDef:: GetConnect

QueryDef 'in veri kaynağıyla ilişkili bağlantı dizesini almak için bu üye işlevi çağırın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

QueryDef için bağlantı dizesini içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca ODBC veri kaynakları ve belirli ISAM sürücüleri ile kullanılır. Microsoft Jet (. MDB) veritabanları; Bu durumda `GetConnect` boş bir dize döndürür. Daha fazla bilgi için bkz. [SetConnect](#setconnect).

> [!TIP]
>  ODBC tabloları ile çalışmanın tercih edilen yolu, bunları bir öğesine eklemektir. MDB veritabanı. Daha fazla bilgi için, DAO yardımı 'nda "DAO ile dış veritabanlarına erişme" konusuna bakın.

Bağlantı dizeleri hakkında daha fazla bilgi için, DAO yardımı 'nda "bağlama özelliği" konusuna bakın.

##  <a name="getdatecreated"></a>CDaoQueryDef:: GetDateCreated

QueryDef nesnesinin oluşturulduğu tarihi almak için bu üye işlevini çağırın.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

QueryDef 'in oluşturulduğu tarih ve saati içeren bir [Cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

##  <a name="getdatelastupdated"></a>CDaoQueryDef:: GetDateLastUpdated

QueryDef nesnesinin son güncelleştirildiği tarihi (örneğin adı, SQL dizesi veya bağlantı dizesi) değiştirildiği zaman almak için bu üye işlevini çağırın.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

QueryDef 'in son güncelleştirildiği tarih ve saati içeren bir [Cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

##  <a name="getfieldcount"></a>CDaoQueryDef:: GetFieldCount

Sorgudaki alan sayısını almak için bu üye işlevi çağırın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Sorguda tanımlanan alan sayısı.

### <a name="remarks"></a>Açıklamalar

`GetFieldCount`, QueryDef 'teki tüm alanlarla döngü için yararlıdır. Bu amaçla, [GetFieldInfo](#getfieldinfo)ile birlikte `GetFieldCount` kullanın.

##  <a name="getfieldinfo"></a>CDaoQueryDef:: GetFieldInfo

QueryDef ' de tanımlanan bir alanla ilgili çeşitli bilgi türlerini almak için bu üye işlevini çağırın.

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

*nDizin*<br/>
Dizine göre arama için, QueryDef 'in Fields koleksiyonundaki istenen alanın sıfır tabanlı dizini.

*sağlanırken*<br/>
İstenen bilgileri döndüren `CDaoFieldInfo` nesnesine bir başvuru.

*dwInfoOptions*<br/>
Alınacak alanla ilgili hangi bilgilerin alındığını belirleyen seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte aşağıda listelenmiştir:

- AFX_DAO_PRIMARY_INFO (varsayılan) ad, tür, boyut, öznitelik

- Birincil bilgileri ve AFX_DAO_SECONDARY_INFO: sıralı konum, gerekli, sıfır uzunluğa Izin ver, kaynak alanı, yabancı ad, kaynak tablosu, harmanlama sırası

- Birincil ve ikincil bilgileri AFX_DAO_ALL_INFO Plus: varsayılan değer, doğrulama metni, doğrulama kuralı

*lpszName*<br/>
Ada göre arama için istenen alanın adını içeren bir dize. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)kullanabilirsiniz.

### <a name="remarks"></a>Açıklamalar

*FieldInfo*'da döndürülen bilgilerin açıklaması için bkz. [Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bu yapının, yukarıdaki *Dwinfooptions* altında açıklayıcı bilgilere karşılık gelen üyeleri vardır. Bir düzey bilgi istemeniz durumunda daha önceki bilgi seviyeleri de alırsınız.

##  <a name="getname"></a>CDaoQueryDef:: GetName

QueryDef tarafından temsil edilen sorgunun adını almak için bu üye işlevini çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Sorgunun adı.

### <a name="remarks"></a>Açıklamalar

QueryDef adları, Kullanıcı tanımlı benzersiz adlardır. QueryDef adları hakkında daha fazla bilgi için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

##  <a name="getodbctimeout"></a>CDaoQueryDef:: GetODBCTimeout

ODBC veri kaynağı sorgusunun zaman aşımına uğramadan önce geçerli zaman sınırını almak için bu üye işlevini çağırın.

```
short GetODBCTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Sorgunun zaman aşımına uğramadan önce geçmesi gereken saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu süre sınırı hakkında daha fazla bilgi için, DAO yardımı 'nda "ODBCTimeout Özelliği" konusuna bakın.

> [!TIP]
>  ODBC tabloları ile çalışmanın tercih edilen yolu, bunları bir Microsoft Jet 'e eklemektir (. MDB) veritabanı. Daha fazla bilgi için, DAO yardımı 'nda "DAO ile dış veritabanlarına erişme" konusuna bakın.

##  <a name="getparametercount"></a>CDaoQueryDef:: GetParameterCount

Kaydedilen sorgudaki parametre sayısını almak için bu üye işlevi çağırın.

```
short GetParameterCount();
```

### <a name="return-value"></a>Dönüş Değeri

Sorguda tanımlanan parametrelerin sayısı.

### <a name="remarks"></a>Açıklamalar

`GetParameterCount`, QueryDef 'teki tüm parametreler aracılığıyla döngü için yararlıdır. Bu amaçla, [GetParameterInfo](#getparameterinfo)ile birlikte `GetParameterCount` kullanın.

İlgili bilgiler için, DAO yardımı 'nda "parametre nesnesi", "parametreler koleksiyonu" ve "PARAMETERS bildirimi (SQL)" konularına bakın.

##  <a name="getparameterinfo"></a>CDaoQueryDef:: GetParameterInfo

QueryDef 'te tanımlanan bir parametre hakkında bilgi edinmek için bu üye işlevini çağırın.

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

*nDizin*<br/>
Dizine göre arama için, QueryDef 'in Parameters koleksiyonunda istenen parametrenin sıfır tabanlı dizini.

*paraınfo*<br/>
İstenen bilgileri döndüren bir [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Alınacak parametre hakkındaki bilgileri belirten seçenekler. Kullanılabilir seçenek, işlevin döndürmesine neden olan ile birlikte aşağıda listelenmiştir:

- AFX_DAO_PRIMARY_INFO (varsayılan) ad, tür

*lpszName*<br/>
Ada göre arama için istenen parametrenin adını içeren bir dize. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)kullanabilirsiniz.

### <a name="remarks"></a>Açıklamalar

*Paraınfo*'da döndürülen bilgilerin açıklaması için bkz. [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) yapısı. Bu yapının, yukarıdaki *Dwinfooptions* altında açıklayıcı bilgilere karşılık gelen üyeleri vardır.

İlgili bilgiler için, DAO yardımı 'nda "PARAMETERS bildirimi (SQL)" konusuna bakın.

##  <a name="getparamvalue"></a>CDaoQueryDef:: GetParamValue

QueryDef 'in Parameters koleksiyonunda depolanan belirtilen parametrenin geçerli değerini almak için bu üye işlevi çağırın.

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Adına göre arama için, değerini istediğiniz parametresinin adı.

*nDizin*<br/>
Dizine göre arama için, QueryDef 'in Parameters koleksiyonundaki parametrenin sıfır tabanlı dizini. Bu değeri [GetParameterCount](#getparametercount) ve [GetParameterInfo](#getparameterinfo)çağrıları ile elde edebilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Parametrenin değerini içeren [Cotavariant](../../mfc/reference/colevariant-class.md) sınıfının bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Parametreye ada veya koleksiyondaki sıra konumuna göre erişebilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "PARAMETERS bildirimi (SQL)" konusuna bakın.

##  <a name="getrecordsaffected"></a>CDaoQueryDef:: Getrecordsabetkilenen

Son [yürütme](#execute)çağrısından kaç tane kaydın etkilendiğini öğrenmek için bu üye işlevi çağırın.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Dönüş Değeri

Etkilenen kayıt sayısı.

### <a name="remarks"></a>Açıklamalar

Döndürülen sayı, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

İlgili bilgiler için, DAO yardımı 'nda "Recordsabetkilenen özellik" konusuna bakın.

##  <a name="getreturnsrecords"></a>CDaoQueryDef:: GetReturnsRecords

QueryDef 'in kayıtları döndüren bir sorguyu temel alarak kullanıp kullanmadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>Dönüş Değeri

QueryDef, kayıtları döndüren bir sorguyu temel alıyorsa sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca SQL geçiş sorguları için kullanılır. SQL sorguları hakkında daha fazla bilgi için bkz. [Execute](#execute) member işlevi. SQL geçişli sorgularla çalışma hakkında daha fazla bilgi için bkz. [SetReturnsRecords](#setreturnsrecords) üye işlevi.

İlgili bilgiler için, DAO yardımı 'nda "ReturnsRecords özelliği" konusuna bakın.

##  <a name="getsql"></a>CDaoQueryDef:: GetSQL

QueryDef 'in temel aldığı sorguyu tanımlayan SQL ifadesini almak için bu üye işlevi çağırın.

```
CString GetSQL();
```

### <a name="return-value"></a>Dönüş Değeri

QueryDef 'in temel aldığı sorguyu tanımlayan SQL deyimidir.

### <a name="remarks"></a>Açıklamalar

Daha sonra muhtemelen anahtar sözcükler, tablo adları vb. için dizeyi ayrıştırmaya devam edersiniz.

İlgili bilgiler için, DAO yardımı 'nda "SQL özelliği", "Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL karşılaştırması" ve "kod içinde SQL ile veritabanı sorgulama" konularına bakın.

##  <a name="gettype"></a>CDaoQueryDef:: GetType

QueryDef sorgu türünü öğrenmek için bu üye işlevini çağırın.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

QueryDef tarafından tanımlanan sorgunun türü. Değerler için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Sorgu türü, QueryDef ' i oluştururken veya var olan bir QueryDef [SetSQL](#setsql) üye işlevini çağırdığınızda, QUERYDEF 'in SQL dizesinde belirtdikleriniz tarafından ayarlanır. Bu işlev tarafından döndürülen sorgu türü aşağıdaki değerlerden biri olabilir:

- `dbQSelect` seçme

- `dbQAction` eylemi

- `dbQCrosstab` çapraz

- `dbQDelete` silme

- `dbQUpdate` güncelleştirme

- `dbQAppend` Ekle

- `dbQMakeTable` tablosu oluşturma

- `dbQDDL` veri tanımı

- `dbQSQLPassThrough` geçişli

- `dbQSetOperation` UNION

- `dbQSPTBulk`, kayıt döndürmeyen bir sorgu belirtmek için `dbQSQLPassThrough` ile birlikte kullanılır.

> [!NOTE]
>  Bir SQL geçişli sorgu oluşturmak için `dbSQLPassThrough` sabiti ayarlayın. Bu, bir QueryDef nesnesi oluşturup bağlantı dizesini ayarladığınızda Microsoft Jet veritabanı altyapısı tarafından otomatik olarak ayarlanır.

SQL dizeleri hakkında daha fazla bilgi için bkz. [GetSQL](#getsql). Sorgu türleri hakkında daha fazla bilgi için bkz. [Execute](#execute).

##  <a name="isopen"></a>CDaoQueryDef:: IsOpen

`CDaoQueryDef` nesnesinin açık olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoQueryDef` nesnesi şu anda açıksa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir QueryDef, [Execute](#execute) veya bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturmak için kullanılmadan önce açık durumda olmalıdır. Bir QueryDef öğesini açık durum çağrısına eklemek [için (yeni](#create) bir QueryDef için) veya [açın](#open) (varolan bir QueryDef için).

##  <a name="m_pdatabase"></a>CDaoQueryDef:: m_pDatabase

QueryDef nesnesiyle ilişkili [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Veritabanına doğrudan erişmeniz gerekiyorsa (örneğin, veritabanının koleksiyonlarındaki diğer querydef veya Recordset nesnelerine işaretçiler almak için) Bu işaretçiyi kullanın.

##  <a name="m_pdaoquerydef"></a>CDaoQueryDef:: m_pDAOQueryDef

Temel alınan DAO QueryDef nesnesi için OLE arabirimine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi, diğer sınıflarla bütünlüğü ve tutarlılık için sağlanır. Bununla birlikte, MFC DAO QueryDefs 'i tam olarak sarmalamadığı için ihtiyacınız düşüktür. Bu işlemi kullanırsanız, bu işlemi özellikle, ne yaptığınızı bilmiyorsanız işaretçinin değerini değiştirmeyin...

##  <a name="open"></a>CDaoQueryDef:: Open

Daha önce veritabanının QueryDefs koleksiyonunda kayıtlı bir QueryDef açmak için bu üye işlevini çağırın.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Açılacak kaydedilmiş QueryDef adını içeren bir dize. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)kullanabilirsiniz.

### <a name="remarks"></a>Açıklamalar

QueryDef açıldıktan sonra [Execute](#execute) üye işlevini çağırabilir veya bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturmak için querydef ' i kullanabilirsiniz.

##  <a name="setconnect"></a>CDaoQueryDef:: SetConnect

QueryDef nesnesinin bağlantı dizesini ayarlamak için bu üye işlevini çağırın.

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Parametreler

*lpszConnect*<br/>
İlişkili [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi için bağlantı dizesi içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Bağlantı dizesi, gereken şekilde ODBC ve belirli ISAM sürücülerine ek bilgi geçirmek için kullanılır. Microsoft Jet için kullanılmaz (. MDB) veritabanları.

> [!TIP]
>  ODBC tabloları ile çalışmanın tercih edilen yolu, bunları bir öğesine eklemektir. MDB veritabanı.

ODBC veri kaynağına yönelik bir SQL geçişli sorguyu temsil eden bir QueryDef yürütmeden önce, bağlantı dizesini `SetConnect` olarak ayarlayın ve sorgunun kayıt döndürüp döndürmeyeceğini belirtmek için [SetReturnsRecords](#setreturnsrecords) çağırın.

Bağlantı dizesinin yapısı ve bağlantı dizesi bileşenlerinin örnekleri hakkında daha fazla bilgi için, DAO yardımı 'nda "bağlama özelliği" konusuna bakın.

##  <a name="setname"></a>CDaoQueryDef:: SetName

Geçici olmayan bir QueryDef adını değiştirmek istiyorsanız bu üye işlevini çağırın.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
İlişkili [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesinde geçici olmayan bir sorgu için yeni adı içeren bir dize.

### <a name="remarks"></a>Açıklamalar

QueryDef adları benzersiz, Kullanıcı tanımlı adlardır. QueryDef nesnesi QueryDefs koleksiyonuna eklenmeden önce `SetName` çağırabilirsiniz.

##  <a name="setodbctimeout"></a>CDaoQueryDef:: SetODBCTimeout

ODBC veri kaynağı sorgusunun zaman aşımına uğramadan önce zaman sınırını ayarlamak için bu üye işlevini çağırın.

```
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>Parametreler

*nODBCTimeout*<br/>
Sorgunun zaman aşımına uğramadan önce geçmesi gereken saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bağlı veri kaynağındaki "sonraki işlemler" zaman aşımına girmeden önce varsayılan saniye sayısını geçersiz kılmanızı sağlar. Ağ erişimi sorunları, aşırı sorgu işleme süresi vb. nedeniyle bir işlem zaman aşımına uğrar. Sorgu zaman aşımı değerini değiştirmek istiyorsanız, bu QueryDef ile bir sorgu yürütmeden önce `SetODBCTimeout` çağırın. (ODBC bağlantıları yeniden kullanır olarak zaman aşımı değeri aynı bağlantıdaki tüm istemciler için aynıdır.)

Sorgu zaman aşımları için varsayılan değer 60 saniyedir.

##  <a name="setparamvalue"></a>CDaoQueryDef:: SetParamValue

Çalışma zamanında QueryDef içindeki bir parametrenin değerini ayarlamak için bu üye işlevini çağırın.

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
Değerini ayarlamak istediğiniz parametrenin adı.

*varValue*<br/>
Ayarlanacak değer; bkz. açıklamalar.

*nDizin*<br/>
QueryDef 'in Parameters koleksiyonundaki parametresinin sıra konumu. Bu değeri [GetParameterCount](#getparametercount) ve [GetParameterInfo](#getparameterinfo)çağrıları ile elde edebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Parametrenin, zaten querydef 'in SQL dizesinin bir parçası olarak oluşturulmuş olması gerekir. Parametreye ada veya koleksiyondaki sıra konumuna göre erişebilirsiniz.

`COleVariant` nesne olarak ayarlanacak değeri belirtin. `COleVariant` nesneniz için istenen değeri ve türü ayarlama hakkında daha fazla bilgi için bkz. sınıf [Cotavariant](../../mfc/reference/colevariant-class.md).

##  <a name="setreturnsrecords"></a>CDaoQueryDef:: SetReturnsRecords

Dış veritabanına SQL geçişli sorgu ayarlama işleminin bir parçası olarak bu üye işlevi çağırın.

```
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>Parametreler

*bReturnsRecords*<br/>
Dış veritabanındaki sorgu kayıtları döndürürse, doğru geçirin; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Böyle bir durumda, QueryDef ' i oluşturmanız ve diğer `CDaoQueryDef` üye işlevlerini kullanarak özelliklerini ayarlamanız gerekir. Dış veritabanlarının açıklaması için bkz. [SetConnect](#setconnect).

##  <a name="setsql"></a>CDaoQueryDef:: SetSQL

QueryDef 'in çalıştırdığı SQL ifadesini ayarlamak için bu üye işlevini çağırın.

```
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Parametreler

*lpszSQL*<br/>
Yürütme için uygun olan, tamamlanmış bir SQL ifadesini içeren bir dize. Bu dizenin sözdizimi, sorgunuzun hedeflediği DBMS 'ye bağlıdır. Microsoft Jet veritabanı altyapısında kullanılan söz dizimi ile ilgili bir tartışma için, DAO yardımı 'nda "kodda SQL deyimleri oluşturma" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

`SetSQL` tipik kullanımı, bir SQL geçişli sorgusunda kullanılmak üzere bir QueryDef nesnesi ayarlamadır. (Hedef DBMS 'nizin SQL geçişli sorgularının sözdizimi için, DBMS 'nize yönelik belgelere bakın.)

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
