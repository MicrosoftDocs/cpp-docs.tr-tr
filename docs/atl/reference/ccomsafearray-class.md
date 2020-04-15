---
title: CComSafeArray Sınıfı
ms.date: 05/06/2019
f1_keywords:
- CComSafeArray
- ATLSAFE/ATL::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::CComSafeArray
- ATLSAFE/ATL::CComSafeArray::Add
- ATLSAFE/ATL::CComSafeArray::Attach
- ATLSAFE/ATL::CComSafeArray::CopyFrom
- ATLSAFE/ATL::CComSafeArray::CopyTo
- ATLSAFE/ATL::CComSafeArray::Create
- ATLSAFE/ATL::CComSafeArray::Destroy
- ATLSAFE/ATL::CComSafeArray::Detach
- ATLSAFE/ATL::CComSafeArray::GetAt
- ATLSAFE/ATL::CComSafeArray::GetCount
- ATLSAFE/ATL::CComSafeArray::GetDimensions
- ATLSAFE/ATL::CComSafeArray::GetLowerBound
- ATLSAFE/ATL::CComSafeArray::GetSafeArrayPtr
- ATLSAFE/ATL::CComSafeArray::GetType
- ATLSAFE/ATL::CComSafeArray::GetUpperBound
- ATLSAFE/ATL::CComSafeArray::IsSizable
- ATLSAFE/ATL::CComSafeArray::MultiDimGetAt
- ATLSAFE/ATL::CComSafeArray::MultiDimSetAt
- ATLSAFE/ATL::CComSafeArray::Resize
- ATLSAFE/ATL::CComSafeArray::SetAt
- ATLSAFE/ATL::CComSafeArray::m_psa
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
ms.openlocfilehash: d1e72d364858ea31541d574ed77bdc8ccca7d748
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327395"
---
# <a name="ccomsafearray-class"></a>CComSafeArray Sınıfı

