---
title: CStringElementTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43581995e8979ec733d8c82374896009c843166b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766652"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits sınıfı

Statik işlevler depolama koleksiyon sınıfları tarafından kullanılan bu sınıfın sağladığı `CString` nesneleri.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>  
class CStringElementTraits
```

#### <a name="parameters"></a>Parametreler

*T*  
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

*str1*  
İlk dize öğesi.

*str2*  
İkinci dize öğesi.

### <a name="return-value"></a>Dönüş Değeri

Öğe yanlış Aksi takdirde, eşitse true döndürür.

##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered

İki dize öğe Karşılaştırılacak statik bu işlevi çağırın.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parametreler

*str1*  
İlk dize öğesi.

*str2*  
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

*pDest*  
Kopyalanan veriler alacak ilk öğesinin işaretçisi.

*pSrc*  
Kopyalamak için ilk öğesinin işaretçisi.

*nElements*  
Kopyalanacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef öğeleri çakışmaması.

##  <a name="hash"></a>  CStringElementTraits::Hash

Verilen dize öğesi için bir karma değeri hesaplamak için statik bu işlevi çağırın.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>Parametreler

*str*  
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

*pDest*  
Veriler yeni yerlerine alacak ilk öğesinin işaretçisi.

*pSrc*  
Dışında yeniden konumlandırmakta ilk öğesinin işaretçisi.

*nElements*  
Dışında yeniden konumlandırmakta öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu statik işlev çağrıları [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), çoğu veri türleri için yeterli olduğu. Taşınan nesnelerin kendi üye işaretçileri içeriyorsa, bu statik işlev geçersiz kılınması gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[CElementTraitsBase sınıfı](../../atl/reference/celementtraitsbase-class.md)   
[Cstringelementtraitsı sınıfı](../../atl/reference/cstringelementtraitsi-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
