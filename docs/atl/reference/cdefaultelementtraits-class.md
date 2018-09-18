---
title: CDefaultElementTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44822df983021846e9b4168343252affd971accd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097282"
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
