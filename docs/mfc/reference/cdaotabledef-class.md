---
description: 'Daha fazla bilgi edinin: CDaoTableDef sınıfı'
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
ms.openlocfilehash: ead41d1dae2d248324809690e778e8f623a73caf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248027"
---
# <a name="cdaotabledef-class"></a>CDaoTableDef sınıfı

Bir temel tablonun veya eklenmiş tablonun saklı tanımını temsil eder.

## <a name="syntax"></a>Syntax

```
class CDaoTableDef : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoTableDef:: CDaoTableDef](#cdaotabledef)|Bir `CDaoTableDef` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoTableDef:: Append](#append)|Veritabanına yeni bir tablo ekler.|
|[CDaoTableDef:: CanUpdate](#canupdate)|Tablo güncelleştirilemeyebilir sıfır dışında bir değer döndürür (alanların tanımını veya tablo özelliklerini değiştirebilirsiniz).|
|[CDaoTableDef:: Close](#close)|Açık bir TableDef kapatır.|
|[CDaoTableDef:: Create](#create)|[Append](#append)kullanılarak veritabanına eklenebilen bir tablo oluşturur.|
|[CDaoTableDef:: CreateField](#createfield)|Tablo için alan oluşturmak üzere çağırılır.|
|[CDaoTableDef:: CreateIndex](#createindex)|Bir tablo için dizin oluşturmak üzere çağırılır.|
|[CDaoTableDef::D eleteField](#deletefield)|Tablodaki bir alanı silmek için çağırılır.|
|[CDaoTableDef::D Eleteındex](#deleteindex)|Tablodan bir dizini silmek için çağırılır.|
|[CDaoTableDef:: GetAttributes](#getattributes)|Bir nesnenin bir veya daha fazla özelliğini gösteren bir değer döndürür `CDaoTableDef` .|
|[CDaoTableDef:: GetConnect](#getconnect)|Bir tablonun kaynağı hakkında bilgi sağlayan bir değer döndürür.|
|[CDaoTableDef:: GetDateCreated](#getdatecreated)|Temel tablonun bir nesnenin oluşturulduğu tarih ve saati döndürür `CDaoTableDef` .|
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
|[CDaoTableDef:: SetAttributes](#setattributes)|Bir nesnenin bir veya daha fazla özelliğini gösteren bir değer ayarlar `CDaoTableDef` .|
|[CDaoTableDef:: SetConnect](#setconnect)|Bir tablonun kaynağı hakkında bilgi sağlayan bir değer ayarlar.|
|[CDaoTableDef:: SetName](#setname)|Tablonun adını ayarlar.|
|[CDaoTableDef:: SetSourceTableName](#setsourcetablename)|Kaynak veritabanında eklenmiş bir tablonun adını belirten bir değer ayarlar.|
|[CDaoTableDef:: SetValidationRule](#setvalidationrule)|Bir alandaki verileri değiştirilmiş veya tabloya eklendiği için doğrulayan bir değeri ayarlar.|
|[CDaoTableDef:: SetValidationText](#setvalidationtext)|Bir alan nesnesinin değeri belirtilen doğrulama kuralını karşılamadığı takdirde, uygulamanızın görüntüleyeceği iletinin metnini belirten bir değer ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoTableDef:: m_pDAOTableDef](#m_pdaotabledef)|Tabledef nesnesini temel alan DAO arabirimine yönelik bir işaretçi.|
|[CDaoTableDef:: m_pDatabase](#m_pdatabase)|Bu tablo için kaynak veritabanı.|

## <a name="remarks"></a>Açıklamalar

Her DAO veritabanı nesnesi, tüm kaydedilmiş DAO TableDef nesnelerini içeren TableDefs adlı bir koleksiyon tutar.

Bir nesne kullanarak bir tablo tanımını işlersiniz `CDaoTableDef` . Örneğin, şunları yapabilirsiniz:

- Bir veritabanındaki herhangi bir yerel, ekli veya dış tablonun alanını ve dizin yapısını inceleyin.

- `SetConnect` `SetSourceTableName` Eklenmiş tablolar için ve üye işlevlerini çağırın ve `RefreshLink` ekli tablolardaki bağlantıları güncelleştirmek için üye işlevini kullanın.

- `CanUpdate`Tablodaki alan tanımlarını düzenleyip düzenleyebiliyorsanız, öğesini öğrenmek için üye işlevini çağırın.

- `GetValidationRule`Ve ve `SetValidationRule` `GetValidationText` `SetValidationText` üye işlevlerini kullanarak doğrulama koşullarını alın veya ayarlayın.

- `Open`Tablo, dynaset veya anlık görüntü türünde bir nesne oluşturmak için üye işlevini kullanın `CDaoRecordset` .

    > [!NOTE]
    >  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adlarında "CDao" öneki vardır. ODBC veri kaynaklarına yine de DAO sınıfları ile erişebilirsiniz; DAO sınıfları, Microsoft Jet veritabanı altyapısına özgü olduklarından üstün yetenekler sunar.

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>TableDef nesnelerini, var olan bir tabloyla çalışmak ya da yeni bir tablo oluşturmak için kullanmak için

1. Her durumda, ilk olarak `CDaoTableDef` tablonun ait olduğu bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine bir işaretçi sağlayan bir nesne oluşturun.

1. Ardından, istediğiniz seçeneğe bağlı olarak aşağıdakileri yapın:

   - Varolan bir kaydedilmiş tabloyu kullanmak için, kayıt tablosunun adını sağlayarak TableDef nesnesinin [Open](#open) üye işlevini çağırın.

   - Yeni bir tablo oluşturmak için, tablo adını sağlayarak TableDef nesnesinin üye [Oluştur](#create) işlevini çağırın. Tabloya alanlar ve dizinler eklemek için [CreateField](#createfield) ve [CreateIndex](#createindex) ' i çağırın.

   - Tabloyu veritabanının TableDefs koleksiyonuna ekleyerek kaydetmek için [append](#append) çağrısı yapın. `Create` TableDef 'i açık bir duruma getirir, bu nedenle çağrı yapıldıktan sonra `Create` çağırmayın `Open` .

        > [!TIP]
        >  Kaydedilmiş tabloları oluşturmanın en kolay yolu, bunları oluşturmak ve Microsoft Access 'i kullanarak veritabanınızda depolar. Bu durumda, MFC kodunuzda açabilir ve kullanabilirsiniz.

Açtığınız veya oluşturduğunuz TableDef nesnesini kullanmak için, `CDaoRecordset` `dbOpenTable` *nOpenType* parametresinde bir değer ile TableDef adını belirterek bir nesne oluşturun ve açın.

Bir nesne oluşturmak için bir TableDef nesnesi kullanmak için `CDaoRecordset` , genellikle yukarıda açıklanan şekilde bir TableDef oluşturun veya açın, ardından bir kayıt kümesi nesnesi oluşturur ve bu, [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open)' ı çağırdığınızda TableDef nesnesine bir işaretçi geçirmektir. Geçirdiğiniz tabledef açık durumda olmalıdır. Daha fazla bilgi için bkz. Class [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Bir TableDef nesnesi kullanmayı bitirdiğinizde, [Close](../../mfc/reference/cdaorecordset-class.md#close) üye işlevini çağırın; Sonra TableDef nesnesini yok edin.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="cdaotabledefappend"></a><a name="append"></a> CDaoTableDef:: Append

TableDef 'i veritabanına kaydetmek üzere yeni bir TableDef nesnesi oluşturmak için [Oluştur](#create) ' a çağrı yaptıktan sonra bu üye işlevini çağırın.

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, nesneyi veritabanının TableDefs koleksiyonuna ekler. TableDef öğesini ekleyerek geçici bir nesne olarak kullanabilirsiniz, ancak onu kaydedip kullanmak istiyorsanız, öğesini çağırmanız gerekir `Append` .

> [!NOTE]
> Adlandırılmamış bir TableDef (null veya boş dize içeren) eklemeye çalışırsanız, MFC bir özel durum oluşturur.

İlgili bilgiler için, DAO yardımı 'nda "ekleme yöntemi" konusuna bakın.

## <a name="cdaotabledefcanupdate"></a><a name="canupdate"></a> CDaoTableDef:: CanUpdate

Bir nesnenin temelindeki tablo tanımının değiştirilip değiştirilemeyeceğini öğrenmek için bu üye işlevi çağırın `CDaoTableDef` .

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo yapısı (şema) değiştirilemiyorsa (alanlar ve dizinler ekleyin veya silin), aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bir nesneyi temel alan yeni oluşturulan bir tablo `CDaoTableDef` güncelleştirilebilecek ve bir nesneyi temel alan eklenmiş bir tablo `CDaoTableDef` güncelleştirilemez. `CDaoTableDef`Elde edilen kayıt kümesi güncelleştirilebilir olmasa bile bir nesne güncelleştirilebilir olabilir.

İlgili bilgiler için, DAO yardımı 'nda "güncelleştirilebilir özellik" konusuna bakın.

## <a name="cdaotabledefcdaotabledef"></a><a name="cdaotabledef"></a> CDaoTableDef:: CDaoTableDef

Bir `CDaoTableDef` nesnesi oluşturur.

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra [Create](#create) veya [Open](#open) member işlevini çağırmanız gerekir. Nesnesiyle bitirdiğinizde, [Close](#close) üye işlevini çağırmanız ve nesneyi yok etmeniz gerekir `CDaoTableDef` .

## <a name="cdaotabledefclose"></a><a name="close"></a> CDaoTableDef:: Close

Tabledef nesnesini kapatmak ve serbest bırakmak için bu üye işlevi çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Genellikle çağrıldıktan sonra `Close` TableDef nesnesini, ile ayrıldıysa silinir **`new`** .

Öğesini çağırdıktan sonra yeniden [Aç](#open) ' a çağrı yapabilirsiniz `Close` . Bu, TableDef nesnesini yeniden kullanmanıza olanak sağlar.

İlgili bilgiler için, DAO yardımı 'nda "Yöntem kapatma" konusuna bakın.

## <a name="cdaotabledefcreate"></a><a name="create"></a> CDaoTableDef:: Create

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

TableDef 'i adlandırdıktan sonra, TableDef ' [i çağırıp veritabanının](#append) TableDefs koleksiyonuna kaydedebilirsiniz. Çağrıldıktan sonra `Append` , TableDef açık durumdadır ve bunu bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi oluşturmak için kullanabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "CreateTableDef yöntemi" konusuna bakın.

## <a name="cdaotabledefcreatefield"></a><a name="createfield"></a> CDaoTableDef:: CreateField

Tabloya bir alan eklemek için bu üye işlevini çağırın.

```cpp
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

