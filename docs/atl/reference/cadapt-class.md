---
title: CAdapt sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs:
- C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 13a04f9ba199205d84d94b9b3792c4bafb570319
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766496"
---
# <a name="cadapt-class"></a>CAdapt sınıfı

Bu şablon, nesnenin adresi dışında bir öğe döndürmek üzere address-of işlecini yeniden tanımlayan sınıfları sarmalamak için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
template <class T>  
class CAdapt
```

#### <a name="parameters"></a>Parametreler

*T*  
Uyarlanmış tür.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAdapt::CAdapt](#cadapt)|Oluşturucu.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAdapt::operator const T &](#operator_const_t_amp)|Döndürür bir **const** başvurusu `m_T`.|
|[CAdapt::operator T &](#operator_t_amp)|Bir başvuru döndürür `m_T`.|
|[CAdapt::operator <](#operator_lt)|İle uyarlanmış türde bir nesneyi karşılaştırır `m_T`.|
|[CAdapt::operator =](#operator_eq)|İçin uyarlanmış türde bir nesne atar `m_T`.|
|[CAdapt::operator ==](#operator_eq_eq)|İle uyarlanmış türde bir nesneyi karşılaştırır `m_T`.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CAdapt::m_T](#m_t)|Uyarlanan veri.|

## <a name="remarks"></a>Açıklamalar

`CAdapt` address-of işlecini yeniden tanımlayan sınıfları sarmalamak için kullanılan basit bir şablonu (`operator &`) nesnenin adresi dışında bir şey dönün. Tür sınıfların örnekleri arasında ATL `CComBSTR`, `CComPtr`, ve `CComQIPtr` sınıfları ve derleyici COM destek sınıfı `_com_ptr_t`. Bu sınıfların tümü veri üyelerinden birinin adresini döndürmek için address-of işlecini yeniden tanımlayan (durumunda BSTR `CComBSTR`ve diğer sınıflar bir arabirim işaretçisi).

`CAdapt`kullanıcının birincil rolü, sınıf tarafından tanımlanan address-of işleci gizlemek için *T*, ancak uyarlanmış sınıfın özelliklerini hala korur. `CAdapt` Bu rol, bir ortak üye tutarak fulfils [m_T](#m_t), türü *T*ve dönüştürme işleçleri, karşılaştırma işleçlerini ve kopya Oluşturucu uzmanlıkları izin verecek şekilde tanımlayarak `CAdapt` olması türündeki nesneler oldukları gibi kabul *T*.

Bağdaştırıcı sınıfı `CAdapt` bazı container-style sınıflarının address-of işlecini kullanarak kapsanan nesnelerinin adreslerini alabilmesi faydalıdır. İşlecin adresinin yeniden tanımlanması, genellikle derleme hatalarına neden olacak ve bunun "çalışmasını" bekleyen sınıfların uyarlanmamış türünün kullanımını önleyecek şekilde bu gereksinimi bozabilir. `CAdapt` Bu sorunların geçici bir yol sağlar.

Genellikle, kullanacağınız `CAdapt` depolamak istediğinizde `CComBSTR`, `CComPtr`, `CComQIPtr`, veya `_com_ptr_t` nesnelerini kapsayıcı stili bir sınıfta. Bu en yaygın olarak C++ Standart Kitaplığı kapsayıcıları önceki C ++ 11 standardı desteği için gerekli, ancak C ++ 11 standart kitaplığı kapsayıcıları, aşırı yüklenmiş türleri ile otomatik olarak iş `operator&()`. Standart kitaplık bunu dahili olarak kullanarak sağlar. [std::addressof](../../standard-library/memory-functions.md#addressof) nesnelerin doğru adreslerini almak için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcomcli.h

##  <a name="cadapt"></a>  CAdapt::CAdapt

Oluşturucular bağdaştırıcısı nesneyi oluşturulmuş, uyarlanmış türde bir nesneden kopyaladığınız veya başka bir bağdaştırıcı nesneden kopyaladığınız varsayılan olmasına izin verin.

```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*rSrc*  
Yeni oluşturulan bağdaştırıcısı nesnesine kopyalanacak uyarlanan türünde bir değişken.

*rSrCA*  
Kapsanan verisini kopyalanamaz (yeni oluşturulmuş bağdaştırıcı nesnesine veya taşınamaz) bir bağdaştırıcı nesne.

##  <a name="m_t"></a>  CAdapt::m_T

Uyarlanan veri tutar.

```
T m_T;
```

### <a name="remarks"></a>Açıklamalar

Bu **genel** veri üyesinin erişilebilir doğrudan veya dolaylı olarak ile [işleci const T &](#operator_const_t_amp) ve [işleci T &](#operator_t_amp).

##  <a name="operator_const_t_amp"></a>  CAdapt::operator const T&amp;

Döndürür bir **const** başvurusu [m_T](#m_t) bağdaştırıcısı nesnesini bir nesne türü değilmiş gibi kabul edilmesi izin verme, üye *T*.

```  
operator const T&() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** başvurusu `m_T`.

##  <a name="operator_t_amp"></a>  CAdapt::operator T&amp;

Bir başvuru döndürür [m_T](#m_t) bağdaştırıcısı nesnesini bir nesne türü değilmiş gibi kabul edilmesi izin verme, üye *T*.

```  
operator T&();
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru `m_T`.

##  <a name="operator_lt"></a>  CAdapt::operator &lt;

İle uyarlanmış türde bir nesneyi karşılaştırır [m_T](#m_t).

```
bool operator<(const T& rSrc) const;
```

### <a name="parameters"></a>Parametreler

*rSrc*  
Karşılaştırılacak nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırmanın sonucu `m_T` ve *rSrc*.

##  <a name="operator_eq"></a>  CAdapt::operator =

Atama işleci bağımsız değişkeni atar *rSrc*, veri üyesine [m_T](#m_t) ve geçerli bağdaştırıcısı nesnesini döndürür.

```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```

### <a name="parameters"></a>Parametreler

*rSrc*  
Kopyalanacak uyarlanmış türde bir nesneye başvuru. 

*rSrCA* taşınacak bir nesneye bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesneye bir başvuru.

##  <a name="operator_eq_eq"></a>  CAdapt::operator ==

İle uyarlanmış türde bir nesneyi karşılaştırır [m_T](#m_t).

```
bool operator== (const T& rSrc) const;
```

### <a name="parameters"></a>Parametreler

*rSrc*  
Karşılaştırılacak nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırmanın sonucu *m_T* ve *rSrc*.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
