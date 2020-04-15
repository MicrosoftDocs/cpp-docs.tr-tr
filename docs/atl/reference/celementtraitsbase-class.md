---
title: CElementTraitsBase Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
ms.openlocfilehash: 5a29e8778cf2f3400df25b55574950a005bad995
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327000"
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase Sınıfı

Bu sınıf, bir koleksiyon sınıfı için varsayılan kopyalama ve taşıma yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CElementTraitsBase::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CElementTraitsBase::CopyElements](#copyelements)|Koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak için bu yöntemi çağırın.|
|[CElementTraitsBase::RelocateElements](#relocateelements)|Koleksiyon sınıfı nesnesinde depolanan öğeleri taşımak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu taban sınıf, toplama sınıfındaöğeleri kopyalama ve değiştirme yöntemlerini tanımlar. [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)ve [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)sınıfları tarafından kullanılmaktadır.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="celementtraitsbasecopyelements"></a><a name="copyelements"></a>CElementTraitsBase::CopyElements

Koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak için bu yöntemi çağırın.

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

## <a name="celementtraitsbaseinargtype"></a><a name="inargtype"></a>CElementTraitsBase::INARGTYPE

Koleksiyona öğe eklemek için kullanılacak veri türü.

```
typedef const T& INARGTYPE;
```

## <a name="celementtraitsbaseoutargtype"></a><a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE

Koleksiyondan öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="celementtraitsbaserelocateelements"></a><a name="relocateelements"></a>CElementTraitsBase::RelocateElements

Koleksiyon sınıfı nesnesinde depolanan öğeleri taşımak için bu yöntemi çağırın.

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

Bu yöntem, çoğu veri türleri için yeterli olan [memmove](../../c-runtime-library/reference/memmove-wmemmove.md)çağırır. Taşınan nesneler kendi üyelerine işaretçiler içeriyorsa, bu yöntemin geçersiz kılınması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