Bir `DAOField` (OLE) nesnesi oluşturulur ve `DAOTableDef` (OLE) nesnesinin alanlar koleksiyonuna eklenir. Nesne özelliklerini incelemek için kullanmanın yanı sıra, `CDaoFieldInfo` bir TableDef içinde yeni alanlar oluşturmak için bir giriş parametresi oluşturmak için de kullanabilirsiniz. Uygulamasının ilk sürümü `CreateField` kullanımı basittir, ancak daha hassas bir denetim istiyorsanız, `CreateField` bir parametre alan ikinci sürümünü kullanabilirsiniz `CDaoFieldInfo` .

`CreateField`Bir parametre alan sürümünü kullanırsanız `CDaoFieldInfo` , yapının aşağıdaki üyelerinin her birini dikkatle ayarlamanız gerekir `CDaoFieldInfo` :

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

Kalan üyeleri, `CDaoFieldInfo` üyeye uygun şekilde **0**, false veya boş bir dize olarak ayarlanmalıdır ya da bir `CDaoException` gerçekleşebilir.

İlgili bilgiler için, DAO yardımı 'nda "CreateField yöntemi" konusuna bakın.

## <a name="cdaotabledefcreateindex"></a><a name="createindex"></a> CDaoTableDef:: CreateIndex

