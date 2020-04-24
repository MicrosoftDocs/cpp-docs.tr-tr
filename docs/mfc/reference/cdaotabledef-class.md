---
title: CDaoTableDef Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
helpviewer_keywords:
- CDaoTableDef [MFC], CDaoTableDef
- CDaoTableDef [MFC], Append
- CDaoTableDef [MFC], CanUpdate
- CDaoTableDef [MFC], Close
- CDaoTableDef [MFC], Create
- CDaoTableDef [MFC], CreateField
- CDaoTableDef [MFC], CreateIndex
- CDaoTableDef [MFC], DeleteField
- CDaoTableDef [MFC], DeleteIndex
- CDaoTableDef [MFC], GetAttributes
- CDaoTableDef [MFC], GetConnect
- CDaoTableDef [MFC], GetDateCreated
- CDaoTableDef [MFC], GetDateLastUpdated
- CDaoTableDef [MFC], GetFieldCount
- CDaoTableDef [MFC], GetFieldInfo
- CDaoTableDef [MFC], GetIndexCount
- CDaoTableDef [MFC], GetIndexInfo
- CDaoTableDef [MFC], GetName
- CDaoTableDef [MFC], GetRecordCount
- CDaoTableDef [MFC], GetSourceTableName
- CDaoTableDef [MFC], GetValidationRule
- CDaoTableDef [MFC], GetValidationText
- CDaoTableDef [MFC], IsOpen
- CDaoTableDef [MFC], Open
- CDaoTableDef [MFC], RefreshLink
- CDaoTableDef [MFC], SetAttributes
- CDaoTableDef [MFC], SetConnect
- CDaoTableDef [MFC], SetName
- CDaoTableDef [MFC], SetSourceTableName
- CDaoTableDef [MFC], SetValidationRule
- CDaoTableDef [MFC], SetValidationText
- CDaoTableDef [MFC], m_pDAOTableDef
- CDaoTableDef [MFC], m_pDatabase
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
ms.openlocfilehash: adc31ccbf2be34aa1df1fa56111d1990701a6329
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754693"
---
# <a name="cdaotabledef-class"></a>CDaoTableDef Sınıfı

