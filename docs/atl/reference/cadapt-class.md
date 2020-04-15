---
title: CAdapt Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
ms.openlocfilehash: 23544bc103de0d7b76cd73d403626ba93af6e31a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321635"
---
# <a name="cadapt-class"></a>CAdapt Sınıfı

Bu şablon, nesnenin adresi dışında bir öğe döndürmek üzere address-of işlecini yeniden tanımlayan sınıfları sarmalamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CAdapt
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Uyarlanmış tür.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAdapt::CAdapt](#cadapt)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAdapt::operatör const T&](#operator_const_t_amp)|Const **const** başvurusu `m_T`verir.|
|[CAdapt::operatör T&](#operator_t_amp)|Bir başvuru `m_T`verir.|
|[CAdapt::operatör <](#operator_lt)|Uyarlanmış türdeki bir nesneyi `m_T`.|
|[CAdapt::operator =](#operator_eq)|Uyarlanmış türden bir nesne `m_T`atar.|
|[CAdapt::operatör ==](#operator_eq_eq)|Uyarlanmış türdeki bir nesneyi `m_T`.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAdapt::m_T](#m_t)|Uyarlanan veri.|

## <a name="remarks"></a>Açıklamalar

`CAdapt`nesnenin adresi dışında bir şey döndürmek için işlecinin adresini yeniden`operator &`tanımlayan sınıfları sarmak için kullanılan basit bir şablondur. Bu tür sınıflara örnek `CComBSTR`olarak `CComPtr`ATL'ler ve `CComQIPtr` sınıflar ve `_com_ptr_t`derleyici COM destek sınıfı verilebilir. Bu sınıflar, veri üyelerinden birinin adresini (örneğin `CComBSTR`bstr ve diğer sınıflarda bir arabirim işaretçisi) döndürmek için işlecinin adresini yeniden tanımlar.

`CAdapt`'birincil rolü sınıf *T*tarafından tanımlanan işleci adresi gizlemek için, ama yine de uyarlanmış sınıfın özelliklerini korumaktır. `CAdapt`bir kamu üyesi tutarak bu rolü yerine getirir, [m_T,](#m_t) *T*türü, ve dönüşüm operatörleri, karşılaştırma operatörleri `CAdapt` tanımlayarak, karşılaştırma operatörleri, ve bir kopya oluşturucu onlar *t*tipi nesneleri gibi davranılması için uzmanlıklar izin vermek .

Bazı kapsayıcı `CAdapt` stili sınıfları işleç adresini kullanarak kendi içerdiği nesnelerin adreslerini elde etmek mümkün olmasını bekliyoruz bağdaştırıcı sınıfı yararlıdır. İşlecin adresinin yeniden tanımlanması, genellikle derleme hatalarına neden olacak ve bunun "çalışmasını" bekleyen sınıfların uyarlanmamış türünün kullanımını önleyecek şekilde bu gereksinimi bozabilir. `CAdapt`bu sorunları aşmak için bir yol sağlar.

Genellikle, kapsayıcı tarzı `CAdapt` bir sınıfta `CComBSTR`, `CComPtr` `CComQIPtr`, `_com_ptr_t` nesneleri depolamak istediğinizde kullanırsınız. Bu, C++11 Standardını desteklemeden önce C++ Standart Kitaplık kapsayıcıları için en yaygın olarak gerekliydi, ancak `operator&()`C++11 Standart Kitaplık kapsayıcıları aşırı yüklenmiş türlerle otomatik olarak çalışır. Standart Kitaplık bunu, nesnelerin gerçek adreslerini almak için [std::addressof](../../standard-library/memory-functions.md#addressof) kullanarak başarır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomcli.h

## <a name="cadaptcadapt"></a><a name="cadapt"></a>CAdapt::CAdapt

Oluşturucular, bağdaştırıcı nesnesinin varsayılan olarak oluşturulmasına, uyarlanan türden bir nesneden kopyalanmasını veya başka bir bağdaştırıcı nesnesinden kopyalanmasını sağlar.

```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Yeni oluşturulan bağdaştırıcı nesneye kopyalanacak şekilde uyarlanan türden bir değişken.

*rSrCA*<br/>
İçerdiği verileri yeni oluşturulan bağdaştırıcı nesnesine kopyalanmış (veya taşınmış) bir bağdaştırıcı nesnesi.

## <a name="cadaptm_t"></a><a name="m_t"></a>CAdapt::m_T

Uyarlanan verileri tutar.

```
T m_T;
```

### <a name="remarks"></a>Açıklamalar

Bu **genel** veri üyesine doğrudan veya dolaylı olarak [operatör const T&](#operator_const_t_amp) ve operatör T [&](#operator_t_amp)ile ulaşılabilir.

## <a name="cadaptoperator-const-tamp"></a><a name="operator_const_t_amp"></a>CAdapt::operatör const T&amp;

Bağdaştırıcı nesnesinin *T*türündeki bir nesnegibi davranılmasına izin veren [m_T](#m_t) üyeye **const** bir başvuru verir.

```
operator const T&() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir **const** `m_T`referans .

## <a name="cadaptoperator-tamp"></a><a name="operator_t_amp"></a>CAdapt::operatör T&amp;

Bağdaştırıcı nesnesinin *T*türündeki bir nesne gibi davranılmasına izin veren [m_T](#m_t) üyeye bir başvuru verir.

```
operator T&();
```

### <a name="return-value"></a>Dönüş Değeri

Bir referans `m_T`.

## <a name="cadaptoperator-lt"></a><a name="operator_lt"></a>CAdapt::operatör&lt;

Uyarlanmış türdeki bir nesneyi [m_T](#m_t)ile karşılaştırır.

```
bool operator<(const T& rSrc) const;
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Karşılaştırılacak nesneye bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

ve *rSrc* `m_T` arasında karşılaştırma sonucu .

## <a name="cadaptoperator-"></a><a name="operator_eq"></a>CAdapt::operator =

Atama işleci, m_T veri [üyesine](#m_t) bağımsız değişken, *rSrc*atar ve geçerli bağdaştırıcı nesnesini döndürür.

```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Kopyalanacak uyarlanmış türdeki bir nesneye başvuru.

*rSrCA*<br/>
Taşınacak bir nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru.

## <a name="cadaptoperator-"></a><a name="operator_eq_eq"></a>CAdapt::operatör ==

Uyarlanmış türdeki bir nesneyi [m_T](#m_t)ile karşılaştırır.

```
bool operator== (const T& rSrc) const;
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Karşılaştırılacak nesneye bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

*m_T* ve *rSrc*arasındaki karşılaştırmasonucu .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