Tabloya bir dizin eklemek için bu işlevi çağırın.

```cpp
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>Parametreler

*ındexınfo*<br/>
Bir [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Dizinler, veritabanı tablolarından erişilen kayıt sırasını ve yinelenen kayıtların kabul edilip edilmeyeceğini belirtir. Dizinler ayrıca verilere verimli erişim sağlar.

Tablolar için dizin oluşturmanız gerekmez, ancak büyük, dizine alınmamış tablolarda, belirli bir kayda erişmek veya bir kayıt kümesi oluşturmak uzun sürebilir. Öte yandan, çok sayıda dizin oluşturmak güncelleştirme, ekleme ve silme işlemlerini yavaşlattığından tüm dizinler otomatik olarak güncelleştirilir. Hangi dizinlerin oluşturulacağı konusunda karar verirken bu faktörleri göz önünde bulundurun.

Yapının aşağıdaki üyeleri `CDaoIndexInfo` ayarlanmalıdır:

- `m_strName` Bir ad sağlanmalıdır.

- `m_pFieldInfos` Bir yapı dizisine işaret etmelidir `CDaoIndexFieldInfo` .

- `m_nFields` Yapıların dizisindeki alan sayısı belirtilmelidir `CDaoFieldInfo` .

Kalan Üyeler FALSE olarak ayarlandıysa yok sayılır. Ayrıca, `m_lDistinctCount` Dizin oluşturma sırasında üye yok sayılır.

## <a name="cdaotabledefdeletefield"></a><a name="deletefield"></a> CDaoTableDef::D eleteField

Bir alanı kaldırmak ve erişilebilir hale getirmek için bu üye işlevini çağırın.

```cpp
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

## <a name="cdaotabledefdeleteindex"></a><a name="deleteindex"></a> CDaoTableDef::D Eleteındex

Temel tablodaki bir dizini silmek için bu üye işlevini çağırın.

