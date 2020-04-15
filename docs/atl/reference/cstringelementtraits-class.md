---
title: CStringElementTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
ms.openlocfilehash: 078cfd5ff93bfcd8acc747904ea05e6a2e762bc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330617"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits Sınıfı

Bu sınıf, nesneleri depolayan `CString` toplama sınıfları tarafından kullanılan statik işlevler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)|(Statik) Eşitlik için iki dize öğesini karşılaştırmak için bu işlevi arayın.|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Statik) İki dize öğesini karşılaştırmak için bu işlevi arayın.|
|[CStringElementTraits::CopyElements](#copyelements)|(Statik) Koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak `CString` için bu işlevi çağırın.|
|[CStringElementTraits::Karma](#hash)|(Statik) Verilen dize öğesi için karma değeri hesaplamak için bu işlevi çağırın.|
|[CStringElementTraits::RelocateElements](#relocateelements)|(Statik) Koleksiyon sınıfı nesnesinde depolanan öğeleri taşımak `CString` için bu işlevi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, dizeleri kopyalamak, taşımak ve karşılaştırmak ve karma değer oluşturmak için statik işlevler sağlar. Bu işlevler, dize tabanlı verileri depolamak için bir koleksiyon sınıfı kullanırken yararlıdır. Büyük/küçük harf duyarsız karşılaştırmalar gerektiğinde [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) kullanın. Dize nesneleri başvuru olarak ele alınacaksa [CStringRefElementTraits'ı](../../atl/reference/cstringrefelementtraits-class.md) kullanın.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** cstringt.h

## <a name="cstringelementtraitscompareelements"></a><a name="compareelements"></a>CStringElementTraits::CompareElements

Eşitlik için iki dize öğesini karşılaştırmak için bu statik işlevi çağırın.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğeler eşitse doğru döndürür, aksi takdirde yanlış.

## <a name="cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered

İki dize öğesini karşılaştırmak için bu statik işlevi çağırın.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizeleri aynı ysa sıfır, *str1* str2'den küçükse 0 < veya *str1* *str2'den*büyükse 0'>. *str2* Karşılaştırmaları gerçekleştirmek için [CStringT::Karşılaştır](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi kullanılır.

## <a name="cstringelementtraitscopyelements"></a><a name="copyelements"></a>CStringElementTraits::CopyElements

Bir koleksiyon sınıfı `CString` nesnesinde depolanan öğeleri kopyalamak için bu statik işlevi çağırın.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
Kopyalanan verileri alacak ilk öğeyi işaretle.

*pSrc*<br/>
Kopyalanması gereken ilk öğeyi işaretçi.

*nElements*<br/>
Kopyalanması gereken öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef öğeleri çakışmamalıdır.

## <a name="cstringelementtraitshash"></a><a name="hash"></a>CStringElementTraits::Karma

Verilen dize öğesi için karma değeri hesaplamak için bu statik işlevi çağırın.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dize içeriğini kullanarak hesaplanan karma değeri döndürür.

## <a name="cstringelementtraitsinargtype"></a><a name="inargtype"></a>CStringElementTraits::INARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsoutargtype"></a><a name="outargtype"></a>CStringElementTraits::OUTARGTYPE

Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a>CStringElementTraits::RelocateElements

Bir koleksiyon sınıfı `CString` nesnesinde depolanan öğeleri taşımak için bu statik işlevi çağırın.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
Taşınan verileri alacak ilk öğeyi işaretçi.

*pSrc*<br/>
Taşınmak için ilk öğeyi işaretçi.

*nElements*<br/>
Taşınacak öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Bu statik işlev, çoğu veri türü için yeterli olan [memmove'u](../../c-runtime-library/reference/memmove-wmemmove.md)çağırır. Taşınan nesneler kendi üyelerine işaretçiler içeriyorsa, bu statik işlevin geçersiz kılınması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CElementTraitsBase Sınıfı](../../atl/reference/celementtraitsbase-class.md)<br/>
[CStringElementTraitsI Sınıfı](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
