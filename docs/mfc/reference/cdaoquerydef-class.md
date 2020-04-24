---
title: CDaoQueryDef Sınıfı
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
ms.openlocfilehash: ed298c40daa9485683d0b989e47b97fdce9f6562
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754706"
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef Sınıfı

Genellikle bir veritabanına kaydedilmiş bir sorgu tanımı veya "querydef"i temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Bir `CDaoQueryDef` nesne inşa eder. Bir `Open` sonraki `Create`arama ya da, ihtiyaçlarınıza bağlı olarak.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoQueryDef::Ek](#append)|Kaydedilen bir sorgu olarak veritabanının QueryDefs koleksiyonuna querydef ekler.|
|[CDaoQueryDef::CanUpdate](#canupdate)|Sorgu veritabanını güncelleştirebiliyorsa sıfırsız döndürür.|
|[CDaoQueryDef::Kapat](#close)|Querydef nesnesini kapatır. Onunla bitirdiğinizde C++ nesnesini yok edin.|
|[CDaoQueryDef::Oluştur](#create)|Altta yatan DAO querydef nesnesini oluşturur. Querydef'i geçici bir sorgu `Append` olarak kullanın veya veritabanına kaydetmek için arayın.|
|[CDaoQueryDef::Yürüt](#execute)|Querydef nesnesi tarafından tanımlanan sorguyu yürütür.|
|[CDaoQueryDef::GetConnect](#getconnect)|Querydef ile ilişkili bağlantı dizesini döndürür. Bağlantı dizesi veri kaynağını tanımlar. (Yalnızca SQL geçiş sorguları için; aksi takdirde boş bir dize.)|
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Kaydedilen sorgunun oluşturulduğu tarihi döndürür.|
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Kaydedilen sorgunun en son güncelleştirilen tarihi döndürür.|
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Querydef tarafından tanımlanan alan sayısını döndürür.|
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Sorguda tanımlanan belirli bir alanla ilgili bilgileri verir.|
|[CDaoQueryDef::GetName](#getname)|Querydef adını döndürür.|
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|Querydef yürütüldüğünde ODBC tarafından kullanılan zaman aşım değerini (ODBC sorgusu için) döndürür. Bu, sorgueyleminin tamamlanmasına ne kadar süre yle izin verilebildiğini belirler.|
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Sorgu için tanımlanan parametre sayısını verir.|
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Belirtilen bir parametre hakkındaki bilgileri sorguya verir.|
|[CDaoQueryDef::GetParamValue](#getparamvalue)|Sorguya belirtilen bir parametrenin değerini verir.|
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Eylem sorgusundan etkilenen kayıt sayısını döndürür.|
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Querydef tarafından tanımlanan sorgu kayıtları döndürürse sıfırsız döndürür.|
|[CDaoQueryDef::GetSQL](#getsql)|Querydef tarafından tanımlanan sorguyu belirten SQL dizesini döndürür.|
|[CDaoQueryDef::GetType](#gettype)|Sorgu türünü döndürür: silme, güncelleme, ekleme, tablo yapma ve benzeri.|
|[CDaoQueryDef::Açık](#isopen)|Querydef açıksa ve yürütülebilirse sıfırsız döndürür.|
|[CDaoQueryDef::Aç](#open)|Veritabanının QueryDefs koleksiyonunda depolanan varolan bir querydef'i açar.|
|[CDaoQueryDef::SetConnect](#setconnect)|ODBC veri kaynağında bir SQL geçiş sorgusu için bağlantı dizesini ayarlar.|
|[CDaoQueryDef::SetName](#setname)|Querydef oluşturulduğunda kullanılan adı değiştirerek kaydedilen sorgunun adını ayarlar.|
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|Querydef yürütüldüğünde ODBC (ODBC sorgusu için) tarafından kullanılan zaman aşım değerini ayarlar.|
|[CDaoQueryDef::SetParamValue](#setparamvalue)|Sorguiçin belirtilen bir parametrenin değerini ayarlar.|
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Querydef'in kayıtları döndürüp döndürmeyeceğini belirtir. Bu özniteliği TRUE olarak ayarlamak yalnızca SQL geçiş sorguları için geçerlidir.|
|[CDaoQueryDef::SetSQL](#setsql)|Querydef tarafından tanımlanan sorguyu belirten SQL dizesini ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|Altta yatan DAO querydef nesnesi için OLE arabirimine bir işaretçi.|
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Querydef'in `CDaoDatabase` ilişkili olduğu nesneye işaretçi. Querydef veritabanına kaydedilebilir veya kaydedilmemiş olabilir.|

## <a name="remarks"></a>Açıklamalar

Querydef, sorguyu açıklayan SQL deyimini ve "Oluşturulan Tarih" ve "ODBC Zaman Aş" gibi özelliklerini içeren bir veri erişim nesnesidir. Ayrıca, bunları kaydetmeden geçici querydef nesneleri oluşturabilirsiniz, ancak bir veritabanında sık kullanılan sorguları kaydetmek için kullanışlı - ve çok daha verimli -. [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi, kaydedilmiş querydefs'ini içeren QueryDefs koleksiyonu adlı bir koleksiyon tutar.

> [!NOTE]
> DAO veritabanı sınıfları Açık Veritabanı Bağlantısı (ODBC) dayalı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" öneki vardır. DAO sınıfları ile ODBC veri kaynaklarına erişebilirsiniz. Genel olarak, DAO'ya dayalı MFC sınıfları ODBC'ye dayalı MFC sınıfları kadar yeteneklidir; DAO tabanlı sınıflar, ODBC sürücüleri aracılığıyla da dahil olmak üzere verilere kendi veritabanı altyapıları aracılığıyla erişebilir. DAO tabanlı sınıflar, doğrudan DAO'yu aramak zorunda kalmadan sınıflar üzerinden tablo eklemek gibi Veri Tanım Dili (DDL) işlemlerini de destekler.

## <a name="usage"></a>Kullanım

Varolan bir kayıtlı sorguyla çalışmak veya yeni bir kayıtlı sorgu veya geçici sorgu oluşturmak için querydef nesnelerini kullanın:

1. Her durumda, önce `CDaoQueryDef` sorgunun ait olduğu [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine bir işaretçi sağlayan bir nesne oluştur.

1. Sonra ne istediğinize bağlı olarak, aşağıdakileri yapın:

   - Varolan kaydedilmiş bir sorguyu kullanmak için, kaydedilen sorgunun adını sağlayan querydef nesnesinin [Açık](#open) üye işlevini çağırın.

   - Yeni bir kayıtlı sorgu oluşturmak için query's [Create](#create) üye işlevini arayarak sorgunun adını belirtin. Ardından, sorguyu veritabanının QueryDefs koleksiyonuna ekleyerek sorguyu kaydetmek için [Append'i](#append) arayın. `Create`querydef'i açık bir duruma getirir, bu nedenle aradıktan `Create` sonra aramazsınız. `Open`

   - Geçici bir querydef oluşturmak `Create`için . Sorgu adı için boş bir dize geçirin. Arama. `Append`

Bir querydef nesnesi kullanmayı bitirdiğinizde, [Yakın](#close) üye işlevini arayın; sonra querydef nesnesini yok edin.

> [!TIP]
> Kaydedilen sorguları oluşturmanın en kolay yolu, bunları oluşturmak ve Microsoft Access'i kullanarak veritabanınızda depolamaktır. Ardından bunları MFC kodunuzda açıp kullanabilirsiniz.

## <a name="purposes"></a>Amaçlı

Aşağıdaki amaçlardan herhangi biri için bir querydef nesnesi kullanabilirsiniz:

- `CDaoRecordset` Nesne oluşturmak için

- Doğrudan bir eylem `Execute` sorgusu veya SQL geçiş sorgusu yürütmek için nesnenin üye işlevini çağırmak için

Select, action, crosstab, delete, update, append, make-table, data definition, SQL pass-through, union ve toplu sorgular dahil olmak üzere herhangi bir sorgu türü için bir querydef nesnesi kullanabilirsiniz. Sorgunun türü, sağladığınız SQL deyiminin içeriğine göre belirlenir. Sorgu türleri hakkında bilgi `Execute` için [gettype](#gettype) üye işlevlerine bakın. Recordsets genellikle satır döndüren sorgular için kullanılır, genellikle SELECT ... ** FROM** anahtar kelimeleri. `Execute`en sık toplu işlemler için kullanılır. Daha fazla bilgi için [Execute](#execute) ve [CDaoRecordset'e](../../mfc/reference/cdaorecordset-class.md)bakın.

## <a name="querydefs-and-recordsets"></a>Querydefs ve Recordsets

Bir nesne oluşturmak için bir `CDaoRecordset` querydef nesnesi kullanmak için, genellikle yukarıda açıklandığı gibi bir querydef oluşturur veya açarsınız. Sonra [cdaoRecordset::Aç](../../mfc/reference/cdaorecordset-class.md#open)çağırdığınızda querydef nesnenize bir işaretçi geçerek bir recordset nesnesi oluşturmak. Geçtiğiniz querydef açık durumda olmalıdır. Daha fazla bilgi için [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)sınıfına bakın.

Açık bir durumda olmadığı sürece bir kayıt kümesi (bir querydef için en yaygın kullanım) oluşturmak için bir querydef kullanamazsınız. Querydef'i ya da `Open` ' yı `Create`arayarak açık bir duruma getirin.

## <a name="external-databases"></a>Dış Veritabanları

Querydef nesneleri, harici bir veritabanı altyapısının yerel SQL lehçesini kullanmanın tercih edilen yoludur. Örneğin, bir Transact SQL sorgusu oluşturabilir (Microsoft SQL Server'da kullanıldığı gibi) ve sorgunesnesinde depolayabilirsiniz. Microsoft Jet veritabanı altyapısına dayanmayan bir SQL sorgusu kullanmanız gerektiğinde, dış veri kaynağını işaret eden bir bağlantı dizesi sağlamanız gerekir. Geçerli bağlantı dizeleri olan sorgular veritabanı altyapısını atlar ve sorguyu doğrudan işleme için dış veritabanı sunucusuna geçirir.

> [!TIP]
> ODBC tabloları ile çalışmak için tercih edilen yolu bir Microsoft Jet (. MDB) veritabanı.

İlgili bilgiler için DAO SDK'daki "QueryDef Object", "QueryDefs Collection" ve "CdbDatabase Object" konularına bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="cdaoquerydefappend"></a><a name="append"></a>CDaoQueryDef::Ek

Yeni bir querydef nesnesi oluşturmak için [Oluştur'u](#create) aradıktan sonra bu üye işlevi arayın.

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

`Append`nesneyi veritabanının QueryDefs koleksiyonuna ekleyerek querydef'i veritabanına kaydeder. Querydef'i eklemeden geçici bir nesne olarak kullanabilirsiniz, ancak devam etmesini `Append`istiyorsanız, ' ı aramanız gerekir.

Geçici bir querydef nesnesi eklemeye çalışırsanız, MFC [CDaoException](../../mfc/reference/cdaoexception-class.md)türünden bir özel durum atar.

## <a name="cdaoquerydefcanupdate"></a><a name="canupdate"></a>CDaoQueryDef::CanUpdate

Querydef'i değiştirip değiştiremeyeceğinibelirlemek için bu üye işlevini çağırın ( örneğin, adını veya SQL dizesini değiştirin.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef'i değiştirmenize izin vereneyseniz sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Aşağıdakileri varsa querydef'i değiştirebilirsiniz:

- Salt okunur açık bir veritabanını temel almıyor.

- Veritabanı için güncelleştirme izinleri var.

   Bu, güvenlik özelliklerini uygulayıp uygulamadığınıza bağlıdır. MFC güvenlik desteği sağlamaz; doğrudan DAO'ya araarak veya Microsoft Access'i kullanarak kendiniz uygulamanız gerekir. DAO Yardım'da "İzinler Özelliği" konusuna bakın.

## <a name="cdaoquerydefcdaoquerydef"></a><a name="cdaoquerydef"></a>CDaoQueryDef::CDaoQueryDef

Bir `CDaoQueryDef` nesne inşa eder.

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Açık bir [CDaoDatabase nesnesine](../../mfc/reference/cdaodatabase-class.md) işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesne, veritabanının QueryDefs koleksiyonunda depolanan varolan bir querydef'i, koleksiyonda depolanacak yeni bir sorguyu veya depolanmaması gereken geçici bir sorguyu temsil edebilir. Bir sonraki adımquerydef türüne bağlıdır:

- Nesne varolan bir querydef'i temsil ediyorsa, onu başlatması için nesnenin [Açık](#open) üye işlevini çağırın.

- Nesne kaydedilecek yeni bir querydef'i temsil ediyorsa, nesnenin [Oluştur](#create) üye işlevini arayın. Bu, nesneyi veritabanının QueryDefs koleksiyonuna ekler. Ardından `CDaoQueryDef` nesnenin özniteliklerini ayarlamak için üye işlevleri arayın. Son olarak, [Append'i](#append)arayın.

- Nesne geçici bir querydef 'i temsil ediyorsa `Create`(veritabanına kaydedilmez), sorgunun adı için boş bir dize geçirerek arayın. Aradıktan `Create`sonra, doğrudan özniteliklerini ayarlayarak querydef'i başharfe ada. Arama. `Append`

Querydef özniteliklerini ayarlamak için [SetName,](#setname) [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout)ve [SetReturnsRecords](#setreturnsrecords) üye işlevlerini kullanabilirsiniz.

Querydef nesnesi ile bitirdiğinizde, [Yakın](#close) üye işlevini arayın. Querydef için bir işaretçinvarsa, C++ nesnesini yok etmek için **delete** işlecikullanını kullanın.

## <a name="cdaoquerydefclose"></a><a name="close"></a>CDaoQueryDef::Kapat

Querydef nesnesini kullanmayı bitirdiğinizde bu üye işlevi arayın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Querydef'in kapatılması, alttaki DAO nesnesini serbest bırakır, ancak kaydedilen `CDaoQueryDef` DAO querydef nesnesini veya C++ nesnesini yok etmez. Bu [CDaoDatabase aynı değildir::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), DAO veritabanının QueryDefs koleksiyonundan querydef siler (geçici bir querydef değilse).

## <a name="cdaoquerydefcreate"></a><a name="create"></a>CDaoQueryDef::Oluştur

Yeni bir kayıtlı sorgu veya yeni bir geçici sorgu oluşturmak için bu üye işlevini çağırın.

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Veritabanına kaydedilen sorgunun benzersiz adı. Dize hakkında ayrıntılı bilgi için DAO Help'deki "CreateQueryDef Method" konusuna bakın. Varsayılan değeri, boş bir dize kabul ederseniz, geçici bir querydef oluşturulur. Böyle bir sorgu QueryDefs koleksiyonuna kaydedilmez.

*Lpszsql*<br/>
Sorguyu tanımlayan SQL dizesi. NULL'un varsayılan değerini kabul ederseniz, daha sonra dizeyi ayarlamak için [SetSQL'i](#setsql) aramanız gerekir. O zamana kadar, sorgu tanımsız. Ancak, bir kayıt kümesini açmak için tanımlanmamış sorguyu kullanabilirsiniz; ayrıntılar için Açıklamalar'a bakın. QueryDefs koleksiyonuna querydef'i eklemeden önce SQL deyimi tanımlanmalıdır.

### <a name="remarks"></a>Açıklamalar

*LpszName'de*bir ad geçerseniz, veritabanının QueryDefs koleksiyonunda querydef'i kaydetmek için [Append'i](#append) arayabilirsiniz. Aksi takdirde, nesne geçici bir querydef ve kaydedilmez. Her iki durumda da, querydef açık durumda dır ve [cdaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturmak veya querydef'in [Yürüt](#execute) üye işlevini aramak için kullanabilirsiniz.

*LPSZSQL'de*bir SQL deyimi sağlamazsanız, sorguyu `Execute` çalıştıramazsınız, ancak bir kayıt kümesi oluşturmak için kullanabilirsiniz. Bu durumda, MFC kayıt kümesinin varsayılan SQL deyimini kullanır.

## <a name="cdaoquerydefexecute"></a><a name="execute"></a>CDaoQueryDef::Yürüt

Querydef nesnesi tarafından tanımlanan sorguyu çalıştırmak için bu üye işlevi arayın.

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Parametreler

*nSeçenekler*<br/>
Sorgunun özelliklerini belirleyen bir sonsayı. İlgili bilgiler için DAO Yardım'daki "Yürütme Yöntemi" konusuna bakın. Bu bağımsız değişken için aşağıdaki sabitleri birleştirmek için bitwise-OR işleci **(&#124;) **kullanabilirsiniz:

- `dbDenyWrite`Diğer kullanıcılara yazma izni verme.

- `dbInconsistent`Tutarsız güncelleştirmeler.

- `dbConsistent`Tutarlı güncellemeler.

- `dbSQLPassThrough`SQL geçiş. SQL deyiminin işlenmek üzere ODBC veritabanına geçirilmesine neden olur.

- `dbFailOnError`Varsayılan değer. Bir hata oluşursa güncelleştirmeleri geri alave ve hatayı kullanıcıya bildirin.

- `dbSeeChanges`Başka bir kullanıcı düzenlediğiniz verileri değiştiriyorsa çalışma zamanı hatası oluşturun.

> [!NOTE]
> "Tutarsız" ve "tutarlı" terimlerinin açıklaması için DAO Help'deki "Yürütme Yöntemi" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Bu şekilde yürütme için kullanılan querydef nesneleri yalnızca aşağıdaki sorgu türlerinden birini temsil edebilir:

- Eylem sorguları

- SQL geçiş sorguları

`Execute`belirli sorgular gibi kayıtları döndüren sorgular için çalışmaz. `Execute`**UPDATE,** **INSERT**veya **SELECT INTO**gibi toplu işlem sorguları veya veri tanım dili (DDL) işlemleri için kullanılır.

> [!TIP]
> ODBC veri kaynaklarıyla çalışmanın tercih edilen yolu, tabloları bir Microsoft Jet'e eklemektir (. MDB) veritabanı. Daha fazla bilgi için DAO Yardım'da "DAO ile Dış Veritabanlarına Erişim" konusuna bakın.

En son `Execute` çağrıdan etkilenen kayıt sayısını belirlemek için querydef nesnesinin [GetRecordsEtkilenen](#getrecordsaffected) üye işlevini arayın. Örneğin, `GetRecordsAffected` bir eylem sorgusu yürütürürken silinen, güncelleştirilen veya eklenen kayıt sayısıyla ilgili bilgileri döndürür. Döndürülen sayım, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

Her ikisini `dbInconsistent` de `dbConsistent` eklerseniz veya ikisini de eklemezseniz, sonuç varsayılandır. `dbInconsistent`

`Execute`kayıt kümesi döndürmez. Kayıtları `Execute` seçen bir sorguda kullanmak, MFC'nin [CDaoException](../../mfc/reference/cdaoexception-class.md)türünden bir özel durum almasına neden olur.

## <a name="cdaoquerydefgetconnect"></a><a name="getconnect"></a>CDaoQueryDef::GetConnect

Querydef'in veri kaynağıyla ilişkili bağlantı dizesini almak için bu üye işlevini arayın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef için bağlantı dizesini içeren bir [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca ODBC veri kaynakları ve belirli ISAM sürücüleri ile kullanılır. Microsoft Jet (. MDB) veritabanları; bu durumda, `GetConnect` boş bir dize döndürür. Daha fazla bilgi için [SetConnect'e](#setconnect)bakın.

> [!TIP]
> ODBC tabloları ile çalışmak için tercih edilen yolu bir . MDB veritabanı. Daha fazla bilgi için DAO Yardım'da "DAO ile Dış Veritabanlarına Erişim" konusuna bakın.

Bağlantı dizeleri hakkında daha fazla bilgi için DAO Yardım'daki "Özelliği Bağla" konusuna bakın.

## <a name="cdaoquerydefgetdatecreated"></a><a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated

Querydef nesnesinin oluşturulduğu tarihi almak için bu üye işlevini arayın.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef'in oluşturulduğu tarih ve saati içeren bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardım'daki "DateCreated, LastUpdated Properties" konusuna bakın.

## <a name="cdaoquerydefgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoQueryDef::GetDateLastUpdated

Querydef nesnesinin en son güncelleştirilme tarihini almak için bu üye işlevi arayın — adı, SQL dizesi veya bağlantı dizesi gibi özelliklerinden herhangi biri değiştirildiğinde.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef'in en son güncelleştirilen tarih ve saati içeren [bir COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardım'daki "DateCreated, LastUpdated Properties" konusuna bakın.

## <a name="cdaoquerydefgetfieldcount"></a><a name="getfieldcount"></a>CDaoQueryDef::GetFieldCount

Sorgudaki alan sayısını almak için bu üye işlevi arayın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Sorguda tanımlanan alan sayısı.

### <a name="remarks"></a>Açıklamalar

`GetFieldCount`querydef'deki tüm alanlar arasında döngü için yararlıdır. Bu amaçla, `GetFieldCount` [GetFieldInfo](#getfieldinfo)ile birlikte kullanın.

## <a name="cdaoquerydefgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoQueryDef::GetFieldInfo

Querydef'te tanımlanan bir alan hakkında çeşitli bilgiler elde etmek için bu üye işlevini arayın.

```cpp
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

*Nındex*<br/>
Querydef'in Alanlar koleksiyonunda istenen alanın dizin tarafından arama için sıfır tabanlı dizin.

*Fieldınfo*<br/>
İstenilen `CDaoFieldInfo` bilgileri döndüren bir nesneye başvuru.

*dwInfoOptions*<br/>
Alan hakkında hangi bilgilerin alınaaçık olduğunu belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürülmesine neden oldukları yla birlikte burada listelenir:

- AFX_DAO_PRIMARY_INFO (Varsayılan) Adı, Türü, Boyutu, Öznitelikleri

- AFX_DAO_SECONDARY_INFO Birincil bilgi artı: Ordinal Position, Gerekli, İzin Sıfır Uzunluk, Kaynak Alan, Yabancı Ad, Kaynak Tablo, Collating Sipariş

- AFX_DAO_ALL_INFO Birincil ve ikincil bilgi artı: Varsayılan Değer, Doğrulama Metni, Doğrulama Kuralı

*Lpszname*<br/>
Ada göre arama için istenilen alanın adını içeren bir dize. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)kullanabilirsiniz.

### <a name="remarks"></a>Açıklamalar

*Fieldinfo'da*döndürülen bilgilerin açıklaması için [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına bakın. Bu yapı, yukarıdaki *dwInfoOptions* altında açıklayıcı bilgilere karşılık gelen üyeleri vardır. Bir bilgi düzeyi talep ederseniz, önceden de bilgi düzeyi alırsınız.

## <a name="cdaoquerydefgetname"></a><a name="getname"></a>CDaoQueryDef::GetName

Querydef tarafından temsil edilen sorgunun adını almak için bu üye işlevini arayın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Sorgunun adı.

### <a name="remarks"></a>Açıklamalar

Querydef adları benzersiz kullanıcı tanımlı adlardır. Querydef adları hakkında daha fazla bilgi için DAO Help'deki "Ad Özelliği" konusuna bakın.

## <a name="cdaoquerydefgetodbctimeout"></a><a name="getodbctimeout"></a>CDaoQueryDef::GetODBCTimeout

ODBC veri kaynağına bir sorgu dan önce geçerli zaman sınırını almak için bu üye işlevini çağırın.

```
short GetODBCTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sorgudan önceki saniye sayısı zaman ları slenir.

### <a name="remarks"></a>Açıklamalar

Bu zaman sınırı hakkında bilgi için DAO Yardım'daki "ODBCTimeout Özelliği" konusuna bakın.

> [!TIP]
> ODBC tabloları ile çalışmak için tercih edilen yolu bir Microsoft Jet (. MDB) veritabanı. Daha fazla bilgi için DAO Yardım'da "DAO ile Dış Veritabanlarına Erişim" konusuna bakın.

## <a name="cdaoquerydefgetparametercount"></a><a name="getparametercount"></a>CDaoQueryDef::GetParameterCount

Kaydedilen sorgudaki parametre sayısını almak için bu üye işlevini çağırın.

```
short GetParameterCount();
```

### <a name="return-value"></a>Dönüş Değeri

Sorguda tanımlanan parametrelerin sayısı.

### <a name="remarks"></a>Açıklamalar

`GetParameterCount`querydef'deki tüm parametreleri döngüye dahil etmek için yararlıdır. Bu `GetParameterCount` [amaçla, GetParameterInfo](#getparameterinfo)ile birlikte kullanın.

İlgili bilgiler için DAO Help'deki "Parametre Nesnesi", "Parametreler Toplama" ve "PARAMETRELER Bildirimi (SQL)" konularına bakın.

## <a name="cdaoquerydefgetparameterinfo"></a><a name="getparameterinfo"></a>CDaoQueryDef::GetParameterInfo

Querydef'te tanımlanan bir parametre hakkında bilgi almak için bu üye işlevini arayın.

```cpp
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

*Nındex*<br/>
Querydef'in Parametreler koleksiyonunda istenen parametrenin sıfır tabanlı dizin, dizin tarafından arama için.

*paraminfo*<br/>
İstenen bilgileri döndüren [bir CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Parametre hakkında hangi bilgilerin alınamasını belirten seçenekler. Kullanılabilir seçenek, işlevin döndürülmesine neden olan şeyle birlikte burada listelenmiştir:

- AFX_DAO_PRIMARY_INFO (Varsayılan) Adı, Türü

*Lpszname*<br/>
Ada göre arama için istenilen parametrenin adını içeren bir dize. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)kullanabilirsiniz.

### <a name="remarks"></a>Açıklamalar

*Paraminfo*döndürülen bilgilerin açıklaması için [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) yapısına bakın. Bu yapı, yukarıdaki *dwInfoOptions* altında açıklayıcı bilgilere karşılık gelen üyeleri vardır.

İlgili bilgiler için DAO Yardım'daki "PARAMETRELER Bildirimi (SQL)" konusuna bakın.

## <a name="cdaoquerydefgetparamvalue"></a><a name="getparamvalue"></a>CDaoQueryDef::GetParamValue

Querydef'in Parametreler koleksiyonunda depolanan belirtilen parametrenin geçerli değerini almak için bu üye işlevi arayın.

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Ada göre arama yapmak için değerini istediğiniz parametrenin adı.

*Nındex*<br/>
Querydef'in Parametreler koleksiyonundaki parametrenin sıfır tabanlı dizin, dizin tarafından arama için. GetParameterCount ve [GetParameterInfo'ya](#getparameterinfo)yapılan aramalarla bu değeri elde edebilirsiniz. [GetParameterCount](#getparametercount)

### <a name="return-value"></a>Dönüş Değeri

[COleVariant](../../mfc/reference/colevariant-class.md) sınıfının parametre değerini içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Parametreye ada veya koleksiyondaki ordinal konumuna göre erişebilirsiniz.

İlgili bilgiler için DAO Yardım'daki "PARAMETRELER Bildirimi (SQL)" konusuna bakın.

## <a name="cdaoquerydefgetrecordsaffected"></a><a name="getrecordsaffected"></a>CDaoQueryDef::GetRecordsAffected

[Yürüt'ün](#execute)son çağrısından kaç kaydın etkilendiğini belirlemek için bu üye işlevi arayın.

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Dönüş Değeri

Etkilenen kayıt sayısı.

### <a name="remarks"></a>Açıklamalar

Döndürülen sayım, basamaklı güncelleştirmeler veya silmeler etkin olduğunda ilgili tablolardaki değişiklikleri yansıtmaz.

İlgili bilgiler için DAO Yardım'daki "RecordsAffected Property" konusuna bakın.

## <a name="cdaoquerydefgetreturnsrecords"></a><a name="getreturnsrecords"></a>CDaoQueryDef::GetReturnsRecords

Querydef'in kayıtları döndüran bir sorguyu temel alıp almayacağını belirlemek için bu üye işlevini arayın.

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef kayıtları döndüren bir sorguyu temel alırsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev yalnızca SQL geçiş sorguları için kullanılır. SQL sorguları hakkında daha fazla bilgi için [Yürüt](#execute) üye işlevine bakın. SQL geçiş sorgularıyla çalışma hakkında daha fazla bilgi için [SetReturnsRecords](#setreturnsrecords) üye işlevine bakın.

İlgili bilgiler için DAO Yardım'daki "ReturnsRecords Property" konusuna bakın.

## <a name="cdaoquerydefgetsql"></a><a name="getsql"></a>CDaoQueryDef::GetSQL

Querydef'in dayandığı sorguyu tanımlayan SQL deyimini almak için bu üye işlevi arayın.

```
CString GetSQL();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef'in dayandığı sorguyu tanımlayan SQL deyimi.

### <a name="remarks"></a>Açıklamalar

Daha sonra büyük olasılıkla anahtar kelimeler, tablo adları ve benzeri için dize ayrıştırır.

İlgili bilgiler için DAO Help'de "SQL Özelliği", "Microsoft Jet Database Engine SQL ve ANSI SQL karşılaştırması" ve "Code'da SQL ile Veritabanı Sorgulama" konularına bakın.

## <a name="cdaoquerydefgettype"></a><a name="gettype"></a>CDaoQueryDef::GetType

Querydef'in sorgu türünü belirlemek için bu üye işlevini arayın.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

Querydef tarafından tanımlanan sorgu türü. Değerler için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Sorgu türü, querydef'i oluşturduğunuzda veya varolan bir querydef'in [SetSQL](#setsql) üye işlevini çağırdığınızda querydef'in SQL dizesinde belirttiğiniz şekilde ayarlanır. Bu işlevtarafından döndürülen sorgu türü aşağıdaki değerlerden biri olabilir:

- `dbQSelect`Seçin

- `dbQAction`Eylem

- `dbQCrosstab`Çapraz

- `dbQDelete`Silmek

- `dbQUpdate`Güncelleştirme

- `dbQAppend`Ekleme

- `dbQMakeTable`Make-table

- `dbQDDL`Veri tanımı

- `dbQSQLPassThrough`Doğru -dan

- `dbQSetOperation`Birliği

- `dbQSPTBulk`Kayıtları `dbQSQLPassThrough` döndürmeyen bir sorgu belirtmek için kullanılır.

> [!NOTE]
> Bir SQL geçiş sorgusu oluşturmak için sabiti `dbSQLPassThrough` ayarlamayın. Bu, bir querydef nesnesi oluşturduğunuzda ve bağlantı dizesini ayarladığınızda Microsoft Jet veritabanı altyapısı tarafından otomatik olarak ayarlanır.

SQL dizeleri hakkında daha fazla bilgi için [GetSQL'e](#getsql)bakın. Sorgu türleri hakkında bilgi için [yürüt'](#execute)e bakın.

## <a name="cdaoquerydefisopen"></a><a name="isopen"></a>CDaoQueryDef::Açık

Nesnenin `CDaoQueryDef` şu anda açık olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne şu `CDaoQueryDef` anda açıksa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[Yürüt'ü](#execute) aramak veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturmak için kullanmadan önce bir querydef'in açık durumda olması gerekir. Açık durum çağrısına querydef koymak için ya [Oluştur](#create) (yeni bir querydef için) veya [Açık](#open) (varolan bir querydef için).

## <a name="cdaoquerydefm_pdatabase"></a><a name="m_pdatabase"></a>CDaoQueryDef::m_pDatabase

Querydef nesnesi ile ilişkili [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Veritabanına doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın - örneğin, veritabanının koleksiyonlarındaki diğer querydef veya recordset nesnelerine işaretçiler elde etmek için.

## <a name="cdaoquerydefm_pdaoquerydef"></a><a name="m_pdaoquerydef"></a>CDaoQueryDef::m_pDAOQueryDef

Altta yatan DAO querydef nesnesi için OLE arabirimine bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu işaretçi, diğer sınıflarla tamlık ve tutarlılık için sağlanır. Ancak, MFC DAO querydefs'i tam olarak kapsüllediği için, buna ihtiyacınız olması olası değildir. Eğer kullanırsanız, çok dikkatli yapın - özellikle, ne yaptığınızı bilmiyorsanız işaretçinin değerini değiştirmeyin.

## <a name="cdaoquerydefopen"></a><a name="open"></a>CDaoQueryDef::Aç

Veritabanının QueryDefs koleksiyonunda daha önce kaydedilmiş bir querydef'i açmak için bu üye işlevini arayın.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Açılacak kayıtlı querydef'in adını içeren bir dize. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)kullanabilirsiniz.

### <a name="remarks"></a>Açıklamalar

Querydef açıldıktan sonra, [yürüt](#execute) üye işlevini arayabilir veya [cdaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturmak için querydef'i kullanabilirsiniz.

## <a name="cdaoquerydefsetconnect"></a><a name="setconnect"></a>CDaoQueryDef::SetConnect

Querydef nesnesinin bağlantı dizesini ayarlamak için bu üye işlevi arayın.

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Parametreler

*lpszConnect*<br/>
İlişkili [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi için bağlantı dizesi içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Bağlantı dizesi, gerektiğinde ODBC'ye ve bazı ISAM sürücülerine ek bilgi aktarmak için kullanılır. Microsoft Jet (. MDB) veritabanları.

> [!TIP]
> ODBC tabloları ile çalışmak için tercih edilen yolu bir . MDB veritabanı.

Bir ODBC veri kaynağına SQL geçiş sorgusunu temsil eden bir querydef `SetConnect` gerçekleştirmeden önce, sorgunun kayıtları döndürüp döndürmeyeceğini belirtmek için Bağlantı dizesini ayarlayın ve [SetReturnsRecords'u](#setreturnsrecords) arayın.

Bağlantı dizesinin yapısı ve bağlantı dizebileşenleri örnekleri hakkında daha fazla bilgi için DAO Yardım'daki "Özelliği Bağla" konusuna bakın.

## <a name="cdaoquerydefsetname"></a><a name="setname"></a>CDaoQueryDef::SetName

Geçici olmayan bir querydef'in adını değiştirmek istiyorsanız bu üye işlevi arayın.

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
İlişkili [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesinde geçici olmayan bir sorgu için yeni adı içeren dize.

### <a name="remarks"></a>Açıklamalar

Querydef adları benzersiz, kullanıcı tanımlı adlardır. QueryDef `SetName` nesnesi QueryDefs koleksiyonuna eklenilmeden önce arayabilirsiniz.

## <a name="cdaoquerydefsetodbctimeout"></a><a name="setodbctimeout"></a>CDaoQueryDef::SetODBCTimeout

Bir ODBC veri kaynağı na sorgulamadan önce zaman sınırını ayarlamak için bu üye işlevini çağırın.

```cpp
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>Parametreler

*nODBCTimeout*<br/>
Bir sorgudan önceki saniye sayısı zaman ları slenir.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, bağlı veri kaynağı "zaman dışında" sonraki işlemlerden önce varsayılan saniye sayısını geçersiz kılmanızı sağlar. Ağ erişim sorunları, aşırı sorgu işlem süresi ve benzeri nedenler nedeniyle bir işlem zaman alabilir. Sorgu `SetODBCTimeout` zaman öncemi değerini değiştirmek istiyorsanız, bu querydef ile bir sorgu yürütmeden önce arayın. (ODBC bağlantıları yeniden kullandığından, zaman ekme değeri aynı bağlantıdaki tüm istemciler için aynıdır.)

Sorgu zaman ları için varsayılan değer 60 saniyedir.

## <a name="cdaoquerydefsetparamvalue"></a><a name="setparamvalue"></a>CDaoQueryDef::SetParamValue

Çalışma zamanında querydef'teki bir parametrenin değerini ayarlamak için bu üye işlevini çağırın.

```
virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Değerini ayarlamak istediğiniz parametrenin adı.

*varValue*<br/>
Ayarlanan değer; bkz. Açıklamalar.

*Nındex*<br/>
Querydef'in Parametreler koleksiyonundaki parametrenin ordinal konumu. GetParameterCount ve [GetParameterInfo'ya](#getparameterinfo)yapılan aramalarla bu değeri elde edebilirsiniz. [GetParameterCount](#getparametercount)

### <a name="remarks"></a>Açıklamalar

Parametre zaten querydef's SQL dizesinin bir parçası olarak kurulmuş olmalıdır. Parametreye ada veya koleksiyondaki ordinal konumuna göre erişebilirsiniz.

`COleVariant` Nesne olarak ayarlanın değeri belirtin. Nesnenizde `COleVariant` istenen değeri ve türü ayarlama hakkında bilgi için [COleVariant sınıfına](../../mfc/reference/colevariant-class.md)bakın.

## <a name="cdaoquerydefsetreturnsrecords"></a><a name="setreturnsrecords"></a>CDaoQueryDef::SetReturnsRecords

Bu üye işlevini, harici bir veritabanına bir SQL geçiş sorgusu ayarlama işleminin bir parçası olarak çağırın.

```cpp
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>Parametreler

*bReturnsRecords*<br/>
Harici bir veritabanındaki sorgu kayıtları döndürürse TRUE'yu geçirin; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Böyle bir durumda, querydef'i oluşturmanız ve `CDaoQueryDef` diğer üye işlevleri kullanarak özelliklerini ayarlamanız gerekir. Harici veritabanlarının açıklaması için [SetConnect'e](#setconnect)bakın.

## <a name="cdaoquerydefsetsql"></a><a name="setsql"></a>CDaoQueryDef::SetSQL

Querydef'in yürüttüğü SQL deyimini ayarlamak için bu üye işlevin çağrısını arayın.

```cpp
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Parametreler

*Lpszsql*<br/>
Yürütme için uygun tam bir SQL deyimi içeren bir dize. Bu dizenin sözdizimi, sorgunuzun hedef aldığı DBMS'ye bağlıdır. Microsoft Jet veritabanı altyapısında kullanılan sözdizimi tartışması için DAO Help'deki "Code'da SQL Deyimleri Oluşturma" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Tipik bir `SetSQL` kullanım, bir SQL geçiş sorgusunda kullanılmak üzere bir querydef nesnesi ayarlamaktır. (Hedef DBMS'nizdeki SQL geçiş sorgularının sözdizimi için DBMS'nizin belgelerine bakın.)

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