```cpp
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

## <a name="cdaotabledefgetattributes"></a><a name="getattributes"></a> CDaoTableDef:: GetAttributes

Bir `CDaoTableDef` nesne için, dönüş değeri nesnenin temsil ettiği tablonun özelliklerini belirtir `CDaoTableDef` ve bu sabitlerin toplamı olabilir:

```
long GetAttributes();
```

### <a name="return-value"></a>Dönüş Değeri

Bir nesnenin bir veya daha fazla özelliğini gösteren bir değer döndürür `CDaoTableDef` .

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

## <a name="cdaotabledefgetconnect"></a><a name="getconnect"></a> CDaoTableDef:: GetConnect

Bir veri kaynağı için bağlantı dizesi almak üzere bu üye işlevini çağırın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Tablo için yolu ve veritabanı türünü içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Eklenmiş bir `CDaoTableDef` tabloyu temsil eden bir nesne için, `CString` nesnesi bir veya iki bölümden oluşur (bir veritabanı türü belirticisi ve veritabanının yolu).

Aşağıdaki tabloda gösterildiği gibi yol, veritabanı dosyalarını içeren dizinin tam yoludur ve öncesinde "DATABASE =" tanımlayıcısı gelmelidir. Bazı durumlarda (Microsoft Jet ve Microsoft Excel veritabanlarında olduğu gibi), veritabanı yolu bağımsız değişkenine belirli bir dosya adı eklenir.

[CDaoTableDef:: SetConnect](#setconnect) içindeki tablo olası veritabanı türlerini ve bunlara karşılık gelen veritabanı belirticilerini ve yollarını gösterir:

Microsoft Jet veritabanı temel tabloları için, belirtici boş bir dizedir ("").

Bir parola gerekliyse ancak sağlanmazsa, ODBC sürücüsü bir tabloya ilk kez erişildiğinde bir oturum açma iletişim kutusu görüntüler ve bağlantı kapatılıp yeniden açılabilir. Eklenmiş bir tabloda `dbAttachSavePWD` özniteliği varsa, tablo yeniden açıldığında oturum açma istemi görünmez.

İlgili bilgiler için, DAO yardımı 'nda "bağlama özelliği" konusuna bakın.

## <a name="cdaotabledefgetdatecreated"></a><a name="getdatecreated"></a> CDaoTableDef:: GetDateCreated

Nesnenin temel aldığı tablonun oluşturulduğu tarih ve saati öğrenmek için bu işlevi çağırın `CDaoTableDef` .

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyi temel alan tablonun oluşturulma tarihini ve saatini içeren bir değer `CDaoTableDef` .

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablonun oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, kullanıcıların tutarsızlıkları önlemek için bu ayarları doğrudan dosya sunucusundan alması gerekir; diğer bir deyişle, tüm istemciler belki de bir sunucudan "standart" bir zaman kaynağı kullanmalıdır.

İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

## <a name="cdaotabledefgetdatelastupdated"></a><a name="getdatelastupdated"></a> CDaoTableDef:: GetDateLastUpdated

Nesnenin en son güncelleştirildiği tarihi ve saati öğrenmek için bu işlevi çağırın `CDaoTableDef` .

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin temelindeki tablonun son güncelleştirildiği tarih ve saati içeren bir değer `CDaoTableDef` .

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablonun oluşturulduğu veya en son güncelleştirildiği bilgisayardan türetilir. Çok kullanıcılı bir ortamda, kullanıcıların tutarsızlıkları önlemek için bu ayarları doğrudan dosya sunucusundan alması gerekir; diğer bir deyişle, tüm istemciler belki de bir sunucudan "standart" bir zaman kaynağı kullanmalıdır.

İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

## <a name="cdaotabledefgetfieldcount"></a><a name="getfieldcount"></a> CDaoTableDef:: GetFieldCount

Tabloda tanımlanan alan sayısını almak için bu üye işlevi çağırın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablodaki alan sayısı.

### <a name="remarks"></a>Açıklamalar

Değeri 0 ise, koleksiyonda nesne yoktur.

İlgili bilgiler için, DAO yardımı 'nda "Count Property" konusuna bakın.

## <a name="cdaotabledefgetfieldinfo"></a><a name="getfieldinfo"></a> CDaoTableDef:: GetFieldInfo

TableDef içinde tanımlı bir alanla ilgili çeşitli bilgi türlerini almak için bu üye işlevi çağırın.

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

*nDizin*<br/>
Dizine göre arama için tablonun sıfır tabanlı alanlar koleksiyonundaki alan nesnesinin dizini.

*sağlanırken*<br/>
[Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına başvuru.

*dwInfoOptions*<br/>
Alınacak alanla ilgili hangi bilgilerin alındığını belirleyen seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte aşağıda listelenmiştir:

- `AFX_DAO_PRIMARY_INFO` Varsayılanını Ad, tür, boyut, öznitelikler. En hızlı performans için bu seçeneği kullanın.

- `AFX_DAO_SECONDARY_INFO` Birincil bilgiler, artı: sıralı konum, gerekli, sıfır uzunluğa Izin ver, harmanlama sırası, yabancı ad, kaynak alanı, kaynak tablo

- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgiler, ayrıca: doğrulama kuralı, doğrulama metni, varsayılan değer

*lpszName*<br/>
Ada göre arama için alan nesnesinin adına yönelik bir işaretçi. Ad, alanı benzersiz şekilde adlandıran en fazla 64 karakter içeren bir dizedir.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü bir alanı dizine göre arama yapmanızı sağlar. Diğer sürüm, bir alanı adına göre arama yapmanızı sağlar.

Döndürülen bilgilerin açıklaması için bkz. [Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bu yapının, *Dwinfooptions* açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki tüm düzeyler için de bilgi alırsınız.

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

## <a name="cdaotabledefgetindexcount"></a><a name="getindexcount"></a> CDaoTableDef:: GetIndexCount

Bir tablo için dizin sayısını almak üzere bu üye işlevini çağırın.

```
short GetIndexCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo için dizin sayısı.

