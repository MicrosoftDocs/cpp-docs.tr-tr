---
description: 'Şu konuda daha fazla bilgi edinin: CElementTraitsBase sınıfı'
title: CElementTraitsBase sınıfı
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
ms.openlocfilehash: a200517e378cc3c3ca854ff60e9a49ac8e43d215
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141784"
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase sınıfı

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

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CElementTraitsBase:: ıNARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[CElementTraitsBase:: OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CElementTraitsBase:: CopyElements](#copyelements)|Koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak için bu yöntemi çağırın.|
|[CElementTraitsBase:: Relocateöğeleri](#relocateelements)|Koleksiyon sınıfı nesnesinde depolanan öğelerin konumunu değiştirmek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu temel sınıf, bir koleksiyon sınıfındaki öğeleri kopyalama ve değiştirme yöntemlerini tanımlar. [Cdefaultelementnitelikler](../../atl/reference/cdefaultelementtraits-class.md), [cstringrefelementnitelikler](../../atl/reference/cstringrefelementtraits-class.md)ve [Cstrıngelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md)sınıfları tarafından kullanılır.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="celementtraitsbasecopyelements"></a><a name="copyelements"></a> CElementTraitsBase:: CopyElements

Koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak için bu yöntemi çağırın.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
Kopyalanmış verileri alacak olan ilk öğe işaretçisi.

*pSrc*<br/>
Kopyalanacak ilk öğe için işaretçi.

*nElements*<br/>
Kopyalanacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Kaynak ve hedef öğeler çakışmamalıdır.

## <a name="celementtraitsbaseinargtype"></a><a name="inargtype"></a> CElementTraitsBase:: ıNARGTYPE

Koleksiyona öğe eklemek için kullanılacak veri türü.

```
typedef const T& INARGTYPE;
```

## <a name="celementtraitsbaseoutargtype"></a><a name="outargtype"></a> CElementTraitsBase:: OUTARGTYPE

Koleksiyondan öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="celementtraitsbaserelocateelements"></a><a name="relocateelements"></a> CElementTraitsBase:: Relocateöğeleri

Koleksiyon sınıfı nesnesinde depolanan öğelerin konumunu değiştirmek için bu yöntemi çağırın.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parametreler

*pDest*<br/>
Yeniden konumlandırılan verileri alacak olan ilk öğe işaretçisi.

*pSrc*<br/>
Yeniden konumlandırmak için ilk öğe işaretçisi.

*nElements*<br/>
Yeniden konumlandırmak için öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, çoğu veri türü için yeterli olan [memmove](../../c-runtime-library/reference/memmove-wmemmove.md)öğesini çağırır. Taşınan nesneler kendi üyelerine işaretçiler içeriyorsa, bu yöntemin geçersiz kılınması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