Bu sınıf `SAFEARRAY` yapı için bir sarmalayıcıdır.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Dizide depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomsafeArray::CcomsafeArray](#ccomsafearray)|Oluşturucu.|
|[CcomsafeArray::~CcomsafeArray](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomSafeArray::Ekle](#add)|Bir veya daha fazla `SAFEARRAY` öğe veya `CComSafeArray`yapı ekler.|
|[CcomSafeArray::Ekle](#attach)|Bir nesneye `SAFEARRAY` `CComSafeArray` bir yapı bağlar.|
|[CcomSafeArray::CopyFrom](#copyfrom)|Bir `SAFEARRAY` yapının içeriğini nesneye `CComSafeArray` kopyalar.|
|[CcomsafeArray::Copyto](#copyto)|Nesnenin `CComSafeArray` bir kopyasını oluşturur.|
|[CcomSafeArray::Oluştur](#create)|Bir `CComSafeArray` nesnesi oluşturur.|
|[CComSafeArray::Destroy](#destroy)|Bir `CComSafeArray` nesneyi yok eder.|
|[CComSafeArray::Detach](#detach)|Bir `SAFEARRAY` `CComSafeArray` nesneyi ayırın.|
|[CcomsafeArray::Getat](#getat)|Tek boyutlu bir diziden tek bir öğe alır.|
|[CcomSafeArray::GetCount](#getcount)|Dizideki öğe sayısını döndürür.|
|[CcomSafeArray::GetDimensions](#getdimensions)|Dizideki boyut sayısını verir.|
|[CcomsafeArray::GetLowerBound](#getlowerbound)|Dizinin belirli bir boyutu için alt sınırı döndürür.|
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|Veri üyesinin `m_psa` adresini verir.|
|[CcomSafeArray::GetType](#gettype)|Dizide depolanan veri türünü döndürür.|
|[CcomsafeArray::GetupperBound](#getupperbound)|Dizinin herhangi bir boyutu için üst sınırı döndürür.|
|[CComSafeArray::IsSizable](#issizable)|Bir `CComSafeArray` nesne yeniden boyutlandırılabilirse sınar.|
|[CcomsafeArray::multidimgetat](#multidimgetat)|Çok boyutlu bir diziden tek bir öğe alır.|
|[CcomsafeArray::multidimsetat](#multidimsetat)|Çok boyutlu bir dizideki bir öğenin değerini ayarlar.|
|[CComSafeArray::Yeniden boyutlandırma](#resize)|Nesneyi `CComSafeArray` yeniden boyutlandırıyor.|
|[CcomsafeArray::Setat](#setat)|Tek boyutlu bir dizideki bir öğenin değerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CComSafeArray::operatör LPSAFEARRAY](#operator_lpsafearray)|Bir `SAFEARRAY` işaretçiye değer atar.|
|[CComSafeArray::operatör\[\]](ccomsafearray-class.md#operator_at)|Diziden bir öğe alır.|
|[CComSafeArray::operatör =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComSafeArray::m_psa](#m_psa)|Bu veri üyesi `SAFEARRAY` yapının adresini tutar.|

## <a name="remarks"></a>Açıklamalar

`CComSafeArray`[SAFEARRAY Veri Türü](/windows/win32/api/oaidl/ns-oaidl-safearray) sınıfı için bir sarmalayıcı sağlar ve varyant destekli türlerin hemen hemen herhangi birinin tek ve çok boyutlu dizilerinin oluşturulmasını ve yönetilmesini basit bir mesele haline getirir.

`CComSafeArray`işlemler arasında geçen dizileri kolaylaştırır ve buna ek olarak dizi dizi değerlerini üst ve alt sınırlara göre denetleyerek ekstra güvenlik sağlar.

Bir alt sınır `CComSafeArray` herhangi bir kullanıcı tanımlı değerde başlatılabilir; ancak, C++ üzerinden erişilen diziler 0'ın alt sınırını kullanmalıdır. Visual Basic gibi diğer diller diğer sınırlayıcı değerleri (örneğin, -10-10) kullanabilir.

[CComSafeArray kullanın::Bir](#create) `CComSafeArray` nesne oluşturmak için oluştur ve [CComSafeArray::Destroy](#destroy) silmek için.

A, `CComSafeArray` VARIANT veri türlerinin aşağıdaki alt kümesini içerebilir:

|Vartype|Açıklama|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|uzun süre|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|Ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|ondalık işaretçi|
|VT_VARIANT|varyant işaretçisi|
|Vt_cy|Currency veri türü|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsafe.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

## <a name="ccomsafearrayadd"></a><a name="add"></a>CcomSafeArray::Ekle

Bir veya daha fazla `SAFEARRAY` öğe veya `CComSafeArray`yapı ekler.

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Parametreler

*psaSrc*<br/>
Bir `SAFEARRAY` nesneye işaretçi.

*ulCount*<br/>
Diziye eklenecek nesne sayısı.

*Pt*<br/>
Diziye eklenecek bir veya daha fazla nesneye işaretçi.

*T*<br/>
Diziye eklenecek nesneye bir başvuru.

*bFotokopi*<br/>
Verilerin bir kopyasının oluşturulup oluşturulmayacağını gösterir. Varsayılan değer TRUE'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Yeni nesneler varolan `SAFEARRAY` nesnenin sonuna eklenir. Çok boyutlu `SAFEARRAY` bir nesneye nesne eklemek desteklenmez. Varolan bir nesne dizisi eklerken, her iki dizi de aynı türde öğeler içermelidir.

BSTR veya VARIANT türü öğeleri bir diziye eklendiğinde *bCopy* bayrağı dikkate alınır. TRUE'nun varsayılan değeri, öğe diziye eklendiğinde yeni bir kopyanın verilerden yapılmasını sağlar.

## <a name="ccomsafearrayattach"></a><a name="attach"></a>CcomSafeArray::Ekle

Bir nesneye `SAFEARRAY` `CComSafeArray` bir yapı bağlar.

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parametreler

*psaSrc*<br/>
Yapıiçin `SAFEARRAY` bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bir `SAFEARRAY` `CComSafeArray` nesneye bir yapı bağlar `CComSafeArray` ve varolan yöntemleri kullanılabilir hale getirir.

## <a name="ccomsafearrayccomsafearray"></a><a name="ccomsafearray"></a>CcomsafeArray::CcomsafeArray

Oluşturucu.

```
CComSafeArray();
CComSafeArray(const SAFEARRAYBOUND& bound);
CComSafeArray(ULONG  ulCount, LONG lLBound = 0);
CComSafeArray(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
CComSafeArray(const CComSafeArray& saSrc);
CComSafeArray(const SAFEARRAY& saSrc);
CComSafeArray(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parametreler

*Bağlı*<br/>
Bir `SAFEARRAYBOUND` yapı.

*ulCount*<br/>
Dizideki öğelerin sayısı

*lLBound*<br/>
Alt sınır değeri; diğer bir deyişle, dizideki ilk öğenin dizini.

*pBound*<br/>
Bir yapıiçin `SAFEARRAYBOUND` bir işaretçi.

*uDims*<br/>
Dizideki boyut sayısı.

*saSrc*<br/>
Bir `SAFEARRAY` yapı ya `CComSafeArray` da nesneye başvuru. Her iki durumda da oluşturucu dizinin bir kopyasını yapmak için bu başvuruyu kullanır, bu nedenle dizi inşaattan sonra başvurulmez.

*psaSrc*<br/>
Bir yapıiçin `SAFEARRAY` bir işaretçi. Oluşturucu dizinin bir kopyasını oluşturmak için bu adresi kullanır, bu nedenle dizi inşaattan sonra başvurulmez.

### <a name="remarks"></a>Açıklamalar

Bir `CComSafeArray` nesnesi oluşturur.

## <a name="ccomsafearrayccomsafearray"></a><a name="dtor"></a>CcomsafeArray::~CcomsafeArray

Yıkıcı.

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="ccomsafearraycopyfrom"></a><a name="copyfrom"></a>CcomSafeArray::CopyFrom

Bir `SAFEARRAY` yapının içeriğini nesneye `CComSafeArray` kopyalar.

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Parametreler

*ppArray*<br/>
İşaretçi `SAFEARRAY` kopyalamak için.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir `SAFEARRAY` nesnenin içeriğini `CComSafeArray` geçerli nesneye kopyalar. Dizinin varolan içeriği değiştirilir.

## <a name="ccomsafearraycopyto"></a><a name="copyto"></a>CcomsafeArray::Copyto

Nesnenin `CComSafeArray` bir kopyasını oluşturur.

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Parametreler

*ppArray*<br/>
Yeni `SAFEARRAY`oluşturmak için bir konuma işaretçi .

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir `CComSafeArray` nesnenin içeriğini `SAFEARRAY` bir yapıya kopyalar.

## <a name="ccomsafearraycreate"></a><a name="create"></a>CcomSafeArray::Oluştur

Bir `CComSafeArray`.

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>Parametreler

*pBound*<br/>
Bir `SAFEARRAYBOUND` nesneye işaretçi.

*uDims*<br/>
Dizideki boyut sayısı.

*ulCount*<br/>
Dizideki öğelerin sayısı

*lLBound*<br/>
Alt sınır değeri; diğer bir deyişle, dizideki ilk öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bir `CComSafeArray` nesne varolan `SAFEARRAYBOUND` bir yapıdan ve boyut sayısından veya dizideki ve alt sınırdaki öğe sayısını belirterek oluşturulabilir. Diziye C++'dan erişilecekse, alt sınır 0 olmalıdır. Diğer diller alt sınır için diğer değerlere izin verebilir (örneğin, Visual Basic -10 ile 10 gibi aralıklı dizileri destekler).

## <a name="ccomsafearraydestroy"></a><a name="destroy"></a>CComSafeArray::Destroy

Bir `CComSafeArray` nesneyi yok eder.

```
HRESULT Destroy();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Varolan `CComSafeArray` bir nesneyi ve içerdiği tüm verileri yok eder.

## <a name="ccomsafearraydetach"></a><a name="detach"></a>CComSafeArray::Detach

Bir `SAFEARRAY` `CComSafeArray` nesneyi ayırın.

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi `SAFEARRAY` nesneye döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem nesneyi `SAFEARRAY` `CComSafeArray` nesneden ayırır.

## <a name="ccomsafearraygetat"></a><a name="getat"></a>CcomsafeArray::Getat

Tek boyutlu bir diziden tek bir öğe alır.

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>Parametreler

*Lindex*<br/>
Döndürülecek dizideki değerin dizin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Gerekli dizi öğesine bir başvuru verir.

## <a name="ccomsafearraygetcount"></a><a name="getcount"></a>CcomSafeArray::GetCount

Dizideki öğe sayısını döndürür.

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parametreler

*uDim*<br/>
Dizi boyutu.

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Çok boyutlu bir dizi ile kullanıldığında, bu yöntem yalnızca belirli bir boyuttaki öğe sayısını döndürecektir.

## <a name="ccomsafearraygetdimensions"></a><a name="getdimensions"></a>CcomSafeArray::GetDimensions

Dizideki boyut sayısını verir.

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki boyut sayısını verir.

## <a name="ccomsafearraygetlowerbound"></a><a name="getlowerbound"></a>CcomsafeArray::GetLowerBound

Dizinin belirli bir boyutu için alt sınırı döndürür.

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parametreler

*uDim*<br/>
Alt sınırı almak için dizi boyutu. Atlanırsa, varsayılan değer 0'dır.

### <a name="return-value"></a>Dönüş Değeri

Alt sınırı döndürür.

### <a name="remarks"></a>Açıklamalar

Alt sınır 0 ise, bu, ilk öğesi 0 öğesi olan C benzeri bir dizigösterir. Bir hata durumunda, örneğin, geçersiz bir boyut bağımsız değişkeni, bu yöntem hatayı açıklayan bir HRESULT ile çağırır. `AtlThrow`

## <a name="ccomsafearraygetsafearrayptr"></a><a name="getsafearrayptr"></a>CComSafeArray::GetSafeArrayPtr

Veri üyesinin `m_psa` adresini verir.

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi [CComSafeArray::m_psa](#m_psa) veri üyesine döndürür.

## <a name="ccomsafearraygettype"></a><a name="gettype"></a>CcomSafeArray::GetType

Dizide depolanan veri türünü döndürür.

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan ve aşağıdaki türlerden herhangi biri olabilecek veri türünü döndürür:

|Vartype|Açıklama|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|uzun süre|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|Ulonglong|
|VT_R4|float|
|VT_R8|double|
|VT_DECIMAL|ondalık işaretçi|
|VT_VARIANT|varyant işaretçisi|
|Vt_cy|Currency veri türü|

## <a name="ccomsafearraygetupperbound"></a><a name="getupperbound"></a>CcomsafeArray::GetupperBound

Dizinin herhangi bir boyutu için üst sınırı döndürür.

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parametreler

*uDim*<br/>
Üst sınırı almak için dizi boyutu. Atlanırsa, varsayılan değer 0'dır.

### <a name="return-value"></a>Dönüş Değeri

Üst sınırı döndürür. Bu değer kapsayıcıdır, bu boyut için en büyük geçerli dizin.

### <a name="remarks"></a>Açıklamalar

Bir hata durumunda, örneğin, geçersiz bir boyut bağımsız değişkeni, bu yöntem hatayı açıklayan bir HRESULT ile çağırır. `AtlThrow`

## <a name="ccomsafearrayissizable"></a><a name="issizable"></a>CComSafeArray::IsSizable

Bir `CComSafeArray` nesne yeniden boyutlandırılabilirse sınar.

```
bool IsSizable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeniden boyutlandırılabiliyorsa `CComSafeArray` DOĞRU döndürür, yapamıyorsa FALSE.

## <a name="ccomsafearraym_psa"></a><a name="m_psa"></a>CComSafeArray::m_psa

Erişilen yapının `SAFEARRAY` adresini tutar.

```
LPSAFEARRAY m_psa;
```

## <a name="ccomsafearraymultidimgetat"></a><a name="multidimgetat"></a>CcomsafeArray::multidimgetat

Çok boyutlu bir diziden tek bir öğe alır.

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>Parametreler

*alIndex*<br/>
Dizideki her boyut için dizinvektörü işaretçi. En sol (en önemli) `alIndex[0]`boyuttur.

*T*<br/>
Döndürülen verilere bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="ccomsafearraymultidimsetat"></a><a name="multidimsetat"></a>CcomsafeArray::multidimsetat

Çok boyutlu bir dizideki bir öğenin değerini ayarlar.

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>Parametreler

*alIndex*<br/>
Dizideki her boyut için dizinvektörü işaretçi. En doğru (en az `alIndex`anlamlı) boyut [0]'dır.

*T*<br/>
Yeni öğenin değerini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu CComSafeArray çok boyutlu bir [sürümüdür::SetAt](#setat).

## <a name="ccomsafearrayoperator-"></a><a name="operator_at"></a>CComSafeArray::operatör\[\]

Diziden bir öğe alır.

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>Parametreler

*lIndex, nIndex*<br/>
Dizide gerekli öğenin dizin numarası.

### <a name="return-value"></a>Dönüş Değeri

Uygun dizi öğesini döndürür.

### <a name="remarks"></a>Açıklamalar

CComSafeArray benzer bir işlev [gerçekleştirir::GetAt,](#getat)ancak bu işleç sadece tek boyutlu diziler ile çalışır.

## <a name="ccomsafearrayoperator-"></a><a name="operator_eq"></a>CComSafeArray::operatör =

Atama işleci.

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parametreler

*saSrc*<br/>
Bir `CComSafeArray` nesneye başvuru.

*psaSrc*<br/>
Bir `SAFEARRAY` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan veri türünü döndürür.

## <a name="ccomsafearrayoperator-lpsafearray"></a><a name="operator_lpsafearray"></a>CComSafeArray::operatör LPSAFEARRAY

Bir `SAFEARRAY` işaretçiye değer atar.

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `SAFEARRAY` işaretçiye değer atar.

## <a name="ccomsafearrayresize"></a><a name="resize"></a>CComSafeArray::Yeniden boyutlandırma

Nesneyi `CComSafeArray` yeniden boyutlandırıyor.

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>Parametreler

*pBound*<br/>
Öğelerin sayısı `SAFEARRAYBOUND` ve bir dizinin alt sınırı hakkında bilgi içeren bir yapıiçin işaretçi.

*ulCount*<br/>
Yeniden boyutlandırılmış dizide istenen nesne sayısı.

*lLBound*<br/>
Alt sınır.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca en doğru boyutu yeniden boyutlandırıyor. FALSE olarak dönen `IsResizable` dizileri yeniden boyutlandırmaz.

## <a name="ccomsafearraysetat"></a><a name="setat"></a>CcomsafeArray::Setat

Tek boyutlu bir dizideki bir öğenin değerini ayarlar.

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Parametreler

*Lindex*<br/>
Ayarlanan dizi öğesinin dizin sayısı.

*T*<br/>
Belirtilen öğenin yeni değeri.

*bFotokopi*<br/>
Verilerin bir kopyasının oluşturulup oluşturulmayacağını gösterir. Varsayılan değer TRUE'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

BSTR veya VARIANT türü öğeleri bir diziye eklendiğinde *bCopy* bayrağı dikkate alınır. TRUE'nun varsayılan değeri, öğe diziye eklendiğinde yeni bir kopyanın verilerden yapılmasını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[SAFEARRAY Veri Türü](/windows/win32/api/oaidl/ns-oaidl-safearray)<br/>
[CcomSafeArray::Oluştur](#create)<br/>
[CComSafeArray::Destroy](#destroy)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
