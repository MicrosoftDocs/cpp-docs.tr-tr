---
title: CComSafeArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArray class
ms.assetid: ee349aef-33db-4c85-bd08-5d86a3c9d53a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 920cfbde9229131c5148c359f6a82ce002d7fb3a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758524"
---
# <a name="ccomsafearray-class"></a>CComSafeArray sınıfı

Bu sınıf için bir sarmalayıcı olan `SAFEARRAY` yapısı.

## <a name="syntax"></a>Sözdizimi

```
template <typename T, VARTYPE _vartype = _ATL_AutomationType<T>::type>
class CComSafeArray
```

#### <a name="parameters"></a>Parametreler

*T*  
Dizide depolanan verinin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeArray::CComSafeArray](#ccomsafearray)|Oluşturucu.|
|[CComSafeArray:: ~ CComSafeArray](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeArray::Add](#add)|Bir veya daha fazla öğe ekler veya `SAFEARRAY` yapısı için bir `CComSafeArray`.|
|[CComSafeArray::Attach](#attach)|Bağlanan bir `SAFEARRAY` için yapı bir `CComSafeArray` nesne.|
|[CComSafeArray::CopyFrom](#copyfrom)|İçeriğini kopyalar bir `SAFEARRAY` içine yapısı `CComSafeArray` nesne.|
|[CComSafeArray::CopyTo](#copyto)|Bir kopyasını oluşturur `CComSafeArray` nesne.|
|[CComSafeArray::Create](#create)|Oluşturur bir `CComSafeArray` nesne.|
|[CComSafeArray::Destroy](#destroy)|Yok eder bir `CComSafeArray` nesne.|
|[CComSafeArray::Detach](#detach)|Ayırır bir `SAFEARRAY` gelen bir `CComSafeArray` nesne.|
|[CComSafeArray::GetAt](#getat)|Tek boyutlu bir diziden tek bir öğe alır.|
|[CComSafeArray::GetCount](#getcount)|Dizideki öğelerin sayısını döndürür.|
|[CComSafeArray::GetDimensions](#getdimensions)|Dizi boyut sayısını verir.|
|[CComSafeArray::GetLowerBound](#getlowerbound)|Belirli bir boyut dizinin alt sınırını döndürür.|
|[CComSafeArray::GetSafeArrayPtr](#getsafearrayptr)|Adresini döndürür `m_psa` veri üyesi.|
|[CComSafeArray::GetType](#gettype)|Dizide depolanan verilerin türünü döndürür.|
|[CComSafeArray::GetUpperBound](#getupperbound)|Dizinin her boyutunun üst sınırını döndürür.|
|[CComSafeArray::IsSizable](#issizable)|Testleri bir `CComSafeArray` nesne yeniden boyutlandırılabilir.|
|[CComSafeArray::MultiDimGetAt](#multidimgetat)|Tek bir öğe, çok boyutlu bir dizi alır.|
|[CComSafeArray::MultiDimSetAt](#multidimsetat)|Çok boyutlu bir dizi bir öğenin değerini ayarlar.|
|[CComSafeArray::Resize](#resize)|Yeniden boyutlandırır bir `CComSafeArray` nesne.|
|[CComSafeArray::SetAt](#setat)|Tek boyutlu bir dizi bir öğenin değerini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeArray::operator LPSAFEARRAY](#operator_lpsafearray)|Değerine çevirir bir `SAFEARRAY` işaretçi.|
|[CComSafeArray::operator\[\]](ccomsafearray-class.md#operator_at)|Öğe diziden alır.|
|[CComSafeArray::operator =](#operator_eq)|Atama işleci.|  

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComSafeArray::m_psa](#m_psa)|Bu veri üyesinin adresini tutar `SAFEARRAY` yapısı.|

## <a name="remarks"></a>Açıklamalar

`CComSafeArray` için sarmalayıcı sağlar [SAFEARRAY'i veri türü](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearray) sınıfı, oluşturma ve yönetme tek ve çok boyutlu diziler neredeyse türlerinden herhangi birinin değişken desteklenen ibarettir kolaylaştırır.

`CComSafeArray` işlemler arasında dizileri geçirme basitleştirir ve ayrıca dizi dizini değerlerini karşı üst ve alt sınırlarını denetleyerek ek güvenlik sağlar.

Alt sınırı bir `CComSafeArray` herhangi bir kullanıcı tanımlı değerinde başlayabilirsiniz; Bununla birlikte, C++ erişilen bir dizi alt sınırı 0 kullanmanız gerekir. Visual Basic gibi diğer diller, sınırlayıcı diğer değerleri (örneğin, -10-10) kullanabilir.

Kullanım [CComSafeArray::Create](#create) oluşturmak için bir `CComSafeArray` nesnesi ve [CComSafeArray::Destroy](#destroy) silmek için.

A `CComSafeArray` aşağıdaki alt VARIANT veri türü içerebilir:

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
|VT_VARIANT BEKLENİYORDU|değişken işaretçisi|
|VT_CY|Currency veri türü|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsafe.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#75](../../atl/codesnippet/cpp/ccomsafearray-class_1.cpp)]

##  <a name="add"></a>  CComSafeArray::Add

Bir veya daha fazla öğe ekler veya `SAFEARRAY` yapısı için bir `CComSafeArray`.

```
HRESULT Add(const SAFEARRAY* psaSrc);
HRESULT Add(ULONG ulCount, const T* pT, BOOL bCopy = TRUE);
HRESULT Add(const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Parametreler

*psaSrc*  
Bir işaretçi bir `SAFEARRAY` nesne.

*ulCount*  
Diziye eklenecek nesne sayısı.

*PT*  
Diziye eklenecek bir veya daha fazla nesne işaretçisi.

*T*  
Diziye eklenecek nesne bir başvuru.

*bCopy*  
Verilerin bir kopyasını oluşturulması gerekip gerekmediğini gösterir. Varsayılan değer True'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Yeni nesneler varolan sonuna eklenir `SAFEARRAY` nesne. Bir nesne bir çok boyutlu görünümden ekleme `SAFEARRAY` nesne desteklenmiyor. Var olan bir nesne dizisidir eklerken, iki dizi aynı türde öğe içermelidir.

*BCopy* BSTR veya TÜREVLERİ türü öğeler için bir dizi eklendiğinde bayrağı dikkate alınır. Varsayılan değer true, diziye bir öğe eklendiğinde yeni bir kopya verilerinin yapılmasını sağlar.

##  <a name="attach"></a>  CComSafeArray::Attach

Bağlanan bir `SAFEARRAY` için yapı bir `CComSafeArray` nesne.

```
HRESULT Attach(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parametreler

*psaSrc*  
Bir işaretçi `SAFEARRAY` yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Ekler bir `SAFEARRAY` için yapı bir `CComSafeArray` nesne, var olan yapmadan `CComSafeArray` yöntemleri kullanılabilir.

##  <a name="ccomsafearray"></a>  CComSafeArray::CComSafeArray

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

*bağlı*  
A `SAFEARRAYBOUND` yapısı.

*ulCount*  
Dizideki öğelerin sayısı

*lLBound*  
Alt sınır değeri; diğer bir deyişle, dizideki ilk öğenin dizini.

*pBound*  
Bir işaretçi bir `SAFEARRAYBOUND` yapısı.

*uDims*  
Dizideki boyutların sayısı.

*saSrc*  
Bir başvuru bir `SAFEARRAY` yapısı veya `CComSafeArray` nesne. Her iki durumda da, dizi oluşturma başvurulmuyor dizisinin bir kopyasını olmak için bu başvuru Oluşturucusu kullanır.

*psaSrc*  
Bir işaretçi bir `SAFEARRAY` yapısı. Oluşturucu, dizi oluşturma başvurulmuyor dizisinin bir kopyasını olmak için bu adresi kullanır.

### <a name="remarks"></a>Açıklamalar

Oluşturur bir `CComSafeArray` nesne.

##  <a name="dtor"></a>  CComSafeArray:: ~ CComSafeArray

Yıkıcı.

```
~CComSafeArray() throw()
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="copyfrom"></a>  CComSafeArray::CopyFrom

İçeriğini kopyalar bir `SAFEARRAY` içine yapısı `CComSafeArray` nesne.

```
HRESULT CopyFrom(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Parametreler

*ppArray*  
İşaretçi `SAFEARRAY` kopyalanacak.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem içeriğini kopyalar bir `SAFEARRAY` geçerli `CComSafeArray` nesne. Varolan bir dizinin içeriğini değiştirilir.

##  <a name="copyto"></a>  CComSafeArray::CopyTo

Bir kopyasını oluşturur `CComSafeArray` nesne.

```
HRESULT CopyTo(LPSAFEARRAY* ppArray);
```

### <a name="parameters"></a>Parametreler

*ppArray*  
Yeni bir konum için bir işaretçi `SAFEARRAY`.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem içeriğini kopyalar bir `CComSafeArray` içine nesnesi bir `SAFEARRAY` yapısı.

##  <a name="create"></a>  CComSafeArray::Create

Oluşturur bir `CComSafeArray`.

```
HRESULT Create(const SAFEARRAYBOUND* pBound, UINT uDims = 1);
HRESULT Create(ULONG ulCount = 0, LONG lLBound = 0);
```

### <a name="parameters"></a>Parametreler

*pBound*  
Bir işaretçi bir `SAFEARRAYBOUND` nesne.

*uDims*  
Dizideki boyutların sayısı.

*ulCount*  
Dizideki öğelerin sayısı

*lLBound*  
Alt sınır değeri; diğer bir deyişle, dizideki ilk öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

A `CComSafeArray` varolan bir nesne oluşturulabilir `SAFEARRAYBOUND` yapısı ve boyut ya da dizi ve alt sınırı içinde öğe sayısını belirterek sayı. Visual C++'tan erişilecek dizi ise, alt sınırı 0 olmalıdır. Diğer diller için alt sınırı (örneğin, -10-10 gibi bir aralıktaki öğeleri Visual temel destekler Diziler) diğer değerler izin verebilir.

##  <a name="destroy"></a>  CComSafeArray::Destroy

Yok eder bir `CComSafeArray` nesne.

```
HRESULT Destroy();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Var olan bir yok eder `CComSafeArray` nesne ve tüm verileri içerir.

##  <a name="detach"></a>  CComSafeArray::Detach

Ayırır bir `SAFEARRAY` gelen bir `CComSafeArray` nesne.

```
LPSAFEARRAY Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndüren bir `SAFEARRAY` nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ayırır `SAFEARRAY` nesnesinden `CComSafeArray` nesne.

##  <a name="getat"></a>  CComSafeArray::GetAt

Tek boyutlu bir diziden tek bir öğe alır.

```
T& GetAt(LONG lIndex) const;
```

### <a name="parameters"></a>Parametreler

*Dizin*  
Değeri döndürmek için dizide dizin sayısı.

### <a name="return-value"></a>Dönüş Değeri

Gerekli bir dizi öğesine bir başvuru döndürür.

##  <a name="getcount"></a>  CComSafeArray::GetCount

Dizideki öğelerin sayısını döndürür.

```
ULONG GetCount(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parametreler

*uDim*  
Dizi boyutu.

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Çok boyutlu bir dizi ile kullanıldığında, bu yöntem yalnızca belirli bir boyutunda öğelerin sayısını döndürür.

##  <a name="getdimensions"></a>  CComSafeArray::GetDimensions

Dizi boyut sayısını verir.

```
UINT GetDimensions() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizi boyut sayısını verir.

##  <a name="getlowerbound"></a>  CComSafeArray::GetLowerBound

Belirli bir boyut dizinin alt sınırını döndürür.

```
LONG GetLowerBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parametreler

*uDim*  
Dizi boyutu alt sınırı alınacağı. Atlanırsa, varsayılan değer 0'dır.

### <a name="return-value"></a>Dönüş Değeri

Alt sınır döndürür.

### <a name="remarks"></a>Açıklamalar

Alt sınırı 0 ise, bu öğe sayısı 0 olan ilk öğedir bir C benzeri dizisini gösterir. Bir hata olması durumunda, geçersiz bir boyut bağımsız değişken, örneğin, bu yöntemi çağırır. `AtlThrow` hatayı açıklayan bir HRESULT.

##  <a name="getsafearrayptr"></a>  CComSafeArray::GetSafeArrayPtr

Adresini döndürür `m_psa` veri üyesi.

```
LPSAFEARRAY* GetSafeArrayPtr() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi döndürür [CComSafeArray::m_psa](#m_psa) veri üyesi.

##  <a name="gettype"></a>  CComSafeArray::GetType

Dizide depolanan verilerin türünü döndürür.

```
VARTYPE GetType() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu türlerden birini olabilecek dizisinde depolanan verilerin türünü döndürür:

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
|VT_VARIANT BEKLENİYORDU|değişken işaretçisi|
|VT_CY|Currency veri türü|

##  <a name="getupperbound"></a>  CComSafeArray::GetUpperBound

Dizinin her boyutunun üst sınırını döndürür.

```
LONG GetUpperBound(UINT uDim = 0) const;
```

### <a name="parameters"></a>Parametreler

*uDim*  
Dizi boyut üst sınırı alınacağı. Atlanırsa, varsayılan değer 0'dır.

### <a name="return-value"></a>Dönüş Değeri

Üst sınırını döndürür. Bu değer (dahil), bu boyut en fazla geçerli dizini.

### <a name="remarks"></a>Açıklamalar

Bir hata olması durumunda, geçersiz bir boyut bağımsız değişken, örneğin, bu yöntemi çağırır. `AtlThrow` hatayı açıklayan bir HRESULT.

##  <a name="issizable"></a>  CComSafeArray::IsSizable

Testleri bir `CComSafeArray` nesne yeniden boyutlandırılabilir.

```
bool IsSizable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür `CComSafeArray` erişilemiyorsa, yanlış yeniden boyutlandırılabilir.

##  <a name="m_psa"></a>  CComSafeArray::m_psa

Adresini tutar `SAFEARRAY` erişilen yapısı.

```
LPSAFEARRAY m_psa;
```

##  <a name="multidimgetat"></a>  CComSafeArray::MultiDimGetAt

Tek bir öğe, çok boyutlu bir dizi alır.

```
HRESULT MultiDimGetAt(const LONG* alIndex, T& t);
```

### <a name="parameters"></a>Parametreler

*alIndex*  
Dizideki her boyut için dizinleri oluşan bir vektörü işaretçisi. En soldaki (en önemli) boyutu `alIndex[0]`.

*T*  
Döndürülen veriler bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

##  <a name="multidimsetat"></a>  CComSafeArray::MultiDimSetAt

Çok boyutlu bir dizi bir öğenin değerini ayarlar.

```
HRESULT MultiDimSetAt(const LONG* alIndex, const T& t);
```

### <a name="parameters"></a>Parametreler

*alIndex*  
Dizideki her boyut için dizinleri oluşan bir vektörü işaretçisi. Sağdaki (en az önemli) boyutu `alIndex`[0].

*T*  
Yeni öğenin değerini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu çok boyutlu bir sürümü olduğu [CComSafeArray::SetAt](#setat).

##  <a name="operator_at"></a>  CComSafeArray::operator \[\]

Öğe diziden alır.

```
T& operator[](long lindex) const;
T& operator[]int nindex) const;
```

### <a name="parameters"></a>Parametreler

*Dizin, nIndex*  
Dizi içindeki gerekli öğe dizini sayısı.

### <a name="return-value"></a>Dönüş Değeri

Uygun bir dizi öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Benzer bir işlevi gerçekleştiren [CComSafeArray::GetAt](#getat), ancak bu işleç, yalnızca tek boyutlu diziler ile çalışır.

##  <a name="operator_eq"></a>  CComSafeArray::operator =

Atama işleci.

```
ATL::CComSafeArray<T>& operator=(const ATL::CComSafeArray& saSrc);
ATL::CComSafeArray<T>& operator=(const SAFEARRAY* psaSrc);
```

### <a name="parameters"></a>Parametreler

*saSrc*  
Bir başvuru bir `CComSafeArray` nesne.

*psaSrc*  
Bir işaretçi bir `SAFEARRAY` nesne.

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan verilerin türünü döndürür.

##  <a name="operator_lpsafearray"></a>  CComSafeArray::operator LPSAFEARRAY

Değerine çevirir bir `SAFEARRAY` işaretçi.

```
operator LPSAFEARRAY() const;
```

### <a name="return-value"></a>Dönüş Değeri

Değerine çevirir bir `SAFEARRAY` işaretçi.

##  <a name="resize"></a>  CComSafeArray::Resize

Yeniden boyutlandırır bir `CComSafeArray` nesne.

```
HRESULT Resize(const SAFEARRAYBOUND* pBound);
HRESULT Resize(ULONG ulCount, LONG lLBound = 0);
```

### <a name="parameters"></a>Parametreler

*pBound*  
Bir işaretçi bir `SAFEARRAYBOUND` öğe sayısını ve bir dizi alt sınırı hakkında bilgi içeren yapısı.

*ulCount*  
Yeniden boyutlandırılan dizisindeki nesnelere istenen sayısı.

*lLBound*  
Alt sınır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, yalnızca en sağdaki boyutu yeniden boyutlandırır. Dönüş diziler boyutlandırılmayacağını `IsResizable` FALSE olarak.

##  <a name="setat"></a>  CComSafeArray::SetAt

Tek boyutlu bir dizi bir öğenin değerini ayarlar.

```
HRESULT SetAt(LONG lIndex, const T& t, BOOL bCopy = TRUE);
```

### <a name="parameters"></a>Parametreler

*Dizin*  
Ayarlanacak dizi öğesinin dizin numarası.

*T*  
Belirtilen öğenin yeni değeri.

*bCopy*  
Verilerin bir kopyasını oluşturulması gerekip gerekmediğini gösterir. Varsayılan değer True'dur.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

*BCopy* BSTR veya TÜREVLERİ türü öğeler için bir dizi eklendiğinde bayrağı dikkate alınır. Varsayılan değer true, diziye bir öğe eklendiğinde yeni bir kopya verilerinin yapılmasını sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[SAFEARRAY veri türü](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagsafearray)   
[CComSafeArray::Create](#create)   
[CComSafeArray::Destroy](#destroy)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
