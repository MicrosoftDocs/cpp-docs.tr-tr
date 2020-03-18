---
title: CDaoTableDef sınıfı
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
ms.openlocfilehash: 485fe3533916e5e59bc87084f58acfb37368ac32
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418764"
---
# <a name="cdaotabledef-class"></a>CDaoTableDef sınıfı

Bir temel tablonun veya eklenmiş tablonun saklı tanımını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoTableDef : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoTableDef:: CDaoTableDef](#cdaotabledef)|`CDaoTableDef` nesnesi oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoTableDef:: Append](#append)|Veritabanına yeni bir tablo ekler.|
|[CDaoTableDef:: CanUpdate](#canupdate)|Tablo güncelleştirilemeyebilir sıfır dışında bir değer döndürür (alanların tanımını veya tablo özelliklerini değiştirebilirsiniz).|
|[CDaoTableDef:: Close](#close)|Açık bir TableDef kapatır.|
|[CDaoTableDef:: Create](#create)|[Append](#append)kullanılarak veritabanına eklenebilen bir tablo oluşturur.|
|[CDaoTableDef:: CreateField](#createfield)|Tablo için alan oluşturmak üzere çağırılır.|
|[CDaoTableDef:: CreateIndex](#createindex)|Bir tablo için dizin oluşturmak üzere çağırılır.|
|[CDaoTableDef::D eleteField](#deletefield)|Tablodaki bir alanı silmek için çağırılır.|
|[CDaoTableDef::D Eleteındex](#deleteindex)|Tablodan bir dizini silmek için çağırılır.|
|[CDaoTableDef:: GetAttributes](#getattributes)|Bir `CDaoTableDef` nesnesinin bir veya daha fazla özelliğini gösteren bir değer döndürür.|
|[CDaoTableDef:: GetConnect](#getconnect)|Bir tablonun kaynağı hakkında bilgi sağlayan bir değer döndürür.|
|[CDaoTableDef:: GetDateCreated](#getdatecreated)|Temel tablonun bir `CDaoTableDef` nesnesinin oluşturulduğu tarih ve saati döndürür.|
|[CDaoTableDef:: GetDateLastUpdated](#getdatelastupdated)|Temel tablonun tasarımında yapılan en son değişikliğin tarih ve saatini döndürür.|
|[CDaoTableDef:: GetFieldCount](#getfieldcount)|Tablodaki alan sayısını temsil eden bir değer döndürür.|
|[CDaoTableDef:: GetFieldInfo](#getfieldinfo)|Tablodaki alanlarla ilgili belirli tür bilgileri döndürür.|
|[CDaoTableDef:: GetIndexCount](#getindexcount)|Tablo için dizinlerin sayısını döndürür.|
|[CDaoTableDef:: GetIndexInfo](#getindexinfo)|Tabloya yönelik dizinler hakkında belirli tür bilgileri döndürür.|
|[CDaoTableDef:: GetName](#getname)|Tablonun Kullanıcı tanımlı adını döndürür.|
|[CDaoTableDef:: GetRecordCount](#getrecordcount)|Tablodaki kayıt sayısını döndürür.|
|[CDaoTableDef:: GetSourceTableName](#getsourcetablename)|Kaynak veritabanında eklenmiş tablonun adını belirten bir değer döndürür.|
|[CDaoTableDef:: GetValidationRule](#getvalidationrule)|Bir alana değiştiği veya tabloya eklendiği için bir alandaki verileri doğrulayan bir değer döndürür.|
|[CDaoTableDef:: GetValidationText](#getvalidationtext)|Bir alan nesnesinin değeri belirtilen doğrulama kuralını karşılamadığı takdirde, uygulamanızın görüntüleyeceği iletinin metnini belirten bir değer döndürür.|
|[CDaoTableDef:: IsOpen](#isopen)|Tablo açıksa sıfır olmayan bir değer döndürür.|
|[CDaoTableDef:: Open](#open)|Veritabanının Tabledefın koleksiyonunda depolanan mevcut bir TableDef öğesini açar.|
|[CDaoTableDef:: RefreshLink](#refreshlink)|Ekli tablo için bağlantı bilgilerini güncelleştirir.|
|[CDaoTableDef:: SetAttributes](#setattributes)|Bir `CDaoTableDef` nesnesinin bir veya daha fazla özelliğini gösteren bir değer ayarlar.|
|[CDaoTableDef:: SetConnect](#setconnect)|Bir tablonun kaynağı hakkında bilgi sağlayan bir değer ayarlar.|
|[CDaoTableDef:: SetName](#setname)|Tablonun adını ayarlar.|
|[CDaoTableDef:: SetSourceTableName](#setsourcetablename)|Kaynak veritabanında eklenmiş bir tablonun adını belirten bir değer ayarlar.|
|[CDaoTableDef:: SetValidationRule](#setvalidationrule)|Bir alandaki verileri değiştirilmiş veya tabloya eklendiği için doğrulayan bir değeri ayarlar.|
|[CDaoTableDef:: SetValidationText](#setvalidationtext)|Bir alan nesnesinin değeri belirtilen doğrulama kuralını karşılamadığı takdirde, uygulamanızın görüntüleyeceği iletinin metnini belirten bir değer ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoTableDef:: m_pDAOTableDef](#m_pdaotabledef)|Tabledef nesnesini temel alan DAO arabirimine yönelik bir işaretçi.|
|[CDaoTableDef:: m_pDatabase](#m_pdatabase)|Bu tablo için kaynak veritabanı.|

## <a name="remarks"></a>Açıklamalar

Her DAO veritabanı nesnesi, tüm kaydedilmiş DAO TableDef nesnelerini içeren TableDefs adlı bir koleksiyon tutar.

Bir `CDaoTableDef` nesnesi kullanarak bir tablo tanımını işlersiniz. Örneğin, şunları yapabilirsiniz:

- Bir veritabanındaki herhangi bir yerel, ekli veya dış tablonun alanını ve dizin yapısını inceleyin.

- Eklenmiş tablolar için `SetConnect` ve `SetSourceTableName` üye işlevlerini çağırın ve ekli tabloların bağlantılarını güncelleştirmek için `RefreshLink` üye işlevini kullanın.

- Tablodaki alan tanımlarını düzenleyip düzenleyebiliyorsanız, bunu öğrenmek için `CanUpdate` üye işlevini çağırın.

- `GetValidationRule` ve `SetValidationRule`ve `GetValidationText` ve `SetValidationText` üye işlevlerini kullanarak doğrulama koşullarını alın veya ayarlayın.

- Tablo, dynaset veya anlık görüntü türü `CDaoRecordset` nesnesi oluşturmak için `Open` member işlevini kullanın.

    > [!NOTE]
    >  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adlarında "CDao" öneki vardır. ODBC veri kaynaklarına yine de DAO sınıfları ile erişebilirsiniz; DAO sınıfları, Microsoft Jet veritabanı altyapısına özgü olduklarından üstün yetenekler sunar.

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>TableDef nesnelerini, var olan bir tabloyla çalışmak ya da yeni bir tablo oluşturmak için kullanmak için

1. Her durumda, ilk olarak tablonun ait olduğu bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine bir işaretçi sağlayan bir `CDaoTableDef` nesnesi oluşturun.

1. Ardından, istediğiniz seçeneğe bağlı olarak aşağıdakileri yapın:

   - Varolan bir kaydedilmiş tabloyu kullanmak için, kayıt tablosunun adını sağlayarak TableDef nesnesinin [Open](#open) üye işlevini çağırın.

   - Yeni bir tablo oluşturmak için, tablo adını sağlayarak TableDef nesnesinin üye [Oluştur](#create) işlevini çağırın. Tabloya alanlar ve dizinler eklemek için [CreateField](#createfield) ve [CreateIndex](#createindex) ' i çağırın.

   - Tabloyu veritabanının TableDefs koleksiyonuna ekleyerek kaydetmek için [append](#append) çağrısı yapın. `Create`, TableDef 'i açık duruma geçirir, bu nedenle `Create` çağrıldıktan sonra `Open`çağırmayın.

        > [!TIP]
        >  Kaydedilmiş tabloları oluşturmanın en kolay yolu, bunları oluşturmak ve Microsoft Access 'i kullanarak veritabanınızda depolar. Bu durumda, MFC kodunuzda açabilir ve kullanabilirsiniz.

Açtığınız veya oluşturduğunuz TableDef nesnesini kullanmak için, *nOpenType* parametresinde bir `dbOpenTable` değeri ile TableDef adını belirterek bir `CDaoRecordset` nesnesi oluşturun ve açın.

Bir `CDaoRecordset` nesnesi oluşturmak için bir TableDef nesnesi kullanmak için, genellikle yukarıda açıklanan bir TableDef oluşturun veya açın, ardından bir kayıt kümesi nesnesi oluşturur ve bu, [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)' ı çağırdığınızda TableDef nesnesine bir işaretçi geçirerek bir işaretçi alır. Geçirdiğiniz tabledef açık durumda olmalıdır. Daha fazla bilgi için bkz. Class [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Bir TableDef nesnesi kullanmayı bitirdiğinizde, [Close](../../mfc/reference/cdaorecordset-class.md#close) üye işlevini çağırın; Sonra TableDef nesnesini yok edin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

##  <a name="append"></a>CDaoTableDef:: Append

TableDef 'i veritabanına kaydetmek üzere yeni bir TableDef nesnesi oluşturmak için [Oluştur](#create) ' a çağrı yaptıktan sonra bu üye işlevini çağırın.

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, nesneyi veritabanının TableDefs koleksiyonuna ekler. TableDef öğesini ekleyerek geçici bir nesne olarak kullanabilirsiniz, ancak onu kaydedip kullanmak istiyorsanız, `Append`çağırmanız gerekir.

> [!NOTE]
>  Adlandırılmamış bir TableDef (null veya boş dize içeren) eklemeye çalışırsanız, MFC bir özel durum oluşturur.

İlgili bilgiler için, DAO yardımı 'nda "ekleme yöntemi" konusuna bakın.

##  <a name="canupdate"></a>CDaoTableDef:: CanUpdate

`CDaoTableDef` nesnesini temel alan tablonun tanımının değiştirilip değiştirilemeyeceğini öğrenmek için bu üye işlevi çağırın.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo yapısı (şema) değiştirilemiyorsa (alanlar ve dizinler ekleyin veya silin), aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CDaoTableDef` nesnesini temel alan yeni oluşturulan bir tablo güncelleştirilebilecek ve bir `CDaoTableDef` nesnesini temel alan eklenmiş bir tablo güncelleştirilemez. Sonuç kümesi güncelleştirilebilir olmasa bile `CDaoTableDef` nesnesi güncelleştirilebilir.

İlgili bilgiler için, DAO yardımı 'nda "güncelleştirilebilir özellik" konusuna bakın.

##  <a name="cdaotabledef"></a>CDaoTableDef:: CDaoTableDef

`CDaoTableDef` nesnesi oluşturur.

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra [Create](#create) veya [Open](#open) member işlevini çağırmanız gerekir. Nesnesiyle bitirdiğinizde, [Close](#close) üye işlevini çağırmanız ve `CDaoTableDef` nesnesini yok etmeniz gerekir.

##  <a name="close"></a>CDaoTableDef:: Close

Tabledef nesnesini kapatmak ve serbest bırakmak için bu üye işlevi çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Genellikle `Close`çağrıldıktan sonra TableDef nesnesini **Yeni**ile ayrıldıysa silinir.

`Close`çağrıldıktan sonra tekrar [Aç](#open) ' a çağrı yapabilirsiniz. Bu, TableDef nesnesini yeniden kullanmanıza olanak sağlar.

İlgili bilgiler için, DAO yardımı 'nda "Yöntem kapatma" konusuna bakın.

##  <a name="create"></a>CDaoTableDef:: Create

Yeni bir kaydedilmiş tablo oluşturmak için bu üye işlevini çağırın.

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Tablonun adını içeren bir dize işaretçisi.

*lAttributes*<br/>
TableDef nesnesi tarafından temsil edilen tablonun özelliklerine karşılık gelen bir değer. Aşağıdaki sabitlerden herhangi birini birleştirmek için bit düzeyinde veya kullanabilirsiniz:

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, tablonun özel kullanım için açılmış bir eklenmiş tablo olduğunu gösterir.|
|`dbAttachSavePWD`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, ekli tablo için Kullanıcı KIMLIĞI ve parolanın bağlantı bilgileriyle kaydedildiğini belirtir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan gizli bir tablo olduğunu gösterir.|

*lpszSrcTable*<br/>
Kaynak tablo adını içeren bir dize işaretçisi. Varsayılan olarak bu değer, NULL olarak başlatılır.

*lpszConnect*<br/>
Varsayılan bağlantı dizesini içeren bir dize işaretçisi. Varsayılan olarak bu değer, NULL olarak başlatılır.

### <a name="remarks"></a>Açıklamalar

TableDef 'i adlandırdıktan sonra, TableDef ' [i çağırıp veritabanının](#append) TableDefs koleksiyonuna kaydedebilirsiniz. `Append`çağrıldıktan sonra, TableDef açık durumdadır ve bunu bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturmak için kullanabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "CreateTableDef yöntemi" konusuna bakın.

##  <a name="createfield"></a>CDaoTableDef:: CreateField

Tabloya bir alan eklemek için bu üye işlevini çağırın.

```
void CreateField(
    LPCTSTR lpszName,
    short nType,
    long lSize,
    long lAttributes = 0);

void CreateField(CDaoFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bu alanın adını belirten bir dize ifadesi işaretçisi.

*nTür*<br/>
Alanın veri türünü gösteren bir değer. Ayar şu değerlerden biri olabilir:

|Tür|Boyut (bayt)|Açıklama|
|----------|--------------------|-----------------|
|`dbBoolean`|1 bayt|BOOL|
|`dbByte`|BYTE|
|`dbInteger`|2|int|
|`dbLong`|4|long|
|`dbCurrency`|8|Para birimi ( [Copapara birimi](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|float|
|`dbDouble`|8|double|
|`dbDate`|8|Tarih/saat ( [Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Metin ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long Binary (OLE nesnesi), [CLongBinary](../../mfc/reference/clongbinary-class.md) veya [CByteArray](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|Memo ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|

*lSize dili*<br/>
Metin içeren bir alanın en büyük boyutunu bayt cinsinden veya metin veya sayısal değerler içeren bir alanın sabit boyutunu belirten bir değer. Tüm metin alanları için *lSize* parametresi yok sayılır.

*lAttributes*<br/>
Alanın özelliklerine karşılık gelen ve bit düzeyinde OR kullanılarak birleştirilebilen bir değer.

|Sabit|Açıklama|
|--------------|-----------------|
|`dbFixedField`|Alan boyutu sabittir (sayısal alanlar için varsayılan).|
|`dbVariableField`|Alan boyutu değişken (yalnızca metin alanları).|
|`dbAutoIncrField`|Yeni kayıtlar için alan değeri, değiştirilemeyen benzersiz bir uzun tamsayıya otomatik olarak artırılır. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.|
|`dbUpdatableField`|Alan değeri değiştirilebilir.|
|`dbDescending`|Alan azalan (Z-A veya 100-0) düzende sıralanır (yalnızca bir dizin nesnesinin Fields koleksiyonundaki Field nesnesi için geçerlidir). Bu sabiti atlarsanız, alan artan (A-Z veya 0-100) bir düzende sıralanır (varsayılan).|

*sağlanırken*<br/>
[Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Bir `DAOField` (OLE) nesnesi oluşturulur ve `DAOTableDef` (OLE) nesnesinin alanlar koleksiyonuna eklenir. Nesne özelliklerini incelemek için kullanmanın yanı sıra, bir TableDef içinde yeni alanlar oluşturmak için bir giriş parametresi oluşturmak üzere `CDaoFieldInfo` de kullanabilirsiniz. `CreateField` ilk sürümü kullanımı basittir, ancak daha hassas bir denetim istiyorsanız, bir `CDaoFieldInfo` parametresi alan `CreateField`ikinci sürümünü kullanabilirsiniz.

Bir `CDaoFieldInfo` parametresi alan `CreateField` sürümünü kullanıyorsanız, `CDaoFieldInfo` yapısının aşağıdaki üyelerinin her birini dikkatle ayarlamanız gerekir:

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

`CDaoFieldInfo` kalan üyeleri, üyeye uygun şekilde **0**, false veya boş bir dize olarak ayarlanmalıdır ya da bir `CDaoException` olabilir.

İlgili bilgiler için, DAO yardımı 'nda "CreateField yöntemi" konusuna bakın.

##  <a name="createindex"></a>CDaoTableDef:: CreateIndex

Tabloya bir dizin eklemek için bu işlevi çağırın.

```
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>Parametreler

*ındexınfo*<br/>
Bir [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Dizinler, veritabanı tablolarından erişilen kayıt sırasını ve yinelenen kayıtların kabul edilip edilmeyeceğini belirtir. Dizinler ayrıca verilere verimli erişim sağlar.

Tablolar için dizin oluşturmanız gerekmez, ancak büyük, dizine alınmamış tablolarda, belirli bir kayda erişmek veya bir kayıt kümesi oluşturmak uzun sürebilir. Öte yandan, çok sayıda dizin oluşturmak güncelleştirme, ekleme ve silme işlemlerini yavaşlattığından tüm dizinler otomatik olarak güncelleştirilir. Hangi dizinlerin oluşturulacağı konusunda karar verirken bu faktörleri göz önünde bulundurun.

`CDaoIndexInfo` yapısının aşağıdaki üyeleri ayarlanmalıdır:

- `m_strName` bir ad sağlanmalıdır.

- `m_pFieldInfos`, bir `CDaoIndexFieldInfo` yapıları dizisine işaret etmelidir.

- `m_nFields`, `CDaoFieldInfo` yapıları dizisindeki alan sayısını belirtmelidir.

Kalan Üyeler FALSE olarak ayarlandıysa yok sayılır. Ayrıca, dizin oluşturma sırasında `m_lDistinctCount` üye yok sayılır.

##  <a name="deletefield"></a>CDaoTableDef::D eleteField

Bir alanı kaldırmak ve erişilebilir hale getirmek için bu üye işlevini çağırın.

```
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Varolan bir alanın adı olan bir dize ifadesinin işaretçisi.

*nDizin*<br/>
Dizine göre arama için tablonun sıfır tabanlı alanlar koleksiyonundaki alanının dizini.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini veritabanına eklenmemiş yeni bir nesne üzerinde veya [CanUpdate](#canupdate) , sıfır dışında bir değer döndürdüğünde kullanabilirsiniz.

İlgili bilgiler için, DAO yardımında "Yöntem silme" konusuna bakın.

##  <a name="deleteindex"></a>CDaoTableDef::D Eleteındex

Temel tablodaki bir dizini silmek için bu üye işlevini çağırın.

```
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Varolan bir dizinin adı olan bir dize ifadesinin işaretçisi.

*nDizin*<br/>
Dizine göre arama için veritabanının sıfır tabanlı TableDefs koleksiyonundaki dizin nesnesinin dizi dizini.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini veritabanına eklenmemiş yeni bir nesne üzerinde veya [CanUpdate](#canupdate) , sıfır dışında bir değer döndürdüğünde kullanabilirsiniz.

İlgili bilgiler için, DAO yardımında "Yöntem silme" konusuna bakın.

##  <a name="getattributes"></a>CDaoTableDef:: GetAttributes

`CDaoTableDef` nesnesi için, dönüş değeri, `CDaoTableDef` nesnesi tarafından temsil edilen tablonun özelliklerini belirtir ve bu sabitlerin toplamı olabilir:

```
long GetAttributes();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CDaoTableDef` nesnesinin bir veya daha fazla özelliğini gösteren bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, tablonun özel kullanım için açılmış bir eklenmiş tablo olduğunu gösterir.|
|`dbAttachSavePWD`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, ekli tablo için Kullanıcı KIMLIĞI ve parolanın bağlantı bilgileriyle kaydedildiğini belirtir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan gizli bir tablo olduğunu gösterir.|
|`dbAttachedTable`|Tablonun, Paradox veritabanı gibi ODBC olmayan bir veritabanından ekli tablo olduğunu gösterir.|
|`dbAttachedODBC`|Tablonun, Microsoft SQL Server gibi bir ODBC veritabanından ekli tablo olduğunu gösterir.|

Bir sistem tablosu, çeşitli iç bilgileri içerecek şekilde Microsoft Jet veritabanı altyapısı tarafından oluşturulan bir tablodur.

Gizli tablo, Microsoft Jet veritabanı altyapısı tarafından geçici kullanım için oluşturulan bir tablodur.

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

##  <a name="getconnect"></a>CDaoTableDef:: GetConnect

Bir veri kaynağı için bağlantı dizesi almak üzere bu üye işlevini çağırın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

Tablonun yolunu ve veritabanı türünü içeren `CString` nesnesi.

### <a name="remarks"></a>Açıklamalar

Eklenmiş bir tabloyu temsil eden bir `CDaoTableDef` nesnesi için, `CString` nesnesi bir veya iki bölümden oluşur (bir veritabanı türü belirticisi ve veritabanının yolu).

Aşağıdaki tabloda gösterildiği gibi yol, veritabanı dosyalarını içeren dizinin tam yoludur ve öncesinde "DATABASE =" tanımlayıcısı gelmelidir. Bazı durumlarda (Microsoft Jet ve Microsoft Excel veritabanlarında olduğu gibi), veritabanı yolu bağımsız değişkenine belirli bir dosya adı eklenir.

[CDaoTableDef:: SetConnect](#setconnect) içindeki tablo olası veritabanı türlerini ve bunlara karşılık gelen veritabanı belirticilerini ve yollarını gösterir:

Microsoft Jet veritabanı temel tabloları için, belirtici boş bir dizedir ("").

Bir parola gerekliyse ancak sağlanmazsa, ODBC sürücüsü bir tabloya ilk kez erişildiğinde bir oturum açma iletişim kutusu görüntüler ve bağlantı kapatılıp yeniden açılabilir. Eklenmiş bir tabloda `dbAttachSavePWD` özniteliği varsa, tablo yeniden açıldığında oturum açma istemi görünmez.

İlgili bilgiler için, DAO yardımı 'nda "bağlama özelliği" konusuna bakın.

##  <a name="getdatecreated"></a>CDaoTableDef:: GetDateCreated

`CDaoTableDef` nesnesinin temel aldığı tablonun tarihini ve saatini öğrenmek için bu işlevi çağırın.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoTableDef` nesnesini temel alan tablonun oluşturulma tarihini ve saatini içeren bir değer.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablonun oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, kullanıcıların tutarsızlıkları önlemek için bu ayarları doğrudan dosya sunucusundan alması gerekir; diğer bir deyişle, tüm istemciler belki de bir sunucudan "standart" bir zaman kaynağı kullanmalıdır.

İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

##  <a name="getdatelastupdated"></a>CDaoTableDef:: GetDateLastUpdated

`CDaoTableDef` nesnesinin temel aldığı tablonun son güncelleştirilme tarihini ve saatini öğrenmek için bu işlevi çağırın.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoTableDef` nesnesinin temelindeki tablonun son güncelleştirildiği tarih ve saati içeren bir değer.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablonun oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, kullanıcıların tutarsızlıkları önlemek için bu ayarları doğrudan dosya sunucusundan alması gerekir; diğer bir deyişle, tüm istemciler belki de bir sunucudan "standart" bir zaman kaynağı kullanmalıdır.

İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

##  <a name="getfieldcount"></a>CDaoTableDef:: GetFieldCount

Tabloda tanımlanan alan sayısını almak için bu üye işlevi çağırın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablodaki alan sayısı.

### <a name="remarks"></a>Açıklamalar

Değeri 0 ise, koleksiyonda nesne yoktur.

İlgili bilgiler için, DAO yardımı 'nda "Count Property" konusuna bakın.

##  <a name="getfieldinfo"></a>CDaoTableDef:: GetFieldInfo

TableDef içinde tanımlı bir alanla ilgili çeşitli bilgi türlerini almak için bu üye işlevi çağırın.

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
Dizine göre arama için tablonun sıfır tabanlı alanlar koleksiyonundaki alan nesnesinin dizini.

*sağlanırken*<br/>
[Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına başvuru.

*dwInfoOptions*<br/>
Alınacak alanla ilgili hangi bilgilerin alındığını belirleyen seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte aşağıda listelenmiştir:

- `AFX_DAO_PRIMARY_INFO` (varsayılan) ad, tür, boyut, öznitelik. En hızlı performans için bu seçeneği kullanın.

- Birincil bilgileri `AFX_DAO_SECONDARY_INFO`, ayrıca: sıralı konum, gerekli, sıfır uzunluğa Izin ver, harmanlama sırası, yabancı ad, kaynak alanı, kaynak tablo

- Birincil ve ikincil bilgileri `AFX_DAO_ALL_INFO`, ayrıca: doğrulama kuralı, doğrulama metni, varsayılan değer

*lpszName*<br/>
Ada göre arama için alan nesnesinin adına yönelik bir işaretçi. Ad, alanı benzersiz şekilde adlandıran en fazla 64 karakter içeren bir dizedir.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü bir alanı dizine göre arama yapmanızı sağlar. Diğer sürüm, bir alanı adına göre arama yapmanızı sağlar.

Döndürülen bilgilerin açıklaması için bkz. [Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bu yapının, *Dwinfooptions*açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki tüm düzeyler için de bilgi alırsınız.

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

##  <a name="getindexcount"></a>CDaoTableDef:: GetIndexCount

Bir tablo için dizin sayısını almak üzere bu üye işlevini çağırın.

```
short GetIndexCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo için dizin sayısı.

### <a name="remarks"></a>Açıklamalar

Değeri 0 ise, koleksiyonda dizin yoktur.

İlgili bilgiler için, DAO yardımı 'nda "Count Property" konusuna bakın.

##  <a name="getindexinfo"></a>CDaoTableDef:: GetIndexInfo

TableDef içinde tanımlı bir dizin hakkında çeşitli bilgiler almak için bu üye işlevi çağırın.

```
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

*nDizin*<br/>
Koleksiyondaki konumuna göre arama için tablonun sıfır tabanlı dizinler koleksiyonundaki dizin nesnesinin sayısal dizini.

*ındexınfo*<br/>
Bir [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına başvuru.

*dwInfoOptions*<br/>
Alınacak dizin hakkındaki bilgileri belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte aşağıda listelenmiştir:

- `AFX_DAO_PRIMARY_INFO` adı, alan bilgileri, alanlar. En hızlı performans için bu seçeneği kullanın.

- Birincil bilgileri `AFX_DAO_SECONDARY_INFO`, ek olarak: birincil, benzersiz, kümelenmiş, Yoksay null, gerekli, yabancı

- Birincil ve ikincil bilgileri `AFX_DAO_ALL_INFO`, ayrıca: ayrı sayım

*lpszName*<br/>
Ada göre arama için dizin nesnesinin adına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, koleksiyondaki konumuyla bir dizin araması yapmanızı sağlar. Diğer sürüm, dizin adına göre arama yapmanızı sağlar.

Döndürülen bilgilerin açıklaması için, [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions*açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki tüm düzeyler için de bilgi alırsınız.

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

##  <a name="getname"></a>CDaoTableDef:: GetName

Temel alınan tablonun Kullanıcı tanımlı adını almak için bu üye işlevi çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo için Kullanıcı tanımlı bir ad.

### <a name="remarks"></a>Açıklamalar

Bu ad, bir harfle başlar ve en fazla 64 karakter içerebilir. Sayılar ve alt çizgi karakterlerini içerebilir, ancak noktalama veya boşluk içeremez.

İlgili bilgiler için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

##  <a name="getrecordcount"></a>CDaoTableDef:: GetRecordCount

`CDaoTableDef` nesnesinde kaç kayıt olduğunu öğrenmek için bu üye işlevi çağırın.

```
long GetRecordCount();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tabledef nesnesinde erişilen kayıt sayısı.

### <a name="remarks"></a>Açıklamalar

Tablo türü `CDaoTableDef` nesnesi için `GetRecordCount` çağırmak, tablodaki yaklaşık kayıt sayısını yansıtır ve tablo kayıtları eklenip silindiğine hemen etkilenir. Geri alınmış işlemler, [CDaoWorkspace:: CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)öğesini çağırana kadar kayıt sayısının bir parçası olarak görüntülenir. Kayıtları olmayan bir `CDaoTableDef` nesnesi, 0 kayıt sayısı özelliği ayarına sahiptir. Eklenmiş tablolar veya ODBC veritabanları ile çalışırken `GetRecordCount` her zaman-1 döndürür.

İlgili bilgiler için, DAO yardımı 'nda "RecordCount özelliği" konusuna bakın.

##  <a name="getsourcetablename"></a>CDaoTableDef:: GetSourceTableName

Bir kaynak veritabanında eklenmiş bir tablonun adını almak için bu üye işlevini çağırın.

```
CString GetSourceTableName();
```

### <a name="return-value"></a>Dönüş Değeri

Eklenmiş bir tablonun kaynak adını veya yerel veri tablosu ise boş bir dizeyi belirten `CString` nesne.

### <a name="remarks"></a>Açıklamalar

Ekli tablo, bir Microsoft Jet veritabanıyla bağlantılı başka bir veritabanındaki tablodur. Ekli tablo verileri, diğer uygulamalar tarafından işlenebileceği dış veritabanında kalır.

İlgili bilgiler için, DAO yardımı 'nda "SourceTableName özelliği" konusuna bakın.

##  <a name="getvalidationrule"></a>CDaoTableDef:: GetValidationRule

Bir TableDef için doğrulama kuralını almak üzere bu üye işlevi çağırın.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen veya tabloya eklenen bir alandaki verileri doğrulayan `CString` nesne.

### <a name="remarks"></a>Açıklamalar

Doğrulama kuralları, güncelleştirme işlemleriyle bağlantılı olarak kullanılır. Bir TableDef bir doğrulama kuralı içeriyorsa, veri değiştirilmeden önce bu TableDef güncelleştirmelerinin önceden belirlenmiş ölçütlerle eşleşmesi gerekir. Değişiklik ölçütlere eşleşmezse [GetValidationText](#getvalidationtext) değerini içeren bir özel durum oluşturulur. `CDaoTableDef` nesnesi için, bu `CString`, ekli tablo için salt okunurdur ve temel tablo için okuma/yazma işlemi yapılır.

İlgili bilgiler için, DAO yardımı 'nda "ValidationRule özelliği" konusuna bakın.

##  <a name="getvalidationtext"></a>CDaoTableDef:: GetValidationText

Kullanıcı doğrulama kuralıyla eşleşmeyen verileri girdiğinde görüntülenecek dizeyi almak için bu işlevi çağırın.

```
CString GetValidationText();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı doğrulama kuralıyla eşleşmeyen verileri girerse görüntülenen metni belirten `CString` nesne.

### <a name="remarks"></a>Açıklamalar

`CDaoTableDef` nesnesi için, bu `CString`, ekli tablo için salt okunurdur ve temel tablo için okuma/yazma işlemi yapılır.

İlgili bilgiler için, DAO yardımı 'nda "ValidationText özelliği" konusuna bakın.

##  <a name="isopen"></a>CDaoTableDef:: IsOpen

`CDaoTableDef` nesnesinin açık olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoTableDef` nesnesi açıksa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_pdatabase"></a>CDaoTableDef:: m_pDatabase

Bu tablo için [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine bir işaretçi içeriyor.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_pdaotabledef"></a>CDaoTableDef:: m_pDAOTableDef

`CDaoTableDef` nesnesini temel alan DAO TableDef nesnesi için OLE arabirimine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

DAO arabirimine doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.

##  <a name="open"></a>CDaoTableDef:: Open

Daha önce veritabanının Tabledefın koleksiyonunda kayıtlı olan bir TableDef açmak için bu üye işlevini çağırın.

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bir tablo adı belirten bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="refreshlink"></a>CDaoTableDef:: RefreshLink

Ekli bir tablonun bağlantı bilgilerini güncelleştirmek için bu üye işlevi çağırın.

```
void RefreshLink();
```

### <a name="remarks"></a>Açıklamalar

Ekli bir tablo için bağlantı bilgilerini, karşılık gelen `CDaoTableDef` nesnesinde [SetConnect](#setconnect) 'i çağırarak ve sonra bilgileri güncelleştirmek için `RefreshLink` member işlevini kullanarak değiştirirsiniz. `RefreshLink`çağırdığınızda, eklenen tablonun özellikleri değiştirilmez.

Değiştirilen bağlantı bilgilerinin etkili olmasını zorlamak için, bu TableDef 'e dayalı tüm açık [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnelerinin kapatılması gerekir.

İlgili bilgiler için, DAO yardımı 'nda "RefreshLink method" konusuna bakın.

##  <a name="setattributes"></a>CDaoTableDef:: SetAttributes

Bir `CDaoTableDef` nesnesinin bir veya daha fazla özelliğini gösteren bir değer ayarlar.

```
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>Parametreler

*lAttributes*<br/>
`CDaoTableDef` nesnesi tarafından temsil edilen tablonun özellikleri ve bu sabitlerin toplamı olabilir:

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, tablonun özel kullanım için açılmış bir eklenmiş tablo olduğunu gösterir.|
|`dbAttachSavePWD`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, ekli tablo için Kullanıcı KIMLIĞI ve parolanın bağlantı bilgileriyle kaydedildiğini belirtir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan gizli bir tablo olduğunu gösterir.|

### <a name="remarks"></a>Açıklamalar

Birden çok öznitelik ayarlarken, bit düzeyinde OR işlecini kullanarak uygun sabitleri toplayarak bunları birleştirebilirsiniz. Eklenmemiş bir tabloda `dbAttachExclusive` ayarlama işlemi özel durum oluşturur. Aşağıdaki değerleri birleştirmek özel bir durum da üretir:

- **dbAttachExclusive &#124; dbattachedodbc**

- **dbAttachSavePWD &#124; dbAttachedTable**

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

##  <a name="setconnect"></a>CDaoTableDef:: SetConnect

Eklenmiş bir tabloyu temsil eden bir `CDaoTableDef` nesnesi için, dize nesnesi bir veya iki bölümden oluşur (bir veritabanı türü belirticisi ve veritabanının yolu).

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Parametreler

*lpszConnect*<br/>
ODBC veya yüklenebilir ISAM sürücülerine geçirilecek ek parametreleri belirten bir dize ifadesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda gösterildiği gibi yol, veritabanı dosyalarını içeren dizinin tam yoludur ve öncesinde "DATABASE =" tanımlayıcısı gelmelidir. Bazı durumlarda (Microsoft Jet ve Microsoft Excel veritabanlarında olduğu gibi), veritabanı yolu bağımsız değişkenine belirli bir dosya adı eklenir.

> [!NOTE]
>  "DATABASE = Drive:\\\path" biçimindeki eşittir oturum açma yolu deyimlerinin etrafına boşluk eklemeyin. Bu, bir özel durumun oluşmasına ve bağlantının başarısız olmasına neden olur.

Aşağıdaki tabloda, olası veritabanı türleri ve bunlara karşılık gelen veritabanı belirticileri ve yolları gösterilmektedir:

|Veritabanı türü|Belirleyici|Yol|
|-------------------|---------------|----------|
|Jet veritabanı altyapısını kullanan veritabanı|"[`database`];"|"`drive`:\\\ *yol*\\\ *filename*. TATIL|
|dBASE III|"dBASE III;"|"`drive`:\\\ *yolu*"|
|dBASE IV|"dBASE IV;"|"`drive`:\\\ *yolu*"|
|dBASE 5|"dBASE 5,0;"|"`drive`:\\\ *yolu*"|
|Paradox 3. x|"Paradox 3. x;"|"`drive`:\\\ *yolu*"|
|Paradox 4. x|"Paradox 4. x;"|"`drive`:\\\ *yolu*"|
|Paradox 5. x|"Paradox 5. x;"|"`drive`:\\\ *yolu*"|
|Excel 3,0|"Excel 3,0;"|"`drive`:\\\ *yol*\\\ *filename*. XLS|
|Excel 4,0|"Excel 4,0;"|"`drive`:\\\ *yol*\\\ *filename*. XLS|
|Excel 5,0 veya Excel 95|"Excel 5,0;"|"`drive`:\\\ *yol*\\\ *filename*. XLS|
|Excel 97|"Excel 8,0;"|"`drive`:\\\ *yol*\ *filename*. XLS|
|HTML Içeri aktarma|"HTML Içeri aktarma;"|"`drive`:\\\ *yol*\ *filename*"|
|HTML dışarı aktarma|"HTML dışarı aktarma;"|"`drive`:\\\ *yolu*"|
|Metin|"Metin;"|"sürücü:\\\Yol"|
|ODBC|ISTI VERITABANı = `database`; UID = *User*; PWD = *parola*; DSN = *DataSourceName;* LOGINTIMEOUT = *saniye;* " (Bu, tüm sunucular için tam bir bağlantı dizesi olmayabilir; yalnızca bir örnektir. Parametreler arasında boşluk olmaması çok önemlidir.)|Yok|
|Exchange|Değişimi<br /><br /> MAPILELEVEL = *FolderPath*;<br /><br /> [TABLETYPE = {0 &#124; 1};]<br /><br /> [PROFILE = *profile*;]<br /><br /> [PWD = *Password*;]<br /><br /> [VERITABANı = `database`;] "|*"sürücü*:\\\ *yol*\\\ *dosya adı*. TATIL|

> [!NOTE]
>  Btrieve, DAO 3,5 itibariyle artık desteklenmiyor.

Bağlantı dizelerinde çift ters eğik çizgi (\\\\) kullanmanız gerekir. `SetConnect`kullanarak mevcut bir bağlantının özelliklerini değiştirdiyseniz, daha sonra [RefreshLink](#refreshlink)çağrısı yapmanız gerekir. `SetConnect`kullanarak bağlantı özelliklerini başlatdıysanız, `RefreshLink`çağırmamalıdır, ancak bunu yapmanız gerekir, önce TableDef 'i ekleyin.

Bir parola gerekliyse ancak sağlanmazsa, ODBC sürücüsü bir tabloya ilk kez erişildiğinde bir oturum açma iletişim kutusu görüntüler ve bağlantı kapatılıp yeniden açılabilir.

`Create` üye işlevine bir kaynak bağımsız değişkeni sağlayarak bir `CDaoTableDef` nesnesi için bağlantı dizesi ayarlayabilirsiniz. Bu ayarı, veritabanının türünü, yolunu, kullanıcı KIMLIĞINI, parolasını veya ODBC veri kaynağını tespit etmek için denetleyebilirsiniz. Daha fazla bilgi için, belirli sürücü için belgelere bakın.

İlgili bilgiler için, DAO yardımı 'nda "bağlama özelliği" konusuna bakın.

##  <a name="setname"></a>CDaoTableDef:: SetName

Bir tablo için Kullanıcı tanımlı bir ad ayarlamak üzere bu üye işlevini çağırın.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bir tablo için ad belirten bir dize ifadesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ad bir harfle başlamalı ve en fazla 64 karakter içerebilir. Sayılar ve alt çizgi karakterlerini içerebilir, ancak noktalama veya boşluk içeremez.

İlgili bilgiler için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

##  <a name="setsourcetablename"></a>CDaoTableDef:: SetSourceTableName

Eklenen bir tablonun adını veya `CDaoTableDef` nesnesinin temel aldığı temel tablonun adını belirtmek için bu üye işlevi çağırın, çünkü verilerin özgün kaynağında bulunur.

```
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>Parametreler

*lpszSrcTableName*<br/>
Dış veritabanında tablo adı belirten bir dize ifadesi işaretçisi. Temel tablo için, ayar boş bir dizedir ("").

### <a name="remarks"></a>Açıklamalar

Ardından [RefreshLink](#refreshlink)çağrısı yapmanız gerekir. Bu özellik ayarı bir temel tablo için boştur ve ekli tablo veya bir koleksiyona eklenmemiş bir nesne için okuma/yazma işlemi.

İlgili bilgiler için, DAO yardımı 'nda "SourceTableName özelliği" konusuna bakın.

##  <a name="setvalidationrule"></a>CDaoTableDef:: SetValidationRule

Bir TableDef için doğrulama kuralı ayarlamak için bu üye işlevi çağırın.

```
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>Parametreler

*lpszValidationRule*<br/>
Bir işlemi doğrulayan dize ifadesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Doğrulama kuralları, güncelleştirme işlemleriyle bağlantılı olarak kullanılır. Bir TableDef bir doğrulama kuralı içeriyorsa, veri değiştirilmeden önce bu TableDef güncelleştirmelerinin önceden belirlenmiş ölçütlerle eşleşmesi gerekir. Değişiklik ölçütlere eşleşmezse [GetValidationText](#getvalidationtext) metnini içeren bir özel durum görüntülenir.

Doğrulama yalnızca Microsoft Jet veritabanı altyapısını kullanan veritabanları için desteklenir. İfade Kullanıcı tanımlı işlevlere, etki alanı toplama işlevlerine, SQL toplama işlevlerine veya sorgulara başvuramaz. Bir `CDaoTableDef` nesnesi için bir doğrulama kuralı, bu nesnedeki birden çok alana başvurabilir.

Örneğin, *hire_date* ve *termination_date*adlı alanlar için, bir doğrulama kuralı şu olabilir:

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

İlgili bilgiler için, DAO yardımı 'nda "ValidationRule özelliği" konusuna bakın.

##  <a name="setvalidationtext"></a>CDaoTableDef:: SetValidationText

Microsoft Jet veritabanı altyapısı tarafından desteklenen temel bir temel tabloyla bir `CDaoTableDef` nesnesi için bir doğrulama kuralının özel durum metnini ayarlamak için bu üye işlevi çağırın.

```
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>Parametreler

*lpszValidationText*<br/>
Girilen veriler geçersizse görüntülenen metni belirten bir dize ifadesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Eklenmiş bir tablonun doğrulama metnini ayarlayamazsınız.

İlgili bilgiler için, DAO yardımı 'nda "ValidationText özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)