### <a name="remarks"></a>Açıklamalar

Değeri 0 ise, koleksiyonda dizin yoktur.

İlgili bilgiler için, DAO yardımı 'nda "Count Property" konusuna bakın.

## <a name="cdaotabledefgetindexinfo"></a><a name="getindexinfo"></a> CDaoTableDef:: GetIndexInfo

TableDef içinde tanımlı bir dizin hakkında çeşitli bilgiler almak için bu üye işlevi çağırın.

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

*nDizin*<br/>
Koleksiyondaki konumuna göre arama için tablonun sıfır tabanlı dizinler koleksiyonundaki dizin nesnesinin sayısal dizini.

*ındexınfo*<br/>
Bir [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına başvuru.

*dwInfoOptions*<br/>
Alınacak dizin hakkındaki bilgileri belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte aşağıda listelenmiştir:

- `AFX_DAO_PRIMARY_INFO` Ad, alan bilgisi, alanlar. En hızlı performans için bu seçeneği kullanın.

- `AFX_DAO_SECONDARY_INFO` Birincil bilgiler, artı: birincil, benzersiz, kümelenmiş, Yoksay null, gerekli, yabancı

- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgiler, ayrıca: ayrı sayım

*lpszName*<br/>
Ada göre arama için dizin nesnesinin adına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, koleksiyondaki konumuyla bir dizin araması yapmanızı sağlar. Diğer sürüm, dizin adına göre arama yapmanızı sağlar.

Döndürülen bilgilerin açıklaması için, [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions* açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki tüm düzeyler için de bilgi alırsınız.

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

## <a name="cdaotabledefgetname"></a><a name="getname"></a> CDaoTableDef:: GetName

Temel alınan tablonun Kullanıcı tanımlı adını almak için bu üye işlevi çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo için Kullanıcı tanımlı bir ad.

### <a name="remarks"></a>Açıklamalar

Bu ad, bir harfle başlar ve en fazla 64 karakter içerebilir. Sayılar ve alt çizgi karakterlerini içerebilir, ancak noktalama veya boşluk içeremez.

İlgili bilgiler için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

## <a name="cdaotabledefgetrecordcount"></a><a name="getrecordcount"></a> CDaoTableDef:: GetRecordCount

Bir nesnesinde kaç kayıt olduğunu bulmak için bu üye işlevi çağırın `CDaoTableDef` .

```
long GetRecordCount();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tabledef nesnesinde erişilen kayıt sayısı.

### <a name="remarks"></a>Açıklamalar

Tablo `GetRecordCount` türü bir nesne için arama, tablodaki `CDaoTableDef` yaklaşık sayıda kayıt yansıtır ve tablo kayıtları eklenip silindiğine hemen etkilenir. Geri alınmış işlemler, [CDaoWorkspace:: CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)öğesini çağırana kadar kayıt sayısının bir parçası olarak görüntülenir. Kayıt `CDaoTableDef` içermeyen bir nesne, 0 kayıt sayısı özelliği ayarına sahiptir. Eklenmiş tablolar veya ODBC veritabanları ile çalışırken `GetRecordCount` her zaman-1 döndürür.

İlgili bilgiler için, DAO yardımı 'nda "RecordCount özelliği" konusuna bakın.

## <a name="cdaotabledefgetsourcetablename"></a><a name="getsourcetablename"></a> CDaoTableDef:: GetSourceTableName

Bir kaynak veritabanında eklenmiş bir tablonun adını almak için bu üye işlevini çağırın.

```
CString GetSourceTableName();
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Eklenmiş bir tablonun kaynak adını veya yerel veri tablosu ise boş bir dizeyi belirten nesne.

### <a name="remarks"></a>Açıklamalar

Ekli tablo, bir Microsoft Jet veritabanıyla bağlantılı başka bir veritabanındaki tablodur. Ekli tablo verileri, diğer uygulamalar tarafından işlenebileceği dış veritabanında kalır.

İlgili bilgiler için, DAO yardımı 'nda "SourceTableName özelliği" konusuna bakın.

## <a name="cdaotabledefgetvalidationrule"></a><a name="getvalidationrule"></a> CDaoTableDef:: GetValidationRule

Bir TableDef için doğrulama kuralını almak üzere bu üye işlevi çağırın.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Değiştirilen veya tabloya eklenen bir alandaki verileri doğrulayan bir nesne.

### <a name="remarks"></a>Açıklamalar

Doğrulama kuralları, güncelleştirme işlemleriyle bağlantılı olarak kullanılır. Bir TableDef bir doğrulama kuralı içeriyorsa, veri değiştirilmeden önce bu TableDef güncelleştirmelerinin önceden belirlenmiş ölçütlerle eşleşmesi gerekir. Değişiklik ölçütlere eşleşmezse [GetValidationText](#getvalidationtext) değerini içeren bir özel durum oluşturulur. Bir `CDaoTableDef` nesne için, bu, `CString` ekli tablo için salt okunurdur ve temel tablo için okuma/yazma olur.

İlgili bilgiler için, DAO yardımı 'nda "ValidationRule özelliği" konusuna bakın.

## <a name="cdaotabledefgetvalidationtext"></a><a name="getvalidationtext"></a> CDaoTableDef:: GetValidationText

Kullanıcı doğrulama kuralıyla eşleşmeyen verileri girdiğinde görüntülenecek dizeyi almak için bu işlevi çağırın.

```
CString GetValidationText();
```

### <a name="return-value"></a>Dönüş Değeri

`CString`Kullanıcı doğrulama kuralıyla eşleşmeyen verileri girerse görüntülenen metni belirten nesne.

### <a name="remarks"></a>Açıklamalar

Bir `CDaoTableDef` nesne için, bu, `CString` ekli tablo için salt okunurdur ve temel tablo için okuma/yazma olur.

İlgili bilgiler için, DAO yardımı 'nda "ValidationText özelliği" konusuna bakın.

## <a name="cdaotabledefisopen"></a><a name="isopen"></a> CDaoTableDef:: IsOpen

Nesnenin şu anda açık olup olmadığını anlamak için bu üye işlevi çağırın `CDaoTableDef` .

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDaoTableDef`Nesne açıksa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaotabledefm_pdatabase"></a><a name="m_pdatabase"></a> CDaoTableDef:: m_pDatabase

Bu tablo için [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine bir işaretçi içeriyor.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaotabledefm_pdaotabledef"></a><a name="m_pdaotabledef"></a> CDaoTableDef:: m_pDAOTableDef

Nesneyi temel alan DAO TableDef nesnesi için OLE arabirimine yönelik bir işaretçi içerir `CDaoTableDef` .

### <a name="remarks"></a>Açıklamalar

DAO arabirimine doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.

## <a name="cdaotabledefopen"></a><a name="open"></a> CDaoTableDef:: Open

Daha önce veritabanının Tabledefın koleksiyonunda kayıtlı olan bir TableDef açmak için bu üye işlevini çağırın.

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bir tablo adı belirten bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaotabledefrefreshlink"></a><a name="refreshlink"></a> CDaoTableDef:: RefreshLink

Ekli bir tablonun bağlantı bilgilerini güncelleştirmek için bu üye işlevi çağırın.

```cpp
void RefreshLink();
```

### <a name="remarks"></a>Açıklamalar

Ekli bir tablo için bağlantı bilgilerini, ilgili nesnede [SetConnect](#setconnect) 'i çağırarak `CDaoTableDef` ve sonra da bu `RefreshLink` bilgileri güncelleştirmek için üye işlevini kullanarak değiştirirsiniz. `RefreshLink`' İ çağırdığınızda, eklenen tablonun özellikleri değiştirilmez.

Değiştirilen bağlantı bilgilerinin etkili olmasını zorlamak için, bu TableDef 'e dayalı tüm açık [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnelerinin kapatılması gerekir.

İlgili bilgiler için, DAO yardımı 'nda "RefreshLink method" konusuna bakın.

## <a name="cdaotabledefsetattributes"></a><a name="setattributes"></a> CDaoTableDef:: SetAttributes

Bir nesnenin bir veya daha fazla özelliğini gösteren bir değer ayarlar `CDaoTableDef` .

```cpp
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>Parametreler

*lAttributes*<br/>
Nesnenin temsil ettiği tablonun özellikleri `CDaoTableDef` ve bu sabitlerin toplamı olabilir:

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, tablonun özel kullanım için açılmış bir eklenmiş tablo olduğunu gösterir.|
|`dbAttachSavePWD`|Microsoft Jet veritabanı altyapısını kullanan veritabanları için, ekli tablo için Kullanıcı KIMLIĞI ve parolanın bağlantı bilgileriyle kaydedildiğini belirtir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sunulan gizli bir tablo olduğunu gösterir.|

### <a name="remarks"></a>Açıklamalar

Birden çok öznitelik ayarlarken, bit düzeyinde OR işlecini kullanarak uygun sabitleri toplayarak bunları birleştirebilirsiniz. `dbAttachExclusive`Eklenmemiş bir tablonun ayarı bir özel durum oluşturur. Aşağıdaki değerleri birleştirmek özel bir durum da üretir:

- **dbAttachExclusive &#124; dbAttachedODBC**

- **dbAttachSavePWD &#124; dbAttachedTable**

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

## <a name="cdaotabledefsetconnect"></a><a name="setconnect"></a> CDaoTableDef:: SetConnect

Eklenmiş bir `CDaoTableDef` tabloyu temsil eden bir nesne için dize nesnesi bir veya iki bölümden oluşur (bir veritabanı türü belirticisi ve veritabanının yolu).

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Parametreler

*lpszConnect*<br/>
ODBC veya yüklenebilir ISAM sürücülerine geçirilecek ek parametreleri belirten bir dize ifadesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda gösterildiği gibi yol, veritabanı dosyalarını içeren dizinin tam yoludur ve öncesinde "DATABASE =" tanımlayıcısı gelmelidir. Bazı durumlarda (Microsoft Jet ve Microsoft Excel veritabanlarında olduğu gibi), veritabanı yolu bağımsız değişkenine belirli bir dosya adı eklenir.

> [!NOTE]
> "DATABASE = Drive: \path" biçimindeki eşittir oturum açma yolu deyimlerinin etrafına boşluk eklemeyin \\ . Bu, bir özel durumun oluşmasına ve bağlantının başarısız olmasına neden olur.

Aşağıdaki tabloda, olası veritabanı türleri ve bunlara karşılık gelen veritabanı belirticileri ve yolları gösterilmektedir:

|Veritabanı türü|Belirleyici|Yol|
|-------------------|---------------|----------|
|Jet veritabanı altyapısını kullanan veritabanı|"[ `database`];"|" `drive` : \\ \  *yol* \\ \  *dosya adı*. TATIL|
|dBASE III|"dBASE III;"|" `drive` : \\ \  *yol*"|
|dBASE IV|"dBASE IV;"|" `drive` : \\ \  *yol*"|
|dBASE 5|"dBASE 5,0;"|" `drive` : \\ \  *yol*"|
|Paradox 3. x|"Paradox 3. x;"|" `drive` : \\ \  *yol*"|
|Paradox 4. x|"Paradox 4. x;"|" `drive` : \\ \  *yol*"|
|Paradox 5. x|"Paradox 5. x;"|" `drive` : \\ \  *yol*"|
|Excel 3,0|"Excel 3,0;"|" `drive` : \\ \  *yol* \\ \  *dosya adı*. XLS|
|Excel 4,0|"Excel 4,0;"|" `drive` : \\ \  *yol* \\ \  *dosya adı*. XLS|
|Excel 5,0 veya Excel 95|"Excel 5,0;"|" `drive` : \\ \  *yol* \\ \  *dosya adı*. XLS|
|Excel 97|"Excel 8,0;"|" `drive` : \\ \  *yol* \  *dosya adı*. XLS|
|HTML Içeri aktarma|"HTML Içeri aktarma;"|" `drive` : \\ \  *yol* \  *dosya adı*"|
|HTML dışarı aktarma|"HTML dışarı aktarma;"|" `drive` : \\ \  *yol*"|
|Metin|"Metin;"|"sürücü: \\ \Yol"|
|ODBC|ISTI VERITABANı = `database` ; UID = *User*; PWD = *parola*; DSN = *DataSourceName;* LOGINTIMEOUT = *saniye;*" (Bu, tüm sunucular için tam bir bağlantı dizesi olmayabilir; yalnızca bir örnektir. Parametreler arasında boşluk olmaması çok önemlidir.)|Yok|
|Exchange|Değişimi<br /><br /> MAPILELEVEL = *FolderPath*;<br /><br /> [TABLETYPE = {0 &#124; 1};]<br /><br /> [PROFILE = *profile*;]<br /><br /> [PWD = *Password*;]<br /><br /> [VERITABANı = `database` ;] "|*"sürücü*: \\ \  *yol* \\ \  *dosya adı*. TATIL|

> [!NOTE]
> Btrieve, DAO 3,5 itibariyle artık desteklenmiyor.

\\Bağlantı dizelerinde çift ters eğik çizgi () kullanmanız gerekir \\ . Kullanarak var olan bir bağlantının özelliklerini değiştirdiyseniz `SetConnect` , daha sonra [RefreshLink](#refreshlink)çağrısı yapmanız gerekir. Kullanarak bağlantı özelliklerini başlatdıysanız, `SetConnect` çağırmamalıdır `RefreshLink` , ancak bunu yapmanız gerekir, önce TableDef 'i ekleyin.

Bir parola gerekliyse ancak sağlanmazsa, ODBC sürücüsü bir tabloya ilk kez erişildiğinde bir oturum açma iletişim kutusu görüntüler ve bağlantı kapatılıp yeniden açılabilir.

`CDaoTableDef`Üye işlevine bir kaynak bağımsız değişkeni sağlayarak bir nesne için bağlantı dizesi ayarlayabilirsiniz `Create` . Bu ayarı, veritabanının türünü, yolunu, kullanıcı KIMLIĞINI, parolasını veya ODBC veri kaynağını tespit etmek için denetleyebilirsiniz. Daha fazla bilgi için, belirli sürücü için belgelere bakın.

İlgili bilgiler için, DAO yardımı 'nda "bağlama özelliği" konusuna bakın.

## <a name="cdaotabledefsetname"></a><a name="setname"></a> CDaoTableDef:: SetName

Bir tablo için Kullanıcı tanımlı bir ad ayarlamak üzere bu üye işlevini çağırın.

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bir tablo için ad belirten bir dize ifadesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ad bir harfle başlamalı ve en fazla 64 karakter içerebilir. Sayılar ve alt çizgi karakterlerini içerebilir, ancak noktalama veya boşluk içeremez.

İlgili bilgiler için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

## <a name="cdaotabledefsetsourcetablename"></a><a name="setsourcetablename"></a> CDaoTableDef:: SetSourceTableName

Bu üye işlevini, eklenen bir tablonun adını veya `CDaoTableDef` nesnenin temel aldığı verilerin orijinal kaynağında bulunduğu temel tablonun adını belirtmek için çağırın.

```cpp
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>Parametreler

*lpszSrcTableName*<br/>
Dış veritabanında tablo adı belirten bir dize ifadesi işaretçisi. Temel tablo için, ayar boş bir dizedir ("").

### <a name="remarks"></a>Açıklamalar

Ardından [RefreshLink](#refreshlink)çağrısı yapmanız gerekir. Bu özellik ayarı bir temel tablo için boştur ve ekli tablo veya bir koleksiyona eklenmemiş bir nesne için okuma/yazma işlemi.

İlgili bilgiler için, DAO yardımı 'nda "SourceTableName özelliği" konusuna bakın.

## <a name="cdaotabledefsetvalidationrule"></a><a name="setvalidationrule"></a> CDaoTableDef:: SetValidationRule

Bir TableDef için doğrulama kuralı ayarlamak için bu üye işlevi çağırın.

```cpp
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>Parametreler

*lpszValidationRule*<br/>
Bir işlemi doğrulayan dize ifadesinin işaretçisi.

### <a name="remarks"></a>Açıklamalar

Doğrulama kuralları, güncelleştirme işlemleriyle bağlantılı olarak kullanılır. Bir TableDef bir doğrulama kuralı içeriyorsa, veri değiştirilmeden önce bu TableDef güncelleştirmelerinin önceden belirlenmiş ölçütlerle eşleşmesi gerekir. Değişiklik ölçütlere eşleşmezse [GetValidationText](#getvalidationtext) metnini içeren bir özel durum görüntülenir.

Doğrulama yalnızca Microsoft Jet veritabanı altyapısını kullanan veritabanları için desteklenir. İfade Kullanıcı tanımlı işlevlere, etki alanı toplama işlevlerine, SQL toplama işlevlerine veya sorgulara başvuramaz. Bir nesne için doğrulama kuralı `CDaoTableDef` , bu nesnedeki birden çok alana başvurabilir.

Örneğin, *hire_date* ve *termination_date* adlı alanlar için, bir doğrulama kuralı şu olabilir:

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

İlgili bilgiler için, DAO yardımı 'nda "ValidationRule özelliği" konusuna bakın.

## <a name="cdaotabledefsetvalidationtext"></a><a name="setvalidationtext"></a> CDaoTableDef:: SetValidationText

`CDaoTableDef`Microsoft Jet veritabanı altyapısı tarafından desteklenen temel bir temel tabloyla bir nesne için doğrulama kuralının özel durum metnini ayarlamak için bu üye işlevi çağırın.

```cpp
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>Parametreler

*lpszValidationText*<br/>
Girilen veriler geçersizse görüntülenen metni belirten bir dize ifadesi işaretçisi.

### <a name="remarks"></a>Açıklamalar

Eklenmiş bir tablonun doğrulama metnini ayarlayamazsınız.

İlgili bilgiler için, DAO yardımı 'nda "ValidationText özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)