Bir taban tablonun veya ekli tablonun depolanan tanımını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoTableDef : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Bir `CDaoTableDef` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoTableDef::Ek](#append)|Veritabanına yeni bir tablo ekler.|
|[CDaoTableDef::CanUpdate](#canupdate)|Tablo güncelleştirilebiliyorsa sıfırsız döndürür (alanların veya tablo özelliklerinin tanımını değiştirebilirsiniz).|
|[CDaoTableDef::Kapat](#close)|Açık bir tabledef kapatır.|
|[CDaoTableDef::Oluştur](#create)|[Append](#append)kullanarak veritabanına eklenebilecek bir tablo oluşturur.|
|[CDaoTableDef::CreateField](#createfield)|Tablo için alan oluşturmak için çağrıldı.|
|[CDaoTableDef::CreateIndex](#createindex)|Tablo için dizin oluşturmak için çağrıldı.|
|[CDaoTableDef::DeleteField](#deletefield)|Bir tablodan bir alanı silmek için çağrıldı.|
|[CDaoTableDef::DeleteIndex](#deleteindex)|Bir tablodan bir dizin silmek için çağrıldı.|
|[CDaoTableDef::GetAttributes](#getattributes)|Nesnenin bir veya daha fazla `CDaoTableDef` özelliğini gösteren bir değer verir.|
|[CDaoTableDef::GetConnect](#getconnect)|Tablonun kaynağı hakkında bilgi sağlayan bir değer verir.|
|[CDaoTableDef::GetDateCreated](#getdatecreated)|`CDaoTableDef` Nesnenin altında yatan temel tablonun oluşturulduğu tarihi ve saati döndürür.|
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Taban tablonun tasarımında yapılan en son değişikliğin tarih ve saatini verir.|
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Tablodaki alan sayısını temsil eden bir değer verir.|
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Tablodaki alanlar hakkında belirli türde bilgiler verir.|
|[CDaoTableDef::GetIndexCount](#getindexcount)|Tablo için dizin sayısını verir.|
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Tablonun dizinleri hakkında belirli türde bilgiler verir.|
|[CDaoTableDef::GetName](#getname)|Tablonun kullanıcı tanımlı adını döndürür.|
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Tablodaki kayıt sayısını verir.|
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Kaynak veritabanında ekli tablonun adını belirten bir değer döndürür.|
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Değiştirildikçe veya tabloya eklendikçe alandaki verileri doğrulayan bir değer verir.|
|[CDaoTableDef::GetValidationMetin](#getvalidationtext)|Alan nesnesinin değeri belirtilen doğrulama kuralını karşılamazsa, uygulamanızın görüntülediği iletimetnini belirten bir değer döndürür.|
|[CDaoTableDef::Açık](#isopen)|Tablo açıksa sıfırsız döndürür.|
|[CDaoTableDef::Aç](#open)|Veritabanının TableDef koleksiyonunda depolanan varolan bir tabloyu açar.|
|[CDaoTableDef::RefreshLink](#refreshlink)|Ekli tablonun bağlantı bilgilerini güncelleştirir.|
|[CDaoTableDef::SetAttributes](#setattributes)|Nesnenin bir veya daha fazla `CDaoTableDef` özelliğini gösteren bir değer ayarlar.|
|[CDaoTableDef::SetConnect](#setconnect)|Tablonun kaynağı hakkında bilgi sağlayan bir değer ayarlar.|
|[CDaoTableDef::SetName](#setname)|Tablonun adını ayarlar.|
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Kaynak veritabanında ekli bir tablonun adını belirten bir değer ayarlar.|
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Tablodeğiştirildikçe veya tabloya eklendikçe alandaki verileri doğrulayan bir değer ayarlar.|
|[CDaoTableDef::SetValidationMetin](#setvalidationtext)|Alan nesnesinin değeri belirtilen doğrulama kuralını karşılamazsa, uygulamanızın görüntülediği iletimetnini belirten bir değer ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Tabledef nesnesinin altında yatan DAO arabirimine işaretçi.|
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Bu tablo için kaynak veritabanı.|

## <a name="remarks"></a>Açıklamalar

Her DAO veritabanı nesnesi, kaydedilen tüm DAO tabledef nesnelerini içeren TableDefs adlı bir koleksiyon tutar.

Bir `CDaoTableDef` nesne kullanarak tablo tanımını manipüle emzirsiniz. Örneğin, şunları yapabilirsiniz:

- Veritabanındaki herhangi bir yerel, bağlı veya harici tablonun alan ve dizin yapısını inceleyin.

- Ekli `SetConnect` tablolar `SetSourceTableName` için ve üye işlevleri arayın `RefreshLink` ve bağlı tablolara bağlantıları güncelleştirmek için üye işlevi kullanın.

- Tablodaki `CanUpdate` alan tanımlarını yeniden belirleyip erteleyip edinamayacağınızı belirlemek için üye işlevi arayın.

- `GetValidationRule` Ve `SetValidationRule` `SetValidationText` üye işlevlerini kullanarak `GetValidationText` doğrulama koşullarını alın veya ayarlayın.

- Tablo, `Open` dynaset veya anlık görüntü türü `CDaoRecordset` nde bir nesne oluşturmak için üye işlevi kullanın.

    > [!NOTE]
    >  DAO veritabanı sınıfları Açık Veritabanı Bağlantısı (ODBC) dayalı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" öneki vardır. DaO sınıfları ile ODBC veri kaynaklarına erişebilirsiniz; DAO sınıfları genellikle microsoft jet veritabanı altyapısına özgü olduğundan üstün özellikler sunar.

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Varolan bir tabloyla çalışmak veya yeni bir tablo oluşturmak için tabledef nesnelerini kullanmak için

1. Her durumda, önce `CDaoTableDef` tablonun ait olduğu [bir CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine işaretçi sağlayan bir nesne oluştur.

1. Sonra ne istediğinize bağlı olarak, aşağıdakileri yapın:

   - Varolan kaydedilmiş bir tabloyu kullanmak için tabledef nesnesinin [Açık](#open) üye işlevini arayarak kaydedilen tablonun adını belirtin.

   - Yeni bir tablo oluşturmak için tabledef object'in tablonun adını sağlayan Üye [Oluştur](#create) işlevini çağırın. Tabloya alan ve dizin eklemek için [CreateField](#createfield) ve [CreateIndex'i](#createindex) arayın.

   - Veritabanının TableDefs koleksiyonuna ekleyerek tabloyu kaydetmek için [Append'i](#append) arayın. `Create`açık bir duruma tabledef koyar, `Create` bu yüzden `Open`aradıktan sonra aramayın .

        > [!TIP]
        >  Kaydedilen tabloları oluşturmanın en kolay yolu, bunları oluşturmak ve Microsoft Access'i kullanarak veritabanınızda depolamaktır. Ardından bunları MFC kodunuzda açıp kullanabilirsiniz.

Açtığınız veya oluşturduğunuz tabledef nesnesini kullanmak `CDaoRecordset` için, *nOpenType* parametresinde bir `dbOpenTable` değeriçeren tablodef adını belirterek bir nesne oluşturun ve açın.

Bir nesne oluşturmak için bir `CDaoRecordset` tabledef nesnesi kullanmak için, genellikle oluşturmak veya yukarıda açıklandığı gibi bir tabledef açmak, sonra [cDaoRecordset::Aç](../../mfc/reference/cdaorecordset-class.md#open)çağırdığınızda tabledef nesnesine bir işaretçi geçerek bir kayıt kümesi nesnesi oluşturmak. Geçtiğin tablo açık bir durumda olmalıdır. Daha fazla bilgi için [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)sınıfına bakın.

Tabledef nesnesini kullanmayı bitirdiğinizde, [Yakın](../../mfc/reference/cdaorecordset-class.md#close) üye işlevini arayın; sonra tabledef nesnesini yok edin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="cdaotabledefappend"></a><a name="append"></a>CDaoTableDef::Ek

Veritabanında tabledef kaydetmek için yeni bir tabledef nesnesi oluşturmak için [Oluştur'u](#create) aradıktan sonra bu üye işlevi arayın.

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

İşlev, nesneyi veritabanının TableDefs koleksiyonuna ekler. Tabledef'i geçici bir nesne olarak kullanabilirsiniz, ancak ekolarak tanımlayarak, ancak kaydetmek ve kullanmak `Append`istiyorsanız, aramanız gerekir.

> [!NOTE]
> Adsız bir tabledef (null veya boş dize içeren) eklemeye çalışırsanız, MFC bir özel durum atar.

İlgili bilgiler için DAO Yardım'daki "Uygulama Yöntemi" konusuna bakın.

## <a name="cdaotabledefcanupdate"></a><a name="canupdate"></a>CDaoTableDef::CanUpdate

Bir `CDaoTableDef` nesnenin altında yatan tablonun tanımının değiştirilip değiştirilemeyeceğini belirlemek için bu üye işlevi arayın.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo yapısı (şema) değiştirilebilirse (alanları ve dizinleri ekleme veya silme) sıfırsız, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir nesnenin `CDaoTableDef` altında yatan yeni oluşturulan tablo güncelleştirilebilir ve nesnenin altında yatan eklenmiş tablo `CDaoTableDef` güncelleştirilemez. Elde `CDaoTableDef` edilen kayıt kümesi güncel tutulamaz olsa bile, bir nesne güncellenebilir olabilir.

İlgili bilgiler için DAO Yardım'daki "Güncelilebilir Özellik" konusuna bakın.

## <a name="cdaotabledefcdaotabledef"></a><a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef

Bir `CDaoTableDef` nesne inşa eder.

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturduktan sonra [Oluştur](#create) veya [Aç](#open) üye işlevini aramanız gerekir. Nesneyle bitirdiğinizde, [Yakın](#close) üye işlevini aramalı ve `CDaoTableDef` nesneyi yok etmelisiniz.

## <a name="cdaotabledefclose"></a><a name="close"></a>CDaoTableDef::Kapat

Tabledef nesnesini kapatmak ve serbest bırakmak için bu üye işlevi arayın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Genellikle aradıktan `Close`sonra, yeni ile tahsis edildi eğer tabledef nesnesi silersiniz. **new**

Aradıktan sonra [aç'ı](#open) tekrar arayabilirsiniz. `Close` Bu, tabledef nesnesini yeniden kullanmanıza olanak tanır.

İlgili bilgiler için DAO Yardım'daki "Yöntemi Kapat" konusuna bakın.

## <a name="cdaotabledefcreate"></a><a name="create"></a>CDaoTableDef::Oluştur

Yeni bir kaydedilmiş tablo oluşturmak için bu üye işlevi arayın.

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Tablonun adını içeren bir dize için bir işaretçi.

*lAttributes*<br/>
Tablonun özelliklerine karşılık gelen bir değer tabledef nesnesi tarafından temsil edilir. Aşağıdaki sabitlerden herhangi birini birleştirmek için bitwise-OR'u kullanabilirsiniz:

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için tablo, özel kullanım için açılmış ekli bir tablo olduğunu gösterir.|
|`dbAttachSavePWD`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, bağlı tablonun kullanıcı kimliği ve parolasının bağlantı bilgileriyle birlikte kaydedildiğini gösterir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo olduğunu gösterir.|

*lpszSrcTable*<br/>
Kaynak tablo adını içeren bir dize için işaretçi. Varsayılan olarak bu değer NULL olarak başharfe çevrilir.

*lpszConnect*<br/>
Varsayılan bağlantı dizesini içeren bir dize için işaretçi. Varsayılan olarak bu değer NULL olarak başharfe çevrilir.

### <a name="remarks"></a>Açıklamalar

Tabledef adını verdikten sonra, veritabanının TableDefs koleksiyonunda tabledef kaydetmek için [Append'i](#append) arayabilirsiniz. Aradıktan `Append`sonra, tabledef açık durumdadır ve [cdaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturmak için kullanabilirsiniz.

İlgili bilgiler için DAO Yardım'daki "CreateTableDef Method" konusuna bakın.

## <a name="cdaotabledefcreatefield"></a><a name="createfield"></a>CDaoTableDef::CreateField

Tabloya alan eklemek için bu üye işlevi arayın.

```cpp
void CreateField(
    LPCTSTR lpszName,
    short nType,
    long lSize,
    long lAttributes = 0);

void CreateField(CDaoFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Bu alanın adını belirten bir dize ifadesine işaretçi.

*nTipi*<br/>
Alanın veri türünü gösteren bir değer. Ayar şu değerlerden biri olabilir:

|Tür|Boyut (bayt)|Açıklama|
|----------|--------------------|-----------------|
|`dbBoolean`|1 bayt|Bool|
|`dbByte`|BYTE|
|`dbInteger`|2|int|
|`dbLong`|4|long|
|`dbCurrency`|8|Para Birimi ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|float|
|`dbDouble`|8|double|
|`dbDate`|8|Tarih/Saat ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Metin ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Uzun İkili (OLE Nesnesi), [CLongBinary](../../mfc/reference/clongbinary-class.md) veya [CByteArray](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|Not ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|

*lSize*<br/>
Metin içeren bir alanın veya metin veya sayısal değerler içeren bir alanın sabit boyutunu baytlarda en büyük boyutunu gösteren değer. *lSize* parametresi metin alanları hariç tüm için yoksayılır.

*lAttributes*<br/>
Alanın özelliklerine karşılık gelen ve bitwise-OR kullanılarak birleştirilebilen bir değer.

|Sabit|Açıklama|
|--------------|-----------------|
|`dbFixedField`|Alan boyutu sabittir (Sayısal alanlar için varsayılan).|
|`dbVariableField`|Alan boyutu değişkendir (yalnızca Metin alanları).|
|`dbAutoIncrField`|Yeni kayıtların alan değeri otomatik olarak değiştirilemeyen benzersiz uzun bir tamsayıya dönüştürülr. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.|
|`dbUpdatableField`|Alan değeri değiştirilebilir.|
|`dbDescending`|Alan azalan (Z - A veya 100 - 0) sırasına göre sıralanır (yalnızca Dizin nesnesinin Alanları koleksiyonundaki bir Alan nesnesi için geçerlidir). Bu sabiti atlarsanız, alan artan (A - Z veya 0 - 100) sırada (varsayılan) sıralanır.|

*Fieldınfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bir `DAOField` (OLE) nesnesi oluşturulur ve `DAOTableDef` (OLE) nesnesinin Alanlar koleksiyonuna eklenir. Nesne özelliklerini incelemek için kullanımının yanı `CDaoFieldInfo` sıra, bir tablodef yeni alanlar oluşturmak için bir giriş parametresi oluşturmak için de kullanabilirsiniz. İlk sürümü `CreateField` kullanmak daha kolaydır, ancak daha ince kontrol istiyorsanız, bir `CreateField` `CDaoFieldInfo` parametre alır , ikinci sürümünü kullanabilirsiniz.

Bunun bir `CreateField` `CDaoFieldInfo` parametre sayılsa, `CDaoFieldInfo` yapının aşağıdaki üyelerinin her birini dikkatlice ayarlamanız gerekir:

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

Kalan üyeler `CDaoFieldInfo` üye için uygun olarak **0,** FALSE veya boş bir dize `CDaoException` olarak ayarlanmalıdır veya bir oluşabilir.

İlgili bilgiler için DAO Yardım'daki "CreateField Method" konusuna bakın.

## <a name="cdaotabledefcreateindex"></a><a name="createindex"></a>CDaoTableDef::CreateIndex

Tabloya dizin eklemek için bu işlevi çağırın.

```cpp
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>Parametreler

*indexinfo*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına bir başvuru.

### <a name="remarks"></a>Açıklamalar

Dizinler, veritabanı tablolarından erişilen kayıtların sırasını ve yinelenen kayıtların kabul edilip edilemeyeceğini belirtir. Dizinler de verilere verimli erişim sağlar.

Tablolar için dizin oluşturmanız gerekmez, ancak büyük, dizine eklenmemiş tablolarda, belirli bir kayda erişmek veya bir kayıt kümesi oluşturmak uzun zaman alabilir. Diğer taraftan, çok fazla dizin oluşturmak, tüm dizinler otomatik olarak güncelleştirildikçe güncelleştirmeyi, eklemeyi ve silme işlemlerini yavaşlatır. Hangi dizinlerin oluşturacağına karar vererken bu faktörleri göz önünde bulundurun.

Yapının `CDaoIndexInfo` aşağıdaki üyeleri ayarlanmalıdır:

- `m_strName`Bir ad sağlanmalıdır.

- `m_pFieldInfos`Bir dizi `CDaoIndexFieldInfo` yapıyı işaret etmelidir.

- `m_nFields``CDaoFieldInfo` Yapı dizisindeki alan sayısını belirtmeniz gerekir.

Kalan üyeler FALSE olarak ayarlanırsa yoksayılır. Buna ek `m_lDistinctCount` olarak, üye dizin oluşturulması sırasında göz ardı edilir.

## <a name="cdaotabledefdeletefield"></a><a name="deletefield"></a>CDaoTableDef::DeleteField

Bir alanı kaldırmak ve erişilemez hale getirmek için bu üye işlevi arayın.

```cpp
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Varolan bir alanın adı olan bir dize ifadesiiçin işaretçi.

*Nındex*<br/>
Dizin tarafından arama için tablonun sıfır tabanlı Alanlar koleksiyonundaki alanın dizin.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini, veritabanına ekedilmemiş veya [CanUpdate](#canupdate) sıfırsız döndüğünde yeni bir nesne üzerinde kullanabilirsiniz.

İlgili bilgiler için DAO Yardım'daki "Silme Yöntemi" konusuna bakın.

## <a name="cdaotabledefdeleteindex"></a><a name="deleteindex"></a>CDaoTableDef::DeleteIndex

Altta yatan tablodaki bir dizini silmek için bu üye işlevi arayın.

```cpp
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Varolan bir dizinin adı olan dize ifadesine işaretçi.

*Nındex*<br/>
Dizin tarafından arama için veritabanının sıfır tabanlı TableDefs koleksiyonundaki dizin nesnesinin dizi dizini.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini, veritabanına ekilmemiş yeni bir nesne de veya [CanUpdate](#canupdate) sıfırsız döndüğünde kullanabilirsiniz.

İlgili bilgiler için DAO Yardım'daki "Silme Yöntemi" konusuna bakın.

## <a name="cdaotabledefgetattributes"></a><a name="getattributes"></a>CDaoTableDef::GetAttributes

Bir `CDaoTableDef` nesne için, iade değeri `CDaoTableDef` nesne tarafından temsil edilen tablonun özelliklerini belirtir ve bu sabitlerin toplamı olabilir:

```
long GetAttributes();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin bir veya daha fazla `CDaoTableDef` özelliğini gösteren bir değer verir.

### <a name="remarks"></a>Açıklamalar

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için tablo, özel kullanım için açılmış ekli bir tablo olduğunu gösterir.|
|`dbAttachSavePWD`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, bağlı tablonun kullanıcı kimliği ve parolasının bağlantı bilgileriyle birlikte kaydedildiğini gösterir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo olduğunu gösterir.|
|`dbAttachedTable`|Tablonun, Paradox veritabanı gibi ODBC olmayan bir veritabanından eklenmiş bir tablo olduğunu gösterir.|
|`dbAttachedODBC`|Tablonun Microsoft SQL Server gibi bir ODBC veritabanından eklenmiş bir tablo olduğunu gösterir.|

Sistem tablosu, Microsoft Jet veritabanı altyapısı tarafından çeşitli dahili bilgileri içerecek şekilde oluşturulan tablodur.

Gizli tablo, Microsoft Jet veritabanı altyapısı tarafından geçici olarak kullanılmak üzere oluşturulan tablodur.

İlgili bilgiler için DAO Yardım'daki "Öznitelikler Özelliği" konusuna bakın.

## <a name="cdaotabledefgetconnect"></a><a name="getconnect"></a>CDaoTableDef::GetConnect

Bir veri kaynağının bağlantı dizesini elde etmek için bu üye işlevi arayın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo `CString` için yol ve veritabanı türünü içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Ekli `CDaoTableDef` bir tabloyu temsil eden `CString` bir nesne için nesne bir veya iki bölümden (veritabanı türü belirtimi ve veritabanına giden bir yol) oluşur.

Aşağıdaki tabloda gösterildiği gibi yol veritabanı dosyalarını içeren dizin için tam yoldur ve tanımlayıcı "DATABASE=" tarafından önce olmalıdır. Bazı durumlarda (Microsoft Jet ve Microsoft Excel veritabanlarında olduğu gibi), veritabanı yolu bağımsız değişkenine belirli bir dosya adı dahildir.

[CDaoTableDef tablosu::SetConnect](#setconnect) olası veritabanı türlerini ve bunların karşılık gelen veritabanı belirteçlerini ve yollarını gösterir:

Microsoft Jet veritabanı taban tabloları için belirtici boş bir dize ("") dir.

Parola gerekliyse ancak sağlanmadıysa, ODBC sürücüsü bir tabloya ilk erişici olduğunda ve bağlantı kapatıp yeniden açıldığında tekrar bir giriş iletişim kutusu görüntüler. Ekli bir tablo özniteliği `dbAttachSavePWD` varsa, tablo yeniden açıldığında giriş istemi görünmez.

İlgili bilgiler için DAO Yardım'daki "Özelliği Bağla" konusuna bakın.

## <a name="cdaotabledefgetdatecreated"></a><a name="getdatecreated"></a>CDaoTableDef::GetDateCreated

`CDaoTableDef` Nesnenin altında yatan tablonun oluşturulduğu tarih ve saati belirlemek için bu işlevi arayın.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin altında yatan tablonun oluşturulma tarih `CDaoTableDef` ve saatini içeren bir değer.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablonun oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, kullanıcılar tutarsızlıkları önlemek için bu ayarları doğrudan dosya sunucusundan almalıdır; yani, tüm istemciler bir "standart" zaman kaynağı kullanmalısınız - belki de bir sunucudan.

İlgili bilgiler için DAO Yardım'daki "DateCreated, LastUpdated Properties" konusuna bakın.

## <a name="cdaotabledefgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoTableDef::GetDateLastUpdated

`CDaoTableDef` Nesnenin en son güncelleştirilen tablonun tarihini ve saatini belirlemek için bu işlevi arayın.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoTableDef` Nesnenin altında yatan tablonun en son güncelleştirilen tarih ve saati içeren bir değer.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablonun oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, kullanıcılar tutarsızlıkları önlemek için bu ayarları doğrudan dosya sunucusundan almalıdır; yani, tüm istemciler bir "standart" zaman kaynağı kullanmalısınız - belki de bir sunucudan.

İlgili bilgiler için DAO Yardım'daki "DateCreated, LastUpdated Properties" konusuna bakın.

## <a name="cdaotabledefgetfieldcount"></a><a name="getfieldcount"></a>CDaoTableDef::GetFieldCount

Tabloda tanımlanan alanların sayısını almak için bu üye işlevi arayın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablodaki alan sayısı.

### <a name="remarks"></a>Açıklamalar

Değeri 0 ise, koleksiyonda nesne yok.

İlgili bilgiler için DAO Yardım'daki "Count Property" konusuna bakın.

## <a name="cdaotabledefgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoTableDef::GetFieldInfo

Tabloda tanımlanan bir alan hakkında çeşitli bilgiler elde etmek için bu üye işlevi arayın.

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
Dizin tarafından arama için tablonun sıfır tabanlı Alanlar koleksiyonundaki alan nesnesinin dizin.

*Fieldınfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına bir başvuru.

*dwInfoOptions*<br/>
Alan hakkında hangi bilgilerin alınaaçık olduğunu belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürülmesine neden oldukları yla birlikte burada listelenir:

- `AFX_DAO_PRIMARY_INFO`(Varsayılan) Ad, tür, boyut, öznitelikler. En hızlı performans için bu seçeneği kullanın.

- `AFX_DAO_SECONDARY_INFO`Birincil bilgi, artı: Ordinal Position, Gerekli, İzin Sıfır Uzunluk, Collating Sipariş, Yabancı Ad, Kaynak Alan, Kaynak Tablo

- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgiler, artı: Doğrulama Kuralı, Doğrulama Metni, Varsayılan Değer

*Lpszname*<br/>
Ada göre arama yapmak için alan nesnesinin adına işaretçi. Ad, alanı benzersiz olarak adlandıran 64 karaktere kadar olan bir dizedir.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, bir alanı dizin olarak aramanızı sağlar. Diğer sürüm, bir alanı ada göre aramanızı sağlar.

Döndürülen bilgilerin açıklaması için [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki düzeyler için de bilgi alırsınız.

İlgili bilgiler için DAO Yardım'daki "Öznitelikler Özelliği" konusuna bakın.

## <a name="cdaotabledefgetindexcount"></a><a name="getindexcount"></a>CDaoTableDef::GetIndexCount

Bir tablo için dizin sayısını elde etmek için bu üye işlevi arayın.

```
short GetIndexCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo için dizin sayısı.

### <a name="remarks"></a>Açıklamalar

Değeri 0 ise, koleksiyonda dizin yok.

İlgili bilgiler için DAO Yardım'daki "Count Property" konusuna bakın.

## <a name="cdaotabledefgetindexinfo"></a><a name="getindexinfo"></a>CDaoTableDef::GetIndexInfo

Tabloda tanımlanan bir dizin hakkında çeşitli bilgiler elde etmek için bu üye işlevi arayın.

```cpp
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Tablonun sıfır tabanlı Dizinler koleksiyonundaki Dizin nesnesinin sayısal dizini, koleksiyondaki konumuna göre arama için.

*indexinfo*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına bir başvuru.

*dwInfoOptions*<br/>
Dizin hakkında hangi bilgilerin alınaaçık olduğunu belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürülmesine neden oldukları yla birlikte burada listelenir:

- `AFX_DAO_PRIMARY_INFO`İsim, Alan Bilgisi, Alanlar. En hızlı performans için bu seçeneği kullanın.

- `AFX_DAO_SECONDARY_INFO`Birincil bilgi, artı: Birincil, Benzersiz, Kümelenmiş, Nulls yoksay, Gerekli, Yabancı

- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgiler, artı: Farklı Sayı

*Lpszname*<br/>
Ada göre arama yapmak için dizin nesnesinin adına işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, bir dizini koleksiyondaki konumuna göre aramanızı sağlar. Diğer sürüm, bir dizini ada göre aramanızı sağlar.

Döndürülen bilgilerin açıklaması için [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki düzeyler için de bilgi alırsınız.

İlgili bilgiler için DAO Yardım'daki "Öznitelikler Özelliği" konusuna bakın.

## <a name="cdaotabledefgetname"></a><a name="getname"></a>CDaoTableDef::GetName

Altta yatan tablonun kullanıcı tanımlı adını almak için bu üye işlevini arayın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo için kullanıcı tanımlı bir ad.

### <a name="remarks"></a>Açıklamalar

Bu ad bir harfle başlar ve en fazla 64 karakter içerebilir. Sayıları içerebilir ve karakterleri alt çizebilir, ancak noktalama işareti veya boşluk içeremez.

İlgili bilgiler için DAO Yardım'daki "Ad Özelliği" konusuna bakın.

## <a name="cdaotabledefgetrecordcount"></a><a name="getrecordcount"></a>CDaoTableDef::GetRecordCount

Bir `CDaoTableDef` nesnede kaç kayıt olduğunu öğrenmek için bu üye işlevi arayın.

```
long GetRecordCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tabledef nesnesinde erişilen kayıt sayısı.

### <a name="remarks"></a>Açıklamalar

Tablo `GetRecordCount` türünde `CDaoTableDef` bir nesne çağrısı, tablodaki yaklaşık kayıt sayısını yansıtır ve tablo kayıtları ekleyip silinir silinmez hemen etkilenir. Geri alındı işlemleri CDaoWorkSpace arayana kadar kayıt sayısının bir parçası olarak [görünür::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). Kaydı `CDaoTableDef` olmayan bir nesnenin kayıt sayısı özelliği 0'a sahiptir. Ekli tablolar veya ODBC veritabanları ile `GetRecordCount` çalışırken, her zaman -1 döndürür.

İlgili bilgiler için DAO Yardım'daki "RecordCount Property" konusuna bakın.

## <a name="cdaotabledefgetsourcetablename"></a><a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName

Kaynak veritabanında ekli bir tablonun adını almak için bu üye işlevi arayın.

```
CString GetSourceTableName();
```

### <a name="return-value"></a>Dönüş Değeri

Eklenmiş bir tablonun kaynak adını belirten bir `CString` nesne veya yerel bir veri tablosu varsa boş bir dize.

### <a name="remarks"></a>Açıklamalar

Ekli tablo, Microsoft Jet veritabanına bağlı başka bir veritabanındaki tablodur. Ekteki tablolara ait veriler, diğer uygulamalar tarafından manipüle edilebildiği dış veritabanında kalır.

İlgili bilgiler için DAO Help'deki "SourceTableName Property" konusuna bakın.

## <a name="cdaotabledefgetvalidationrule"></a><a name="getvalidationrule"></a>CDaoTableDef::GetValidationRule

Bir tablo def için doğrulama kuralını almak için bu üye işlevi arayın.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen `CString` veya tabloya eklenen bir alandaki verileri doğrulayan nesne.

### <a name="remarks"></a>Açıklamalar

Doğrulama kuralları güncelleştirme işlemleriyle bağlantılı olarak kullanılır. Bir tabledef bir doğrulama kuralı içeriyorsa, veriler değiştirilmeden önce bu tablodaki güncelleştirmelerin önceden belirlenmiş ölçütlere uyması gerekir. Değişiklik ölçütle eşleşmiyorsa, [GetValidationText](#getvalidationtext) değerini içeren bir özel durum atılır. Bir `CDaoTableDef` nesne için `CString` bu, ekli bir tablo için salt okunur ve taban tablo için okuma/yazma dır.

İlgili bilgiler için DAO Yardım'daki "Doğrulama Kuralı Özelliği" konusuna bakın.

## <a name="cdaotabledefgetvalidationtext"></a><a name="getvalidationtext"></a>CDaoTableDef::GetValidationMetin

Bir kullanıcı doğrulama kuralıyla eşleşmeyen verileri girdiğinde görüntülenecek dizeyi almak için bu işlevi çağırın.

```
CString GetValidationText();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı `CString` doğrulama kuralıyla eşleşmeyen verileri girerse görüntülenen metni belirten bir nesne.

### <a name="remarks"></a>Açıklamalar

Bir `CDaoTableDef` nesne için `CString` bu, ekli bir tablo için salt okunur ve taban tablo için okuma/yazma dır.

İlgili bilgiler için DAO Yardım'daki "DoğrulamaMetni Özelliği" konusuna bakın.

## <a name="cdaotabledefisopen"></a><a name="isopen"></a>CDaoTableDef::Açık

Nesnenin `CDaoTableDef` şu anda açık olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne açıksa `CDaoTableDef` sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaotabledefm_pdatabase"></a><a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase

Bu tablo için [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaotabledefm_pdaotabledef"></a><a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef

Nesnenin altında yatan DAO tabledef nesnesi `CDaoTableDef` için OLE arabirimine bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

DAO arabirimine doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.

## <a name="cdaotabledefopen"></a><a name="open"></a>CDaoTableDef::Aç

Veritabanının TableDef koleksiyonunda daha önce kaydedilmiş bir tabledef açmak için bu üye işlevi arayın.

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Tablo adını belirten bir dize için işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaotabledefrefreshlink"></a><a name="refreshlink"></a>CDaoTableDef::RefreshLink

Ekli bir tablonun bağlantı bilgilerini güncelleştirmek için bu üye işlevini arayın.

```cpp
void RefreshLink();
```

### <a name="remarks"></a>Açıklamalar

İlgili `CDaoTableDef` nesneüzerinde [SetConnect'i](#setconnect) arayarak ve bilgileri güncelleştirmek için `RefreshLink` üye işlevini kullanarak ekli bir tablonun bağlantı bilgilerini değiştirirsiniz. Aradığınızda, `RefreshLink`ekli tablonun özellikleri değişmez.

Değiştirilen bağlantı bilgilerini etkili olmaya zorlamak için, bu tabloya dayalı tüm açık [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnelerinin kapatılması gerekir.

İlgili bilgiler için DAO Yardım'daki "RefreshLink Method" konusuna bakın.

## <a name="cdaotabledefsetattributes"></a><a name="setattributes"></a>CDaoTableDef::SetAttributes

Nesnenin bir veya daha fazla `CDaoTableDef` özelliğini gösteren bir değer ayarlar.

```cpp
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>Parametreler

*lAttributes*<br/>
`CDaoTableDef` Nesne tarafından temsil edilen tablonun özellikleri ve bu sabitlerin toplamı olabilir:

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için tablo, özel kullanım için açılmış ekli bir tablo olduğunu gösterir.|
|`dbAttachSavePWD`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, bağlı tablonun kullanıcı kimliği ve parolasının bağlantı bilgileriyle birlikte kaydedildiğini gösterir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo olduğunu gösterir.|

### <a name="remarks"></a>Açıklamalar

Birden çok öznitelik ayarlarken, bitwise-OR işleci kullanarak uygun sabitleri toplamı yaparak bunları birleştirebilirsiniz. Eksiz bir tabloüzerinde ayar `dbAttachExclusive` bir özel durum oluşturur. Aşağıdaki değerleri birleştirme de bir özel durum üretir:

- **dbAttachExclusive &#124; dbAttachedODBC**

- **dbAttachSavePWD &#124; dbAttachedTable**

İlgili bilgiler için DAO Yardım'daki "Öznitelikler Özelliği" konusuna bakın.

## <a name="cdaotabledefsetconnect"></a><a name="setconnect"></a>CDaoTableDef::SetConnect

Ekli `CDaoTableDef` bir tabloyu temsil eden bir nesne için dize nesnesi bir veya iki bölümden (veritabanı türü belirtimi ve veritabanına giden bir yol) oluşur.

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Parametreler

*lpszConnect*<br/>
ODBC veya yüklenebilir ISAM sürücüleri geçmek için ek parametreleri belirten bir dize ifade için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda gösterildiği gibi yol veritabanı dosyalarını içeren dizin için tam yoldur ve tanımlayıcı "DATABASE=" tarafından önce olmalıdır. Bazı durumlarda (Microsoft Jet ve Microsoft Excel veritabanlarında olduğu gibi), veritabanı yolu bağımsız değişkenine belirli bir dosya adı dahildir.

> [!NOTE]
> "DATABASE=drive:\\\path" formunun yol ifadelerinde eşit işaretin etrafında boşluk eklemeyin. Bu, bir özel durum atılmasına ve bağlantının başarısız olmasına neden olur.

Aşağıdaki tablo, olası veritabanı türlerini ve bunların karşılık gelen veritabanı belirteçlerini ve yollarını gösterir:

|Veritabanı türü|Belirleyici|Yol|
|-------------------|---------------|----------|
|Jet veritabanı altyapısını kullanarak veritabanı|"[ `database`];"|" `drive`\\\ :*yol*\\\ *dosya adı*. MDB"|
|dBASE III|"dBASE III;"|" `drive`\\\ :*yol*"|
|dBASE IV|"dBASE IV;"|" `drive`\\\ :*yol*"|
|dBASE 5|"dBASE 5.0;"|" `drive`\\\ :*yol*"|
|Paradoks 3.x|"Paradoks 3.x;"|" `drive`\\\ :*yol*"|
|Paradoks 4.x|"Paradoks 4.x;"|" `drive`\\\ :*yol*"|
|Paradoks 5.x|"Paradoks 5.x;"|" `drive`\\\ :*yol*"|
|Excel 3.0|"Excel 3.0;"|" `drive`\\\ :*yol*\\\ *dosya adı*. XLS"|
|Excel 4.0|"Excel 4.0;"|" `drive`\\\ :*yol*\\\ *dosya adı*. XLS"|
|Excel 5.0 veya Excel 95|"Excel 5.0;"|" `drive`\\\ :*yol*\\\ *dosya adı*. XLS"|
|Excel 97|"Excel 8.0;"|" `drive`\\\ :*yol*\ *dosya adı*. XLS"|
|HTML İçe Aktarma|"HTML Alma;"|" `drive`\\\ :*yol*\ *dosya adı*"|
|HTML Dışa Aktarma|"HTML Dışa Aktarma;"|" `drive`\\\ :*yol*"|
|Metin|"Metin;"|"sürücü:\\\yol"|
|ODBC|"ODBC; VERITABANı= `database`; UID= *kullanıcı;* PWD= *şifre;* DSN= *datasourcename;* GİrİşZAMANI= *saniye;*" (Bu, tüm sunucular için tam bir bağlantı dizesi olmayabilir; Parametreler arasında boşluk olmaması çok önemlidir.)|Hiçbiri|
|Exchange|"Değişim;<br /><br /> MAPILEVEL= *folderpath*;<br /><br /> [TABLETYPE={ 0 &#124; 1 };]<br /><br /> [PROFILE= *profili*;]<br /><br /> [PWD= *şifre*;]<br /><br /> [DATABASE= `database`;]"|*"drive*\\\ :*yol*\\\ *dosya adı*. MDB"|

> [!NOTE]
> Btrieve artık DAO 3.5 olarak desteklenmez.

Bağlantı dizelerinde çift\\\\eğik çizgi ( ) kullanmanız gerekir. Varolan bir bağlantının özelliklerini kullanarak `SetConnect`değiştirdiyseniz, daha sonra [RefreshLink'i](#refreshlink)aramanız gerekir. Bağlantı özelliklerini kullanarak `SetConnect`başlatma yapıyorsanız, aramanız `RefreshLink`gerekmez, ancak bunu yapmayı seçerseniz, önce tabledef'i eklersiniz.

Parola gerekliyse ancak sağlanmadıysa, ODBC sürücüsü bir tabloya ilk erişici olduğunda ve bağlantı kapatıp yeniden açıldığında tekrar bir giriş iletişim kutusu görüntüler.

Üye işleviçin kaynak bağımsız `CDaoTableDef` değişken sağlayarak bir nesnenin `Create` bağlantı dizesini ayarlayabilirsiniz. Veritabanının türünü, yolunu, kullanıcı kimliğini, parolasını veya ODBC veri kaynağını belirlemek için ayarı denetleyebilirsiniz. Daha fazla bilgi için, belirli sürücü için belgelere bakın.

İlgili bilgiler için DAO Yardım'daki "Özelliği Bağla" konusuna bakın.

## <a name="cdaotabledefsetname"></a><a name="setname"></a>CDaoTableDef::SetName

Tablo için kullanıcı tanımlı bir ad ayarlamak için bu üye işlevini çağırın.

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Tablo için bir ad belirten bir dize ifadesiiçin işaretçi.

### <a name="remarks"></a>Açıklamalar

Ad bir harfle başlamalı ve en fazla 64 karakter içerebilir. Sayıları içerebilir ve karakterleri alt çizebilir, ancak noktalama işareti veya boşluk içeremez.

İlgili bilgiler için DAO Yardım'daki "Ad Özelliği" konusuna bakın.

## <a name="cdaotabledefsetsourcetablename"></a><a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName

Ekteki tablonun adını veya nesnenin temel tablosunun `CDaoTableDef` adını belirtmek için bu üye işlevi arayın, çünkü verilerin özgün kaynağında var.

```cpp
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>Parametreler

*lpszSrcTableName*<br/>
Dış veritabanında bir tablo adı belirten bir dize ifadesi için işaretçi. Bir taban tablo için ayar boş bir dize ("") dir.

### <a name="remarks"></a>Açıklamalar

Daha sonra [RefreshLink'i](#refreshlink)aramanız gerekir. Bu özellik ayarı bir taban tablo için boştur ve ekli bir tablo veya koleksiyona eklenmemiş bir nesne için okuma/yazma.

İlgili bilgiler için DAO Help'deki "SourceTableName Property" konusuna bakın.

## <a name="cdaotabledefsetvalidationrule"></a><a name="setvalidationrule"></a>CDaoTableDef::SetValidationRule

Bir tablo def için bir doğrulama kuralı ayarlamak için bu üye işlevi arayın.

```cpp
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>Parametreler

*lpszValidationKural*<br/>
Bir işlemi doğrulayan bir dize ifadesiiçin işaretçi.

### <a name="remarks"></a>Açıklamalar

Doğrulama kuralları güncelleştirme işlemleriyle bağlantılı olarak kullanılır. Bir tabledef bir doğrulama kuralı içeriyorsa, veriler değiştirilmeden önce bu tablodaki güncelleştirmelerin önceden belirlenmiş ölçütlere uyması gerekir. Değişiklik ölçütle eşleşmiyorsa, [GetValidationText](#getvalidationtext) metnini içeren bir özel durum görüntülenir.

Doğrulama yalnızca Microsoft Jet veritabanı altyapısını kullanan veritabanları için desteklenir. İfade, kullanıcı tanımlı işlevler, etki alanı toplama işlevleri, SQL toplama işlevleri veya sorgulara atıfta bulunamaz. Bir `CDaoTableDef` nesne için doğrulama kuralı, söz konusu nesnedeki birden çok alana başvurabilir.

Örneğin, *hire_date* ve *termination_date*adlı alanlar için bir doğrulama kuralı olabilir:

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

İlgili bilgiler için DAO Yardım'daki "Doğrulama Kuralı Özelliği" konusuna bakın.

## <a name="cdaotabledefsetvalidationtext"></a><a name="setvalidationtext"></a>CDaoTableDef::SetValidationMetin

Microsoft Jet veritabanı altyapısı tarafından desteklenen temel taban `CDaoTableDef` tablosu olan bir nesne için doğrulama kuralının özel durum metnini ayarlamak için bu üye işlevi arayın.

```cpp
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>Parametreler

*lpszValidationMetin*<br/>
Girilen veriler geçersizse görüntülenen metni belirten bir dize ifadesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ekli tablonun doğrulama metnini ayarlayamazsınız.

İlgili bilgiler için DAO Yardım'daki "DoğrulamaMetni Özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)
