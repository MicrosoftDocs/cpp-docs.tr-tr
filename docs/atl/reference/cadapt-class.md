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
ms.openlocfilehash: 1bae98663b8dc2b09efeff9139e8d028abcd862e
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168845"
---
# <a name="cadapt-class"></a>CAdapt Sınıfı

Bu şablon, nesnenin adresi dışında bir öğe döndürmek üzere address-of işlecini yeniden tanımlayan sınıfları sarmalamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class CAdapt
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Uyarlanmış tür.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Cadavpt:: Cabapt](#cadapt)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAdapt:: operator const T&](#operator_const_t_amp)|Öğesine `m_T`bir **const** başvurusu döndürür.|
|[CAdapt:: operator T&](#operator_t_amp)|Öğesine `m_T`bir başvuru döndürür.|
|[CAdapt:: operator <](#operator_lt)|Uyarılmış türdeki bir nesneyi ile `m_T`karşılaştırır.|
|[CAdapt:: operator =](#operator_eq)|Uyartype nesnesinin bir nesnesini öğesine `m_T`atar.|
|[CAdapt:: operator = =](#operator_eq_eq)|Uyarılmış türdeki bir nesneyi ile `m_T`karşılaştırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[Cadadpt:: m_T](#m_t)|Uyarlanan veri.|

## <a name="remarks"></a>Açıklamalar

`CAdapt`, sınıfının adresini (`operator &`) yeniden tanımlayan sınıfları nesnenin adresi dışında bir şey döndürecek şekilde kaydırmak için kullanılan basit bir şablondur. Bu sınıfların örnekleri, ATL `CComBSTR`'in, `CComPtr`, ve `CComQIPtr` sınıflarının yanı sıra derleyicinin com destek sınıfını içerir. `_com_ptr_t` Bu sınıflar, veri üyelerinden birinin adresini (söz konusu durumda `CComBSTR`bir BSTR ve diğer sınıfların durumunda bir arabirim işaretçisi) döndürmek için tüm adres işlecini yeniden tanımlayarak.

`CAdapt`birincil rolü, sınıf *T*tarafından tanımlanan adres işlecinin gizlenme, ancak yine de, bu sınıfın özelliklerini korumalarıdır. `CAdapt`Bu rolü, bir genel üyeyi, *t*türü [m_T](#m_t)tutarak, dönüştürme işleçlerini, karşılaştırma işleçlerini ve bir kopya Oluşturucu tanımlayarak, *t*türünde nesneler gibi değerlendirilmelerini `CAdapt` sağlamak üzere tanımlayın.

Bazı kapsayıcı stili `CAdapt` sınıflar, içerdiği nesnelerin adreslerini Address-of işlecini kullanarak elde edebileceğinden, bağdaştırıcı sınıfı faydalıdır. İşlecin adresinin yeniden tanımlanması, genellikle derleme hatalarına neden olacak ve bunun "çalışmasını" bekleyen sınıfların uyarlanmamış türünün kullanımını önleyecek şekilde bu gereksinimi bozabilir. `CAdapt`Bu sorunları çözmek için bir yol sağlar.

Genellikle, bir kapsayıcı stili `CAdapt` sınıfta, `CComBSTR` `CComPtr` `CComQIPtr`, veya `_com_ptr_t` nesnelerini depolamak istediğinizde kullanırsınız. Bu, c++ 11 standardı desteği olmadan önce C++ standart kitaplığı kapsayıcıları için en yaygın olarak gereklidir, ancak C++ 11 standart kitaplık kapsayıcıları, aşırı yüklenmiş `operator&()`türlerle otomatik olarak çalışır. Standart Kitaplık, nesnelerin doğru adreslerini almak için [std:: AddressOf](../../standard-library/memory-functions.md#addressof) kullanarak bu bunu dahili olarak alır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcomclı. h

## <a name="cadaptcadapt"></a><a name="cadapt"></a>Cadavpt:: Cabapt

Oluşturucular, bir bağdaştırıcı nesnesinin varsayılan olarak oluşturulmasını, bir tür nesnesinden kopyalanmasını veya başka bir bağdaştırıcı nesnesinden kopyalanmasını sağlar.

```cpp
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Yeni oluşturulan bağdaştırıcı nesnesine kopyalanmak üzere uyarlanmakta olan türde bir değişken.

*rSrCA*<br/>
Veri içeren bir bağdaştırıcı nesnesi yeni oluşturulan bağdaştırıcı nesnesine kopyalanmalı (veya taşınacak).

## <a name="cadaptm_t"></a><a name="m_t"></a>Cadadpt:: m_T

Uyarlanmakta olan verileri tutar.

```cpp
T m_T;
```

### <a name="remarks"></a>Açıklamalar

Bu **genel** veri üyesine doğrudan veya dolaylı olarak, [sabit t&](#operator_const_t_amp) ve [işleç T&](#operator_t_amp)ile erişilebilir.

## <a name="cadaptoperator-const-tamp"></a><a name="operator_const_t_amp"></a>CAdapt:: operator const T&amp;

[M_T](#m_t) üyesine bir **const** başvurusu döndürür ve bu, bağdaştırıcı nesnesinin *T*türünde bir nesne gibi işlenmesine izin verir.

```cpp
operator const T&() const;
```

### <a name="return-value"></a>Dönüş Değeri

İçin **const** `m_T`bir const başvurusu.

## <a name="cadaptoperator-tamp"></a><a name="operator_t_amp"></a>CAdapt:: operator T&amp;

[M_T](#m_t) üyesine bir başvuru döndürür ve bu, bağdaştırıcı nesnesinin *T*türünde bir nesne gibi işlenmesine izin verir.

```cpp
operator T&();
```

### <a name="return-value"></a>Dönüş Değeri

Öğesine `m_T`bir başvuru.

## <a name="cadaptoperator-lt"></a><a name="operator_lt"></a>CAdapt:: işleci&lt;

Uyarılmış türdeki bir nesneyi [m_T](#m_t)karşılaştırır.

```cpp
bool operator<(const T& rSrc) const;
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Karşılaştırılacak nesneye bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Ve `m_T` *RSRC*arasındaki Karşılaştırmanın sonucu.

## <a name="cadaptoperator-"></a><a name="operator_eq"></a>CAdapt:: operator =

Atama işleci, *RSRC*bağımsız değişkenini veri üyesine [m_T](#m_t) atar ve geçerli bağdaştırıcı nesnesini döndürür.

```cpp
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Kopyalanacak uyarlamatürünün nesnesine bir başvuru.

*rSrCA*<br/>
Taşınacak bir nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru.

## <a name="cadaptoperator-"></a><a name="operator_eq_eq"></a>CAdapt:: operator = =

Uyarılmış türdeki bir nesneyi [m_T](#m_t)karşılaştırır.

```cpp
bool operator== (const T& rSrc) const;
```

### <a name="parameters"></a>Parametreler

*rSrc*<br/>
Karşılaştırılacak nesneye bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

*M_T* ve *RSRC*arasındaki Karşılaştırmanın sonucu.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
