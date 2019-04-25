---
title: CDynamicAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.CDynamicAccessor
- ATL::CDynamicAccessor
- CDynamicAccessor
- ATL::CDynamicAccessor::AddBindEntry
- AddBindEntry
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
- GetColumnFlags
- GetColumnInfo
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
ms.openlocfilehash: 19b8d0c86044e04cc60fd7aab89ec828c46f5fb9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209307"
---
# <a name="cdynamicaccessor-class"></a>CDynamicAccessor Sınıfı

Veritabanı şeması (veritabanı yapılarını) hiçbir bilgiye sahip olduğunda bir veri kaynağına erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDynamicAccessor : public CAccessorBase
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddBindEntry](#addbindentry)|Çıktı sütunları için varsayılan erişimciyi geçersiz kılma bir bağlama girişi ekler.|
|[CDynamicAccessor](#cdynamicaccessor)|Oluşturur ve başlatır `CDynamicAccessor` nesne.|
|[Kapat](#close)|Tüm sütunları bağlantısını keser, ayrılan belleği serbest bırakır ve serbest [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) sınıfında arabirim işaretçisi.|
|[GetBlobHandling](#getblobhandling)|Geçerli satırı için değer işleme BLOB alır.|
|[GetBlobSizeLimit](#getblobsizelimit)|En yüksek BLOB boyutu bayt cinsinden alır.|
|[GetBookmark](#getbookmark)|Geçerli satır için yer alır.|
|[GetColumnCount](#getcolumncount)|Satır kümesindeki sütunların sayısını alır.|
|[GetColumnFlags](#getcolumnflags)|Sütun özelliklerini alır.|
|[GetColumnInfo](#getcolumninfo)|Sütun meta verileri alır.|
|[GetColumnName](#getcolumnname)|Belirtilen sütunun adını alır.|
|[GetColumnType](#getcolumntype)|Belirtilen bir sütunun veri türünü alır.|
|[GetLength](#getlength)|Bir sütunun bayt cinsinden maksimum olası uzunluğu alır.|
|[GetOrdinal](#getordinal)|Bir sütun adı verilen sütun dizini alır.|
|[GetStatus](#getstatus)|Belirtilen sütun durumunu alır.|
|[GetValue](#getvalue)|Arabellekteki verileri alır.|
|[SetBlobHandling](#setblobhandling)|Geçerli satırı için değer işleme BLOB ayarlar.|
|[SetBlobSizeLimit](#setblobsizelimit)|En yüksek BLOB boyutu bayt cinsinden ayarlar.|
|[SetLength](#setlength)|Sütun uzunluğu bayt cinsinden ayarlar.|
|[SetStatus](#setstatus)|Belirtilen sütun durumunu ayarlar.|
|[SetValue](#setvalue)|Arabellek verilerini depolar.|

## <a name="remarks"></a>Açıklamalar

Kullanım `CDynamicAccessor` sütun adlarını, sütun sayısı, veri türü ve benzeri gibi sütun bilgisi edinmek için. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın.

Sütun bilgisi oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Veri arabelleği kullanımından elde [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md).

Bir tartışma ve dinamik erişimciyi sınıfları kullanma örnekleri için bkz: [Dinamik Erişimcileri Kullanma](../../data/oledb/using-dynamic-accessors.md).

## <a name="addbindentry"></a> CDynamicAccessor::AddBindEntry

Bir bağlama giriş çıkış sütunları ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();
```

#### <a name="parameters"></a>Parametreler

*Bilgileri*<br/>
[in] A `DBCOLUMNINFO` sütun bilgileri içeren yapısı. "DBCOLUMNINFO yapıları" bakın [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

İle oluşturulan bir varsayılan erişimci geçersiz kılarken bu yöntemi kullanmak `CDynamicAccessor` (bkz [nasıl yaparım veri getirme?](../../data/oledb/fetching-data.md)).

## <a name="cdynamicaccessor"></a> CDynamicAccessor::CDynamicAccessor

Oluşturur ve başlatır `CDynamicAccessor` nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,
   DBLENGTH nBlobSize = 8000);
```

#### <a name="parameters"></a>Parametreler

*eBlobHandling*<br/>
Nasıl işleneceğini ikili büyük nesne (BLOB) veri olduğunu belirtir. DBBLOBHANDLING_DEFAULT varsayılan değerdir. Bkz: [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) DBBLOBHANDLINGENUM değerlerin bir açıklaması.

*nBlobSize*<br/>
Bayt cinsinden en yüksek BLOB boyutu; sütun verileri bu değer üzerinde bir BLOB kabul edilir. 8000 varsayılan değerdir. Bkz: [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) Ayrıntılar için.

### <a name="remarks"></a>Açıklamalar

Başlatmak için oluşturucu kullanırsanız `CDynamicAccessor` nesnesi, BLOB'ları nasıl bağlayacaksınız belirtebilirsiniz. Bloblar, grafik, ses veya derlenmiş kod gibi ikili veriler içerebilir. Sütunları 8000 bayttan fazla Bloblar kabul ve bağlayabilir denemek için varsayılan davranıştır bir `ISequentialStream` nesne. Ancak, BLOB boyutu için farklı bir değer belirtebilirsiniz.

Belirtebilirsiniz nasıl `CDynamicAccessor` niteleyen BLOB veri sütunu veri işleme: varsayılan şekilde BLOB verilerini işleyebilir; bunu atlayabilirsiniz (bağlama) veya BLOB verilerini; bağlayabilirsiniz BLOB veri sağlayıcısı tarafından ayrılan bellek.

## <a name="close"></a> CDynamicAccessor::Close

Tüm sütunları bağlantısını keser, ayrılan belleği serbest bırakır ve serbest [IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) sınıfında arabirim işaretçisi.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close() throw();
```

## <a name="getblobhandling"></a> CDynamicAccessor::GetBlobHandling

Geçerli satırı için değer işleme BLOB alır.

### <a name="syntax"></a>Sözdizimi

```cpp
const DBBLOBHANDLINGENUM GetBlobHandling() const;
```

### <a name="remarks"></a>Açıklamalar

Değer işleme BLOB döndürür *eBlobHandling* tarafından ayarlanmış [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md).

## <a name="getblobsizelimit"></a> CDynamicAccessor::GetBlobSizeLimit

En yüksek BLOB boyutu bayt cinsinden alır.

### <a name="syntax"></a>Sözdizimi

```cpp
const DBLENGTH GetBlobSizeLimit() const;
```

### <a name="remarks"></a>Açıklamalar

Değer işleme BLOB döndürür *nBlobSize* tarafından ayarlanmış [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).

## <a name="getbookmark"></a> CDynamicAccessor::GetBookmark

Geçerli satır için yer alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetBookmark(CBookmark< >* pBookmark) const throw();
```

#### <a name="parameters"></a>Parametreler

*pBookmark*<br/>
[out] Bir işaretçi [CBookmark](../../data/oledb/cbookmark-class.md) nesne.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Ayarlanacak ihtiyacınız `DBPROP_IRowsetLocate` VARIANT_TRUE bir yer işareti almak için.

## <a name="getcolumncount"></a> CDynamicAccessor::GetColumnCount

Sütunların sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
DBORDINAL GetColumnCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Sütun sayısı aldı.

## <a name="getcolumnflags"></a> CDynamicAccessor::GetColumnFlags

Sütun özelliklerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetColumnFlags(DBORDINAL nColumn,
   DBCOLUMNFLAGS* pFlags) const throw();
```

#### <a name="parameters"></a>Parametreler

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

*pFlags*<br/>
[out] Sütun özelliklerini açıklayan bir bit maskesi için bir işaretçi. "DBCOLUMNFLAGS numaralandırılmış tür" bölümüne bakın [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** sütun özelliklerini başarıyla almışsa. Aksi halde **false**.

### <a name="remarks"></a>Açıklamalar

Sütun numarası bir uzaklık. Sütunun sıfır, bir özel durumdur; Bu, yer işareti varsa olur.

## <a name="getcolumninfo"></a> CDynamicAccessor::GetColumnInfo

Çoğu tüketiciler tarafından gerekli sütun meta verileri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetColumnInfo(IRowset* pRowset,
   DBORDINAL* pColumns,
   DBCOLUMNINFO** ppColumnInfo,
   OLECHAR** ppStringsBuffer) throw();
```

#### <a name="parameters"></a>Parametreler

*pRowset*<br/>
[in] Bir işaretçi [IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) arabirimi.

*pColumns*<br/>
[out] Hangi sütunların satır kümesi döndürmek bellekte bir işaretçi; varsa, bu sayı yer işareti sütunu içerir.

*ppColumnInfo*<br/>
[out] Bir dizi döndürülecek bellekte bir işaretçiye `DBCOLUMNINFO` yapıları. "DBCOLUMNINFO yapıları" bakın [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.

*ppStringsBuffer*<br/>
[out] Bellek, depolama, tüm dize değerleri için bir işaretçiyi döndürmek bir işaretçi (ya da içinde kullanılan adları *ColumnID* veya *pwszName*) tek bir ayırma bloğu içinde.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Bkz: [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu* veri türleri hakkında bilgi için `DBORDINAL`, `DBCOLUMNINFO`, ve `OLECHAR`.

## <a name="getcolumnname"></a> CDynamicAccessor::GetColumnName

Belirtilen sütunun adını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
LPOLESTR GetColumnName(DBORDINAL nColumn) const throw();
```

#### <a name="parameters"></a>Parametreler

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen sütunun adı.

## <a name="getcolumntype"></a> CDynamicAccessor::GetColumnType

Belirtilen bir sütunun veri türünü alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetColumnType(DBORDINAL nColumn,
   DBTYPE* pType) const throw();
```

#### <a name="parameters"></a>Parametreler

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

*pType*<br/>
[out] Belirtilen sütunun veri türü bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** başarı veya **false** başarısız.

## <a name="getlength"></a> CDynamicAccessor::GetLength

Belirtilen sütun uzunluğunu alır.

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

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

*pColumnName*<br/>
[in] Sütun adı içeren bir karakter dizesine bir işaretçi.

*pLength*<br/>
[out] Sütun bayt cinsinden uzunluğunu içeren bir tamsayı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** belirtilen sütun bulunursa. Aksi takdirde, bu işlevi döndürür **false**.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma sütun sayısını alır ve ANSI veya Unicode biçiminde sütun adı ikinci ve üçüncü geçersiz kılmalarını sırasıyla gerçekleştirin.

## <a name="getordinal"></a> CDynamicAccessor::GetOrdinal

Bir sütun adı verilen sütun sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool GetOrdinal(const CHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();

bool GetOrdinal(const WCHAR* pColumnName,
   DBORDINAL* pOrdinal) const throw();
```

#### <a name="parameters"></a>Parametreler

*pColumnName*<br/>
[in] Sütun adı içeren bir karakter dizesine bir işaretçi.

*pOrdinal*<br/>
[out] Sütun sayısı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** belirtilen ada sahip bir sütun bulunursa. Aksi takdirde, bu işlevi döndürür **false**.

## <a name="getstatus"></a> CDynamicAccessor::GetStatus

Belirtilen sütun durumunu alır.

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

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

*pColumnName*<br/>
[in] Sütun adı içeren bir karakter dizesine bir işaretçi.

*pStatus*<br/>
[out] Sütun durumu içeren değişken bir işaretçi. Bkz: [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) içinde *OLE DB Programcının Başvurusu* daha fazla bilgi için.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** belirtilen sütun bulunursa. Aksi takdirde, bu işlevi döndürür **false**.

## <a name="getvalue"></a> CDynamicAccessor::GetValue

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
[in] Herhangi bir veri türü dize türleri dışındaki işleme şablonlu bir parametre (`CHAR*`, `WCHAR*`), özel işlem gerektirir. `GetValue` ne burada belirttiğiniz üzerinde göre uygun veri türü kullanır.

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

*pColumnName*<br/>
[in] Sütun adı.

*pData*<br/>
[out] Belirtilen sütunun içeriğine işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dize verileri geçirmek istiyorsanız, şablonu oluşturulmamış sürümlerini kullanan `GetValue`. Şablonu oluşturulmamış sürümleri bu yöntemin dönüş `void*`, işaret ettiği bir parçası belirtilen sütun verileri içeren arabellek. Sütun bulunamazsa NULL değer döndürür.

Diğer tüm veri türleri için şablonlu sürümlerini kullanmak daha basit olduğundan `GetValue`. Şablonlu sürümleri dönüş **true** başarı veya **false** başarısız.

### <a name="remarks"></a>Açıklamalar

Şablonu oluşturulmamış sürümleri, dizeler ve diğer veri türleri içeren sütunlar için şablonlu sürümlerini içeren sütunlar döndürmek için kullanın.

Hata ayıklama modunda, bir onay alırsınız boyutunu *pData* işaret ettiği sütun boyutuna eşit olduğu.

## <a name="setblobhandling"></a> CDynamicAccessor::SetBlobHandling

Geçerli satırı için değer işleme BLOB ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);
```

#### <a name="parameters"></a>Parametreler

*eBlobHandling*<br/>
Nasıl ele alınması için BLOB verilerini olduğunu belirtir. Bunu yapmak için şu değerleri alabilir:

- DBBLOBHANDLING_DEFAULT: Sütun verileri büyük işlemek *nBlobSize* (tarafından ayarlanmış `SetBlobSizeLimit`) olarak BLOB veri ve arkasını almak bir `ISequentialStream` veya `IStream` nesne. Bu seçenek, büyük verileri içeren her bir sütun bağlamak çalışacak *nBlobSize* veya BLOB verisi olarak DBTYPE_IUNKNOWN olarak listelenir.

- DBBLOBHANDLING_NOSTREAMS: Sütun verileri büyük işlemek *nBlobSize* (tarafından ayarlanmış `SetBlobSizeLimit`) olarak BLOB veri ve tüketici ait, sağlayıcı tarafından ayrılan bellek başvurusu üzerinden alın. Bu seçenek birden fazla BLOB sütuna sahip tablolar için yararlıdır ve yalnızca bir sağlayıcının desteklediği `ISequentialStream` erişimci her nesne.

- DBBLOBHANDLING_SKIP: Atla (bağlama) Bloblarını içeren olarak niteleme sütunları (erişimci değil bağlama veya sütun değeri alabilir ancak sütununu durumunu ve uzunluğu hala alır).

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız `SetBlobHandling` çağırmadan önce `Open`.

Oluşturucu yöntemi [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) DBBLOBHANDLING_DEFAULT değerine işleme BLOB ayarlar.

## <a name="setblobsizelimit"></a> CDynamicAccessor::SetBlobSizeLimit

En yüksek BLOB boyutu bayt cinsinden ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
void SetBlobSizeLimit(DBLENGTH nBlobSize);
```

#### <a name="parameters"></a>Parametreler

*nBlobSize*<br/>
BLOB boyut sınırını belirtir.

### <a name="remarks"></a>Açıklamalar

En yüksek BLOB boyutu bayt cinsinden ayarlar; sütun verileri bu değerden daha büyük bir BLOB kabul edilir. Bazı sağlayıcıları (örneğin, 2 GB) sütunlar için son derece büyük boyutları sunar. Bu boyuttaki bir sütun için bellek ayırmaya çalışmak yerine, genellikle bu sütunların bloblar bağlama isteriz. Bu şekilde tüm bellek ayırmak gerekmez, ancak yine de kesilmesi, Korku olmadan tüm verileri okuyabilir. Ancak, istediğiniz zorlamak bazı durumlar vardır `CDynamicAccessor` büyük sütunları kendi yerel veri türlerinde bağlamak için. Bunu yapmak için `SetBlobSizeLimit` çağırmadan önce `Open`.

Oluşturucu yöntemi [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) en yüksek BLOB boyutu 8000 bayt varsayılan değerine ayarlar.

## <a name="setlength"></a> CDynamicAccessor::SetLength

Belirtilen sütun uzunluğunu ayarlar.

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

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

*nLength*<br/>
[in] Sütun bayt cinsinden uzunluğu.

*pColumnName*<br/>
[in] Sütun adı içeren bir karakter dizesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** belirtilen sütun uzunluğu başarılı bir şekilde ayarlanmışsa. Aksi takdirde, bu işlevi döndürür **false**.

## <a name="setstatus"></a> CDynamicAccessor::SetStatus

Belirtilen sütun durumunu ayarlar.

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

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

*Durumu*<br/>
[in] Sütun durumu. Bkz: [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) içinde *OLE DB Programcının Başvurusu* daha fazla bilgi için.

*pColumnName*<br/>
[in] Sütun adı içeren bir karakter dizesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** belirtilen sütun durumu başarılı bir şekilde ayarlanmış. Aksi takdirde, bu işlevi döndürür **false**.

## <a name="setvalue"></a> CDynamicAccessor::SetValue

Belirtilen sütun için verileri depolar.

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
[in] Herhangi bir veri türü dize türleri dışındaki işleme şablonlu bir parametre (`CHAR*`, `WCHAR*`), özel işlem gerektirir. `GetValue` ne burada belirttiğiniz üzerinde göre uygun veri türü kullanır.

*pColumnName*<br/>
[in] Sütun adı içeren bir karakter dizesine bir işaretçi.

*Veri*<br/>
[in] Veri içeren bellek işaretçisi.

*nColumn*<br/>
[in] Sütun numarası. Sütun numaraları 1 ile başlayın. 0 değeri, varsa, yer işareti sütunu, ifade eder.

### <a name="return-value"></a>Dönüş Değeri

Dize verileri ayarlamak istiyorsanız, şablonu oluşturulmamış sürümlerini kullanan `GetValue`. Şablonu oluşturulmamış sürümleri bu yöntemin dönüş `void*`, işaret ettiği bir parçası belirtilen sütun verileri içeren arabellek. Sütun bulunamazsa NULL değer döndürür.

Diğer tüm veri türleri için şablonlu sürümlerini kullanmak daha basit olduğundan `GetValue`. Şablonlu sürümleri dönüş **true** başarı veya **false** başarısız.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor Sınıfı](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor Sınıfı](../../data/oledb/cmanualaccessor-class.md)