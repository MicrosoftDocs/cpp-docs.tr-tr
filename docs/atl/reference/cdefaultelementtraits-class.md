---
title: CDefaultElementTraits sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: 2cf93adc5b78a8fa31a603d58f0e4dbe1efb0d6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494694"
---
# <a name="cdefaultelementtraits-class"></a>CDefaultElementTraits sınıfı

Bu sınıf, bir koleksiyon sınıfı için varsayılan yöntemleri ve işlevleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyonda depolanacak veri türü.

## <a name="remarks"></a>Açıklamalar

Bu sınıf, taşıma, kopyalama, karşılaştırma ve bir koleksiyon sınıfı nesnesinde depolanan karma öğeleri için varsayılan statik işlevler ve yöntemleri sağlar. Bu sınıf, yöntemleri ve işlevleri türetilen [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md), ve [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)ve tarafından kullanılan [ CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md), ve [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
