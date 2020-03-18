---
title: CDynamicAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
- ATL::CDynamicAccessor::AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
- ATL::CDynamicAccessor::Close
- ATL.CDynamicAccessor.Close
- CDynamicAccessor.Close
- CDynamicAccessor::Close
- ATL.CDynamicAccessor.GetBlobHandling
- CDynamicAccessor::GetBlobHandling
- ATL::CDynamicAccessor::GetBlobHandling
- GetBlobHandling
- CDynamicAccessor.GetBlobHandling
- ATL::CDynamicAccessor::GetBlobSizeLimit
- CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor::GetBlobSizeLimit
- GetBlobSizeLimit
- ATL.CDynamicAccessor.GetBlobSizeLimit
- CDynamicAccessor.GetBookmark
- GetBookmark
- CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetBookmark
- ATL::CDynamicAccessor::GetBookmark
- ATL.CDynamicAccessor.GetColumnCount
- ATL::CDynamicAccessor::GetColumnCount
- CDynamicAccessor::GetColumnCount
- CDynamicAccessor.GetColumnCount
- GetColumnCount
- CDynamicAccessor.GetColumnFlags
- ATL::CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnFlags
- CDynamicAccessor::GetColumnFlags
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
- ATL::CDynamicAccessor::GetColumnName
- GetColumnName
- ATL.CDynamicAccessor.GetColumnName
- CDynamicAccessor::GetColumnName
- CDynamicAccessor.GetColumnName
- ATL.CDynamicAccessor.GetColumnType
- CDynamicAccessor::GetColumnType
- GetColumnType
- CDynamicAccessor.GetColumnType
- ATL::CDynamicAccessor::GetColumnType
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
- ATL::CDynamicAccessor::GetStatus
- CDynamicAccessor.GetStatus
- ATL.CDynamicAccessor.GetStatus
- CDynamicAccessor::GetStatus
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
- ATL::CDynamicAccessor::SetLength
- CDynamicAccessor.SetLength
- CDynamicAccessor::SetLength
- ATL.CDynamicAccessor.SetLength
- CDynamicAccessor::SetStatus
- ATL::CDynamicAccessor::SetStatus
- CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetStatus
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
helpviewer_keywords:
- CDynamicAccessor class
- AddBindEntry method
- CDynamicAccessor class, constructor
- Close method
- GetBlobHandling method
- GetBlobSizeLimit method
- GetBookmark method
- GetColumnCount method
- GetColumnFlags method
- GetColumnInfo method
- GetColumnName method
- GetColumnType method
- GetLength method
- GetOrdinal method
- GetStatus method
- GetValue method
- SetBlobHandling method
- SetBlobSizeLimit method
- SetLength method
- SetStatus method
- SetValue method
ms.assetid: 374b13b7-1f09-457d-9e6b-df260ff4d178
ms.openlocfilehash: 08e36606ae5d8dc34b9e25dd7d8dbc6d606520da
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447385"
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor Sınıfı

