---
title: CElementTraitsBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1173633cd720ed6ee0e4aacdf75a8b305fdbfe4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043371"
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase sınıfı

Bu sınıf, varsayılan copy sağlar ve bir koleksiyon sınıfı yöntemleri taşıyın.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CElementTraitsBase::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.|
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesneden öğeleri almak için kullanılacak veri türü.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CElementTraitsBase::CopyElements](#copyelements)|Bir koleksiyon sınıfı nesnesinde saklanan öğe kopyalamak için bu yöntemi çağırın.|
|[CElementTraitsBase::RelocateElements](#relocateelements)|Bir koleksiyon sınıfı nesnesinde saklanan öğe konumunu değiştirmek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu temel sınıfı, bir koleksiyon sınıfı öğelerini yeniden konumlandırma ve kopyalama için yöntemleri tanımlar. Sınıflar tarafından kullanıldığı [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), ve [Cstringelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md).

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="copyelements"></a>  CElementTraitsBase::CopyElements

Bir koleksiyon sınıfı nesnesinde saklanan öğe kopyalamak için bu yöntemi çağırın.

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

##  <a name="inargtype"></a>  CElementTraitsBase::INARGTYPE

Öğeleri bir koleksiyona eklemek için kullanılacak veri türü.

```
typedef const T& INARGTYPE;
```

##  <a name="outargtype"></a>  CElementTraitsBase::OUTARGTYPE

Koleksiyondan öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

##  <a name="relocateelements"></a>  CElementTraitsBase::RelocateElements

Bir koleksiyon sınıfı nesnesinde saklanan öğe konumunu değiştirmek için bu yöntemi çağırın.

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

Bu yöntemin çağırdığı [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), çoğu veri türleri için yeterli olduğu. Taşınan nesnelerin kendi üye işaretçileri içeriyorsa, bu yöntemi geçersiz kılınması gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
