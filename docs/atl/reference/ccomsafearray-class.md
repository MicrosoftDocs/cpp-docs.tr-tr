---
title: CComSafeArray sınıfı
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
ms.openlocfilehash: 36750990dc62d5b24cf1107ac8a2724df787a47d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496988"
---
# <a name="ccomsafearray-class"></a>CComSafeArray sınıfı

Bu sınıf, `SAFEARRAY` yapı için bir sarmalayıcıdır.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Dizide depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeArray:: CComSafeArray](#ccomsafearray)|Oluşturucu.|
|[CComSafeArray:: ~ CComSafeArray](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeArray:: Add](#add)|' A `SAFEARRAY` `CComSafeArray`bir veya daha fazla öğe veya bir yapı ekler.|
|[CComSafeArray:: Attach](#attach)|Bir `CComSafeArray` nesneye `SAFEARRAY` bir yapı ekler.|
|[CComSafeArray:: CopyFrom](#copyfrom)|Bir `SAFEARRAY` yapının`CComSafeArray` içeriğini nesnesine kopyalar.|
|[CComSafeArray:: CopyTo](#copyto)|`CComSafeArray` Nesnenin bir kopyasını oluşturur.|
|[CComSafeArray:: Create](#create)|Bir `CComSafeArray` nesnesi oluşturur.|
|[CComSafeArray::D estroy](#destroy)|Bir `CComSafeArray` nesneyi yok eder.|
|[CComSafeArray::D etach](#detach)|Nesnesinden`CComSafeArray` bir `SAFEARRAY` ayırır.|
|[CComSafeArray:: GetAt](#getat)|Tek boyutlu diziden tek bir öğe alır.|
|[CComSafeArray:: GetCount](#getcount)|Dizideki öğe sayısını döndürür.|
|[CComSafeArray:: GetDimensions](#getdimensions)|Dizideki boyutların sayısını döndürür.|
|[CComSafeArray:: Getpın sınırı](#getlowerbound)|Dizinin belirli bir boyutu için alt sınır döndürür.|
|[CComSafeArray:: GetSafeArrayPtr](#getsafearrayptr)|`m_psa` Veri üyesinin adresini döndürür.|
|[CComSafeArray:: GetType](#gettype)|Dizide depolanan veri türünü döndürür.|
|[CComSafeArray:: Getüstsınırı](#getupperbound)|Dizinin herhangi bir boyutu için üst sınırı döndürür.|
|[CComSafeArray:: ıssizable](#issizable)|Bir `CComSafeArray` nesnenin yeniden boyutlandırılabileceğini sınar.|
|[CComSafeArray:: MultiDimGetAt](#multidimgetat)|Çok boyutlu bir diziden tek bir öğe alır.|
|[CComSafeArray:: MultiDimSetAt](#multidimsetat)|Çok boyutlu bir dizideki bir öğenin değerini ayarlar.|
|[CComSafeArray:: Resize](#resize)|Bir `CComSafeArray` nesneyi yeniden boyutlandırır.|
|[CComSafeArray:: SetAt](#setat)|Tek boyutlu dizideki bir öğenin değerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeArray:: operator LPSAFEARRAY](#operator_lpsafearray)|Bir `SAFEARRAY` işaretçiye değer yayınlar.|
|[CComSafeArray:: işleci\[\]](ccomsafearray-class.md#operator_at)|Diziden bir öğe alır.|
|[CComSafeArray:: operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeArray:: m_psa](#m_psa)|Bu veri üyesi `SAFEARRAY` yapının adresini tutar.|

## <a name="remarks"></a>Açıklamalar

`CComSafeArray`[SAFEARRAY veri türü](/windows/win32/api/oaidl/ns-oaidl-tagsafearray) sınıfı için bir sarmalayıcı sağlar ve bu, değişken olarak desteklenen türlerin neredeyse her birinde tek ve çok boyutlu diziler oluşturup yönetmeniz basit bir işlemdir.

`CComSafeArray`süreçler arasında dizileri geçirmeyi basitleştirir ve ayrıca, dizi dizini değerlerini üst ve alt sınırlara göre denetleyerek ek güvenlik sağlar.

Öğesinin `CComSafeArray` alt sınırı, Kullanıcı tanımlı herhangi bir değerle başlayabilir; ancak, üzerinden C++ erişilen diziler 0 alt sınırını kullanmalıdır. Visual Basic gibi diğer diller, diğer sınırlayıcı değerleri kullanabilir (örneğin,-10 ila 10).

[CComSafeArray:: Create](#create) komutunu kullanarak bir `CComSafeArray` nesne oluşturun ve [CComSafeArray::D estroy](#destroy) öğesini silin.

`CComSafeArray` , Değişken veri türlerinin aşağıdaki alt kümesini içerebilir:

|VARTYPE|Açıklama|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ULONGLONG|
|VT_R4|float|
|VT_R8|çift|
|VT_DECIMAL|ondalık işaretçi|
|VT_VARIANT|varyant işaretçisi|
|VT_CY|Currency veri türü|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsafe. h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

##  <a name="add"></a>CComSafeArray:: Add

' A `SAFEARRAY` `CComSafeArray`bir veya daha fazla öğe veya bir yapı ekler.

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Parametreler

*psaSrc*<br/>
Bir `SAFEARRAY` nesne işaretçisi.

*ulCount*<br/>
Diziye eklenecek nesne sayısı.

*Yönergelerinin*<br/>
Diziye eklenecek bir veya daha fazla nesneye yönelik bir işaretçi.

*şı*<br/>
Diziye eklenecek nesneye bir başvuru.

*bCopy*<br/>
Verilerin kopyasının oluşturulup oluşturulmayacağını gösterir. Varsayılan değer TRUE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Yeni nesneler varolan `SAFEARRAY` nesnenin sonuna eklenir. Çok boyutlu `SAFEARRAY` bir nesneye nesne ekleme desteklenmiyor. Varolan bir nesne dizisi eklenirken her iki dizi de aynı türde öğeler içermelidir.

BSTR veya VARIANT türündeki öğeler bir diziye eklendiğinde *bCopy* bayrağı dikkate alınır. Varsayılan TRUE değeri, öğe diziye eklendiğinde verilerin yeni bir kopyasının yapılmasını sağlar.

##  <a name="attach"></a>CComSafeArray:: Attach

Bir `CComSafeArray` nesneye `SAFEARRAY` bir yapı ekler.

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parametreler

*psaSrc*<br/>
`SAFEARRAY` Yapıya yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

`CComSafeArray` `CComSafeArray` Bir nesneye bir Yapıeklervemevcut`SAFEARRAY` yöntemleri kullanılabilir hale getirir.

##  <a name="ccomsafearray"></a>CComSafeArray:: CComSafeArray

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

*bağlı*<br/>
Bir `SAFEARRAYBOUND` yapı.

*ulCount*<br/>
Dizideki öğelerin sayısı

*Llsınırlanan*<br/>
Alt sınır değeri; diğer bir deyişle, dizideki ilk öğenin dizini.

*PUP*<br/>
Bir `SAFEARRAYBOUND` yapıya yönelik işaretçi.

*uDims*<br/>
Dizideki boyutların sayısı.

*saSrc*<br/>
Bir `SAFEARRAY` yapıya veya `CComSafeArray` nesneye bir başvuru. Her iki durumda da, oluşturucunun dizinin bir kopyasını oluşturmak için bu başvuruyu kullanması durumunda, dizi oluşturulduktan sonra başvuruya başvurulmaz.

*psaSrc*<br/>
Bir `SAFEARRAY` yapıya yönelik işaretçi. Oluşturucu, dizinin bir kopyasını oluşturmak için bu adresi kullanır, bu nedenle diziye oluşturulduktan sonra başvurulmaz.

### <a name="remarks"></a>Açıklamalar

Bir `CComSafeArray` nesnesi oluşturur.

##  <a name="dtor"></a>CComSafeArray:: ~ CComSafeArray

Yok edicisi.

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="copyfrom"></a>CComSafeArray:: CopyFrom

Bir `SAFEARRAY` yapının`CComSafeArray` içeriğini nesnesine kopyalar.

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Parametreler

*ppArray*<br/>
`SAFEARRAY` Kopyalanacak yapılacak işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, öğesinin `SAFEARRAY` içeriğini geçerli `CComSafeArray` nesneye kopyalar. Dizinin varolan içeriği değiştirilmiştir.

##  <a name="copyto"></a>CComSafeArray:: CopyTo

`CComSafeArray` Nesnenin bir kopyasını oluşturur.

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Parametreler

*ppArray*<br/>
Yeni `SAFEARRAY`' nin oluşturulacağı konuma yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir `CComSafeArray` nesnenin içeriğini bir `SAFEARRAY` yapıya kopyalar.

##  <a name="create"></a>CComSafeArray:: Create

`CComSafeArray`Oluşturur.

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>Parametreler

*PUP*<br/>
Bir `SAFEARRAYBOUND` nesne işaretçisi.

*uDims*<br/>
Dizideki boyutların sayısı.

*ulCount*<br/>
Dizideki öğelerin sayısı

*Llsınırlanan*<br/>
Alt sınır değeri; diğer bir deyişle, dizideki ilk öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bir `CComSafeArray` nesne varolan `SAFEARRAYBOUND` bir yapıdan ve boyut sayısından, dizideki öğe sayısı ve alt sınır belirtilerek oluşturulabilir. Diziye erişilmesi gerekiyorsa C++, alt sınır 0 olmalıdır. Diğer diller, alt sınır için diğer değerlere izin verebilir (örneğin, Visual Basic-10 ila 10 gibi bir aralığa sahip olan öğeleri içeren dizileri destekler).

##  <a name="destroy"></a>CComSafeArray::D estroy

Bir `CComSafeArray` nesneyi yok eder.

```
HRESULT Destroy();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Var olan `CComSafeArray` bir nesneyi ve içerdiği tüm verileri yok eder.

##  <a name="detach"></a>CComSafeArray::D etach

Nesnesinden`CComSafeArray` bir `SAFEARRAY` ayırır.

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>Dönüş Değeri

`SAFEARRAY` Nesnesine bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem nesneyi `CComSafeArray` nesnesinden `SAFEARRAY` ayırır.

##  <a name="getat"></a>CComSafeArray:: GetAt

Tek boyutlu diziden tek bir öğe alır.

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>Parametreler

*lIndex*<br/>
Döndürülecek dizideki değerin Dizin numarası.

### <a name="return-value"></a>Dönüş Değeri

Gerekli dizi öğesine bir başvuru döndürür.

##  <a name="getcount"></a>CComSafeArray:: GetCount

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

Çok boyutlu bir dizi ile kullanıldığında, bu yöntem yalnızca belirli boyuttaki öğe sayısını döndürür.

##  <a name="getdimensions"></a>CComSafeArray:: GetDimensions

Dizideki boyutların sayısını döndürür.

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki boyutların sayısını döndürür.

##  <a name="getlowerbound"></a>CComSafeArray:: Getpın sınırı

Dizinin belirli bir boyutu için alt sınır döndürür.

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parametreler

*uDim*<br/>
Alt sınırın alınacağı dizi boyutu. Atlanırsa varsayılan değer 0 ' dır.

### <a name="return-value"></a>Dönüş Değeri

Alt sınırı döndürür.

### <a name="remarks"></a>Açıklamalar

Alt sınır 0 ise bu, ilk öğesi öğe numarası 0 olan C benzeri bir diziyi gösterir. Bir hata durumunda, örneğin, geçersiz bir boyut bağımsız değişkeni olan bu yöntem, hatayı açıklayan bir `AtlThrow` HRESULT ile çağrı yapılır.

##  <a name="getsafearrayptr"></a>CComSafeArray:: GetSafeArrayPtr

`m_psa` Veri üyesinin adresini döndürür.

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>Dönüş Değeri

[CComSafeArray:: m_psa](#m_psa) veri üyesine yönelik bir işaretçi döndürür.

##  <a name="gettype"></a>CComSafeArray:: GetType

Dizide depolanan veri türünü döndürür.

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan veri türünü döndürür, bu şu türlerden herhangi biri olabilir:

|VARTYPE|Açıklama|
|-------------|-----------------|
|VT_I1|char|
|VT_I2|short|
|VT_I4|int|
|VT_I4|long|
|VT_I8|longlong|
|VT_UI1|byte|
|VT_UI2|ushort|
|VT_UI4|uint|
|VT_UI4|ulong|
|VT_UI8|ULONGLONG|
|VT_R4|float|
|VT_R8|çift|
|VT_DECIMAL|ondalık işaretçi|
|VT_VARIANT|varyant işaretçisi|
|VT_CY|Currency veri türü|

##  <a name="getupperbound"></a>CComSafeArray:: Getüstsınırı

Dizinin herhangi bir boyutu için üst sınırı döndürür.

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parametreler

*uDim*<br/>
Üst sınır alınacak dizi boyutu. Atlanırsa varsayılan değer 0 ' dır.

### <a name="return-value"></a>Dönüş Değeri

Üst sınırı döndürür. Bu değer, bu boyut için geçerli olan en yüksek dizin.

### <a name="remarks"></a>Açıklamalar

Bir hata durumunda, örneğin, geçersiz bir boyut bağımsız değişkeni olan bu yöntem, hatayı açıklayan bir `AtlThrow` HRESULT ile çağrı yapılır.

##  <a name="issizable"></a>CComSafeArray:: ıssizable

Bir `CComSafeArray` nesnenin yeniden boyutlandırılabileceğini sınar.

```
bool IsSizable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeniden boyutlandırılabiliyorsa `CComSafeArray` true, değilse false döndürür.

##  <a name="m_psa"></a>CComSafeArray:: m_psa

Erişilen `SAFEARRAY` yapının adresini tutar.

```
LPSAFEARRAY m_psa;
```

##  <a name="multidimgetat"></a>CComSafeArray:: MultiDimGetAt

Çok boyutlu bir diziden tek bir öğe alır.

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>Parametreler

*alIndex*<br/>
Dizideki her boyut için Dizin vektörünün işaretçisi. En soldaki (en önemli) Boyut `alIndex[0]`.

*şı*<br/>
Döndürülen verilere yönelik bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="multidimsetat"></a>CComSafeArray:: MultiDimSetAt

Çok boyutlu bir dizideki bir öğenin değerini ayarlar.

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>Parametreler

*alIndex*<br/>
Dizideki her boyut için Dizin vektörünün işaretçisi. En sağdaki (en az önemli) Boyut `alIndex`[0].

*ŞI*<br/>
Yeni öğenin değerini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu, [CComSafeArray:: SetAt](#setat)'in çok boyutlu bir sürümüdür.

##  <a name="operator_at"></a>CComSafeArray:: işleci\[\]

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

[CComSafeArray:: GetAt](#getat)için benzer bir işlev gerçekleştirir, ancak bu işleç yalnızca tek boyutlu dizilerle çalışır.

##  <a name="operator_eq"></a>CComSafeArray:: operator =

Atama işleci.

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parametreler

*saSrc*<br/>
Bir `CComSafeArray` nesneye başvuru.

*psaSrc*<br/>
Bir `SAFEARRAY` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan veri türünü döndürür.

##  <a name="operator_lpsafearray"></a>CComSafeArray:: operator LPSAFEARRAY

Bir `SAFEARRAY` işaretçiye değer yayınlar.

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `SAFEARRAY` işaretçiye değer yayınlar.

##  <a name="resize"></a>CComSafeArray:: Resize

Bir `CComSafeArray` nesneyi yeniden boyutlandırır.

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>Parametreler

*PUP*<br/>
Öğe sayısı ve bir `SAFEARRAYBOUND` dizinin alt sınırı hakkında bilgi içeren bir yapıya yönelik işaretçi.

*ulCount*<br/>
Yeniden boyutlandırılan dizide istenen nesne sayısı.

*Llsınırlanan*<br/>
Alt sınır.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca en sağdaki boyutu yeniden boyutlandırır. Yanlış olarak döndürülen `IsResizable` dizileri yeniden boyutlandıramaz.

##  <a name="setat"></a>CComSafeArray:: SetAt

Tek boyutlu dizideki bir öğenin değerini ayarlar.

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Parametreler

*lIndex*<br/>
Ayarlanacak dizi öğesinin dizin numarası.

*şı*<br/>
Belirtilen öğenin yeni değeri.

*bCopy*<br/>
Verilerin kopyasının oluşturulup oluşturulmayacağını gösterir. Varsayılan değer TRUE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

BSTR veya VARIANT türündeki öğeler bir diziye eklendiğinde *bCopy* bayrağı dikkate alınır. Varsayılan TRUE değeri, öğe diziye eklendiğinde verilerin yeni bir kopyasının yapılmasını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[SAFEARRAY veri türü](/windows/win32/api/oaidl/ns-oaidl-tagsafearray)<br/>
[CComSafeArray:: Create](#create)<br/>
[CComSafeArray::D estroy](#destroy)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