Veritabanı şeması (veritabanının temel yapısı) hakkında bilginiz olmadığında bir veri kaynağına erişmenizi sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDynamicAccessor : public CAccessorBase
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddBindEntry](#addbindentry)|Varsayılan erişimciyi geçersiz kılarken çıkış sütunlarına bir bağlama girişi ekler.|
|[CDynamicAccessor](#cdynamicaccessor)|`CDynamicAccessor` nesnesini başlatır ve başlatır.|
|[~Eksik](#close)|Tüm sütunların bağlantısını kaldırır, ayrılan belleği serbest bırakır ve sınıfında [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) arabirim işaretçisini yayınlar.|
|[GetBlobHandling](#getblobhandling)|Geçerli satır için BLOB işleme değerini alır.|
|[GetBlobSizeLimit](#getblobsizelimit)|En büyük BLOB boyutunu bayt cinsinden alır.|
|[GetBookmark](#getbookmark)|Geçerli satırın yer işaretini alır.|
|[GetColumnCount](#getcolumncount)|Satır kümesindeki sütun sayısını alır.|
|[GetColumnFlags](#getcolumnflags)|Sütun özelliklerini alır.|
|[GetColumnInfo](#getcolumninfo)|Sütun meta verilerini alır.|
|[GetColumnName](#getcolumnname)|Belirtilen sütunun adını alır.|
|[GetColumnType](#getcolumntype)|Belirtilen sütunun veri türünü alır.|
|[GetLength](#getlength)|Bir sütunun bayt olarak en fazla olası uzunluğunu alır.|
|[GetOrdinal](#getordinal)|Sütun adı verilen sütun dizinini alır.|
|[GetStatus](#getstatus)|Belirtilen sütunun durumunu alır.|
|[GetValue](#getvalue)|Arabellekteki verileri alır.|
|[SetBlobHandling](#setblobhandling)|Geçerli satır için BLOB işleme değerini ayarlar.|
|[SetBlobSizeLimit](#setblobsizelimit)|En büyük BLOB boyutunu bayt cinsinden ayarlar.|
|[SetLength](#setlength)|Sütunun uzunluğunu bayt olarak ayarlar.|
|[SetStatus](#setstatus)|Belirtilen sütunun durumunu ayarlar.|
|[SetValue](#setvalue)|Verileri arabelleğe depolar.|

## <a name="remarks"></a>Açıklamalar

Sütun adları, sütun sayısı, veri türü vb. gibi sütun bilgilerini almak için `CDynamicAccessor` yöntemler kullanın. Daha sonra bu sütun bilgisini, çalışma zamanında dinamik olarak bir erişimci oluşturmak için kullanırsınız.

Sütun bilgileri bu sınıf tarafından oluşturulan ve yönetilen bir arabellekte saklanır. [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md)kullanarak arabellekteki verileri alın.

Bir tartışma ve dinamik erişimci sınıflarını kullanma örnekleri için bkz. [dinamik erişimcileri kullanma](../../data/oledb/using-dynamic-accessors.md).

## <a name="addbindentry"></a>CDynamicAccessor:: AddBindEntry

Çıkış sütunlarına bir bağlama girişi ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();
```

#### <a name="parameters"></a>Parametreler

*bilgisine*<br/>
'ndaki Sütun bilgilerini içeren `DBCOLUMNINFO` yapısı. *OLE DB Programcı başvurusunda* [IColumnsInfo:: GETCOLUMNıNFO](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) IÇINDE "DBCOLUMNINFO yapýlarý" başlığına bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`CDynamicAccessor` ile oluşturulan varsayılan erişimciyi geçersiz kılarken bu yöntemi kullanın (bkz. [verileri nasıl alabilirim?](../../data/oledb/fetching-data.md)).

## <a name="cdynamicaccessor"></a>CDynamicAccessor:: CDynamicAccessor

`CDynamicAccessor` nesnesini başlatır ve başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000);
```

#### <a name="parameters"></a>Parametreler

*eBlobHandling*<br/>
İkili büyük nesne (BLOB) verilerinin nasıl işleneceğini belirtir. Varsayılan değer DBBLOBHANDLING_DEFAULT. DBBLOBHANDLINGENUM değerlerinin açıklaması için bkz. [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) .

*nBlobSize*<br/>
En büyük BLOB boyutu bayt cinsinden; Bu değer üzerindeki sütun verileri bir BLOB olarak değerlendirilir. Varsayılan değer 8.000 ' dir. Ayrıntılar için bkz. [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) .

### <a name="remarks"></a>Açıklamalar

`CDynamicAccessor` nesnesini başlatmak için oluşturucuyu kullanırsanız, blob 'Ları nasıl bağlayacağınız belirtebilirsiniz. Blob 'Lar, grafikler, ses veya derlenmiş kod gibi ikili veriler içerebilir. Varsayılan davranış, sütunları 8.000 bayttan fazla BLOB olarak değerlendirmek ve bunları bir `ISequentialStream` nesnesine bağlamayı denemedir. Ancak, BLOB boyutu olacak şekilde farklı bir değer belirtebilirsiniz.

Ayrıca, `CDynamicAccessor` BLOB verileri olarak niteleyen sütun verilerini nasıl işleyeceğini belirtebilirsiniz: BLOB verilerini varsayılan şekilde işleyebilir; BLOB verilerini atlayabilir (bağlanamaz). ya da, BLOB verilerini sağlayıcıya ayrılan belleğe bağlayabilir.

## <a name="close"></a>CDynamicAccessor:: Close

Tüm sütunların bağlantısını kaldırır, ayrılan belleği serbest bırakır ve sınıfında [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) arabirim işaretçisini yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close() throw();
```

## <a name="getblobhandling"></a>CDynamicAccessor:: GetBlobHandling

Geçerli satır için BLOB işleme değerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
const DBBLOBHANDLINGENUM GetBlobHandling() const;
```

### <a name="remarks"></a>Açıklamalar

[SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)tarafından ayarlanan *EBLOBHANDLING* blob işleme değerini döndürür.

## <a name="getblobsizelimit"></a>CDynamicAccessor:: GetBlobSizeLimit

En büyük BLOB boyutunu bayt cinsinden alır.

### <a name="syntax"></a>Sözdizimi

```cpp
const DBLENGTH GetBlobSizeLimit() const;
```

### <a name="remarks"></a>Açıklamalar

[SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)tarafından ayarlanan blob Işleme değerini *nBlobSize* döndürür.

## <a name="getbookmark"></a>CDynamicAccessor:: GetBookmark

Geçerli satırın yer işaretini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();
```

#### <a name="parameters"></a>Parametreler

*pBookmark*<br/>
dışı [CBookmark](../../data/oledb/cbookmark-class.md) nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bir yer işaretini almak için `DBPROP_IRowsetLocate` VARIANT_TRUE ayarlamanız gerekir.

## <a name="getcolumncount"></a>CDynamicAccessor:: GetColumnCount

Sütun sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
DBORDINAL GetColumnCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Alınan sütun sayısı.

## <a name="getcolumnflags"></a>CDynamicAccessor:: GetColumnFlags

Sütun özelliklerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetColumnFlags(DBORDINAL nColumn,
   DBCOLUMNFLAGS* pFlags) const throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

*pFlags*<br/>
dışı Sütun özelliklerini açıklayan bir bit maskesi işaretçisi. *OLE DB Programcı başvurusunda* [IColumnsInfo:: GETCOLUMNıNFO](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) IÇINDE "dbcolumnflags enum Type" başlığına bakın.

### <a name="return-value"></a>Dönüş Değeri

Sütun özellikleri başarıyla alınırsa **true** değerini döndürür. Aksi takdirde, **false**döndürür.

### <a name="remarks"></a>Açıklamalar

Sütun numarası bir öğesinden uzaklığa göre belirlenir. Sıfır sütunu özel bir durumdur; varsa yer işaretidir.

## <a name="getcolumninfo"></a>CDynamicAccessor:: GetColumnInfo

Çoğu tüketiciden gereken sütun meta verilerini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetColumnInfo(IRowset* pRowset,
   DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo,
   OLECHAR** ppStringsBuffer) throw();
```

#### <a name="parameters"></a>Parametreler

*pRowset*<br/>
'ndaki [IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) arabirimine yönelik bir işaretçi.

*pColumns 'lar*<br/>
dışı Satır kümesindeki sütun sayısının döndürüleceği bir bellek işaretçisi; Bu sayı, varsa yer işareti sütununu içerir.

*Ppcolumnınfo*<br/>
dışı Bir dizi `DBCOLUMNINFO` yapının döndürüleceği bir bellek işaretçisi. *OLE DB Programcı başvurusunda* [IColumnsInfo:: GETCOLUMNıNFO](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) IÇINDE "DBCOLUMNINFO yapýlarý" başlığına bakın.

*ppStringsBuffer*<br/>
dışı Tek bir ayırma bloğunda, tüm dize değerleri ( *ColumnID* veya *pwszName*içinde kullanılan adlar) için depolama işaretçisi döndürecek bir bellek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

`DBORDINAL`, `DBCOLUMNINFO`ve `OLECHAR`veri türleri hakkında bilgi edinmek için *OLE DB Programcı başvurusu* Içindeki [IColumnsInfo:: GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) bölümüne bakın.

## <a name="getcolumnname"></a>CDynamicAccessor:: GetColumnName

Belirtilen sütunun adını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütunun adı.

## <a name="getcolumntype"></a>CDynamicAccessor:: GetColumnType

Belirtilen sütunun veri türünü alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetColumnType(DBORDINAL nColumn,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

*pType*<br/>
dışı Belirtilen sütunun veri türüne yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı veya hatalı olduğunda **false** **döndürür.**

## <a name="getlength"></a>CDynamicAccessor:: GetLength

Belirtilen sütunun uzunluğunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetLength(DBORDINAL nColumn,
   DBLENGTH* pLength) const throw();

bool GetLength(const CHAR* pColumnName,
   DBLENGTH* pLength) const throw();

bool GetLength(const WCHAR* pColumnName,
   DBLENGTH* pLength) const throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

*pColumnName*<br/>
'ndaki Sütun adını içeren bir karakter dizesinin işaretçisi.

*pLength*<br/>
dışı Sütunun bayt cinsinden uzunluğunu içeren tamsayıya yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütun bulunursa **true** değerini döndürür. Aksi takdirde, bu işlev **false**döndürür.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma, sütun numarasını alır ve ikinci ve üçüncü geçersiz kılmalar sütun adını sırasıyla ANSI veya Unicode biçiminde alır.

## <a name="getordinal"></a>CDynamicAccessor:: GetOrdinal

Sütun adı verilen sütun numarasını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetOrdinal(const CHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();

bool GetOrdinal(const WCHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();
```

#### <a name="parameters"></a>Parametreler

*pColumnName*<br/>
'ndaki Sütun adını içeren bir karakter dizesinin işaretçisi.

*pOrdinal*<br/>
dışı Sütun numarasına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen ada sahip bir sütun bulunursa **true** değerini döndürür. Aksi takdirde, bu işlev **false**döndürür.

## <a name="getstatus"></a>CDynamicAccessor:: GetStatus

Belirtilen sütunun durumunu alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetStatus(DBORDINAL nColumn,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const CHAR* pColumnName,
   DBSTATUS* pStatus) const throw();

bool GetStatus(const WCHAR* pColumnName,
   DBSTATUS* pStatus) const throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

*pColumnName*<br/>
'ndaki Sütun adını içeren bir karakter dizesinin işaretçisi.

*pStatus*<br/>
dışı Sütun durumunu içeren değişkene yönelik bir işaretçi. Daha fazla bilgi için *OLE DB Programcı başvurusunda* [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütun bulunursa **true** değerini döndürür. Aksi takdirde, bu işlev **false**döndürür.

## <a name="getvalue"></a>CDynamicAccessor:: GetValue

Belirtilen sütun için verileri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
void* GetValue(DBORDINAL nColumn) const throw();

void* GetValue(const CHAR* pColumnName) const throw();

void* GetValue(const WCHAR* pColumnName) const throw();

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();

template < class ctype >
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();

template < class ctype >
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();
```

#### <a name="parameters"></a>Parametreler

*CType*<br/>
'ndaki Özel işleme gerektiren dize türleri (`CHAR*`, `WCHAR*`) dışında herhangi bir veri türünü işleyen şablonlu bir parametre. `GetValue`, burada belirttiğiniz alana göre uygun veri türünü kullanır.

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

*pColumnName*<br/>
'ndaki Sütun adı.

*pData*<br/>
dışı Belirtilen sütunun içerik işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dize verilerini geçirmek istiyorsanız, `GetValue`şablonlu olmayan sürümlerini kullanın. Bu yöntemin şablonlu olmayan sürümleri, belirtilen sütun verilerini içeren arabelleğin kısmına işaret eden `void*`döndürür. Sütun bulunmazsa NULL değerini döndürür.

Diğer tüm veri türleri için `GetValue`şablonlu sürümlerinin kullanılması daha basittir. Şablonlu sürümler başarılı veya hatalı hata durumunda **false** **değerini döndürür.**

### <a name="remarks"></a>Açıklamalar

Diğer veri türlerini içeren sütunlarda dize ve şablonlu sürümler içeren sütunları döndürmek için Şablonsuz sürümleri kullanın.

Hata ayıklama modunda, *pData* boyutu işaret ettiği sütunun boyutuna eşit değilse bir onaylama işlemi alacaksınız.

## <a name="setblobhandling"></a>CDynamicAccessor:: SetBlobHandling

Geçerli satır için BLOB işleme değerini ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);
```

#### <a name="parameters"></a>Parametreler

*eBlobHandling*<br/>
BLOB verilerinin nasıl işleneceğini belirtir. Bu, aşağıdaki değerleri alabilir:

- DBBLOBHANDLING_DEFAULT: sütun verilerini *nBlobSize* (`SetBlobSizeLimit`tarafından ayarlandığı gıbı) blob verileri olarak işleyin ve bir `ISequentialStream` veya `IStream` nesnesi aracılığıyla alın. Bu seçenek, *nBlobSize* boyutundan büyük verileri içeren veya dbtype_ıunknown olarak listelenen her sütunu blob verileri olarak bağlamaya çalışır.

- DBBLOBHANDLING_NOSTREAMS: sütun verilerini *nBlobSize* (`SetBlobSizeLimit`tarafından ayarlandığı gıbı) blob verileri olarak işleyin ve sağlayıcıya ayrılan, tüketiciye ait bellek ' deki başvuruya alın. Bu seçenek, birden fazla BLOB sütunu olan tablolar için yararlıdır ve sağlayıcı her erişimci için yalnızca bir `ISequentialStream` nesnesini destekler.

- DBBLOBHANDLING_SKIP: Skip (bağlama) blob 'Ları içeren bir sütun niteleyen (erişimci sütun değerini bağlamaz veya alamaz, ancak yine de sütun durumunu ve uzunluğu alır).

### <a name="remarks"></a>Açıklamalar

`Open`çağrılmadan önce `SetBlobHandling` çağırmalısınız.

Bir Oluşturucu yöntemi [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) blob işleme değerini DBBLOBHANDLING_DEFAULT olarak ayarlar.

## <a name="setblobsizelimit"></a>CDynamicAccessor:: SetBlobSizeLimit

En büyük BLOB boyutunu bayt cinsinden ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetBlobSizeLimit(DBLENGTH nBlobSize);
```

#### <a name="parameters"></a>Parametreler

*nBlobSize*<br/>
BLOB boyut sınırını belirtir.

### <a name="remarks"></a>Açıklamalar

En büyük BLOB boyutunu bayt cinsinden ayarlar; Bu değerden daha büyük olan sütun verileri bir BLOB olarak değerlendirilir. Bazı sağlayıcılar sütunlar için çok büyük boyutlar (2 GB gibi) verir. Bu boyuttaki bir sütun için bellek ayırmaya çalışmak yerine, genellikle bu sütunları blob olarak bağlamaya çalışırsınız. Bu şekilde, tüm belleği ayırmanız gerekmez, ancak tüm verileri korksız bir biçimde okumaya devam edebilirsiniz. Ancak, `CDynamicAccessor`, yerel veri türlerinde büyük sütunları bağlamaya zorlamak isteyebileceğiniz bazı durumlar vardır. Bunu yapmak için, `Open`çağrılmadan önce `SetBlobSizeLimit` çağırın.

Bir kurucu yöntemi [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , en büyük blob boyutunu varsayılan değer olan 8.000 bayt olarak ayarlar.

## <a name="setlength"></a>CDynamicAccessor:: SetLength

Belirtilen sütunun uzunluğunu ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetLength(DBORDINAL nColumn,
   DBLENGTH nLength)throw();

bool SetLength(const CHAR* pColumnName,
   DBLENGTH nLength) throw();

bool SetLength(const WCHAR* pColumnName,
   DBLENGTH nLength) throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

*nLength*<br/>
'ndaki Sütunun bayt cinsinden uzunluğu.

*pColumnName*<br/>
'ndaki Sütun adını içeren bir karakter dizesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütun uzunluğu başarıyla ayarlandıysa **true** değerini döndürür. Aksi takdirde, bu işlev **false**döndürür.

## <a name="setstatus"></a>CDynamicAccessor:: SetStatus

Belirtilen sütunun durumunu ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetStatus(DBORDINAL nColumn,
   DBSTATUS status)throw();

bool SetStatus(const CHAR* pColumnName,
   DBSTATUS status) throw();

bool SetStatus(const WCHAR* pColumnName,
   DBSTATUS status) throw();
```

#### <a name="parameters"></a>Parametreler

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

*durumlarına*<br/>
'ndaki Sütun durumu. Daha fazla bilgi için *OLE DB Programcı başvurusunda* [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) bölümüne bakın.

*pColumnName*<br/>
'ndaki Sütun adını içeren bir karakter dizesinin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütun durumu başarıyla ayarlandıysa **true** değerini döndürür. Aksi takdirde, bu işlev **false**döndürür.

## <a name="setvalue"></a>CDynamicAccessor:: SetValue

Verileri belirtilen bir sütuna depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
template <class ctype>
bool SetValue(
   DBORDINAL nColumn,
   constctype& data) throw( );

template <class ctype> 
bool SetValue(
   const CHAR * pColumnName,
   const ctype& data) throw( );

template <class ctype>
bool SetValue(
   const WCHAR *pColumnName,
   const ctype& data) throw( );
```

#### <a name="parameters"></a>Parametreler

*CType*<br/>
'ndaki Özel işleme gerektiren dize türleri (`CHAR*`, `WCHAR*`) dışında herhangi bir veri türünü işleyen şablonlu bir parametre. `GetValue`, burada belirttiğiniz alana göre uygun veri türünü kullanır.

*pColumnName*<br/>
'ndaki Sütun adını içeren bir karakter dizesinin işaretçisi.

*verileri*<br/>
'ndaki Verileri içeren bellek işaretçisi.

*Nsütun*<br/>
'ndaki Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütununa başvurur.

### <a name="return-value"></a>Dönüş Değeri

Dize verileri ayarlamak istiyorsanız, `GetValue`şablonlu olmayan sürümlerini kullanın. Bu yöntemin şablonlu olmayan sürümleri, belirtilen sütun verilerini içeren arabelleğin kısmına işaret eden `void*`döndürür. Sütun bulunmazsa NULL değerini döndürür.

Diğer tüm veri türleri için `GetValue`şablonlu sürümlerinin kullanılması daha basittir. Şablonlu sürümler başarılı veya hatalı hata durumunda **false** **değerini döndürür.**

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)