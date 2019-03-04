---
title: CStringElementTraits sınıfı
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
ms.openlocfilehash: 80efd4dbc4ff0541e083ed61bed872d5e69c7a74
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261888"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits sınıfı

Statik işlevler depolama koleksiyon sınıfları tarafından kullanılan bu sınıfın sağladığı `CString` nesneleri.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)|(Statik) Eşitlik için iki dize öğeleri karşılaştırmak için bu işlevi çağırın.|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Statik) İki dize öğe karşılaştırmak için bu işlevi çağırın.|
|[CStringElementTraits::CopyElements](#copyelements)|(Statik) Kopyalamak için bu işlevi çağırın `CString` bir koleksiyon sınıfı nesnesinde saklanan öğe.|
|[CStringElementTraits::Hash](#hash)|(Statik) Verilen dize öğesi için bir karma değeri hesaplamak için bu işlevi çağırın.|
|[CStringElementTraits::RelocateElements](#relocateelements)|(Statik) Yeniden konumlandırmak için bu işlevi çağırın `CString` bir koleksiyon sınıfı nesnesinde saklanan öğe.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, kopyalama, taşıma ve dizeleri karşılaştırmak için ve bir karma değer oluşturmak için statik işlevler sağlar. Bu işlevler, dize tabanlı verileri depolamak için koleksiyon sınıfı kullanıldığında yararlıdır. Kullanım [Cstringelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md) büyük küçük harf duyarsız karşılaştırmalar zaman gereklidir. Kullanım [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) olduğunda dize nesneleri ile başvuru olarak ele alınabilir.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** cstringt.h

##  <a name="compareelements"></a>  CStringElementTraits::CompareElements

Eşitlik için iki dize öğeleri Karşılaştırılacak statik bu işlevi çağırın.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğe yanlış Aksi takdirde, eşitse true döndürür.

##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered

İki dize öğe Karşılaştırılacak statik bu işlevi çağırın.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize öğesi.

*str2*<br/>
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizeler aynıysa sıfır, < 0, *str1* olduğu küçüktür *str2*, veya > 0 ise *str1* büyüktür *str2*. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) yöntemi karşılaştırmalar yapmak için kullanılır.

##  <a name="copyelements"></a>  CStringElementTraits::CopyElements

Kopyalamak için statik bu işlevi çağırın `CString` bir koleksiyon sınıfı nesnesinde saklanan öğe.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
Kopyalanan veriler alacak ilk öğesinin işaretçisi.

*pSrc*<br/>
Kopyalamak için ilk öğesinin işaretçisi.

*nElements*<br/>
Kopyalanacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef öğeleri çakışmaması.

##  <a name="hash"></a>  CStringElementTraits::Hash

Verilen dize öğesi için bir karma değeri hesaplamak için statik bu işlevi çağırın.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Dizenin içeriklerini kullanarak hesaplanan bir karma değer döndürür.

##  <a name="inargtype"></a>  CStringElementTraits::INARGTYPE

Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraits::OUTARGTYPE

Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

##  <a name="relocateelements"></a>  CStringElementTraits::RelocateElements

Dışında yeniden konumlandırmakta statik bu işlevi çağırın `CString` bir koleksiyon sınıfı nesnesinde saklanan öğe.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
Veriler yeni yerlerine alacak ilk öğesinin işaretçisi.

*pSrc*<br/>
Dışında yeniden konumlandırmakta ilk öğesinin işaretçisi.

*nElements*<br/>
Dışında yeniden konumlandırmakta öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu statik işlev çağrıları [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), çoğu veri türleri için yeterli olduğu. Taşınan nesnelerin kendi üye işaretçileri içeriyorsa, bu statik işlev geçersiz kılınması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CElementTraitsBase Sınıfı](../../atl/reference/celementtraitsbase-class.md)<br/>
[CStringElementTraitsI Sınıfı](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
