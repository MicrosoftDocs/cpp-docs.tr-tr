---
description: 'Daha fazla bilgi edinin: Cdefaultelementnitelikler sınıfı'
title: Cdefaultelementnitelikler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: f4dd1bae67ef626ef793ecee946d88879a07f194
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141901"
---
# <a name="cdefaultelementtraits-class"></a>Cdefaultelementnitelikler sınıfı

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

Bu sınıf, bir koleksiyon sınıfı nesnesinde depolanan öğeleri taşımak, kopyalamak, karşılaştırmak ve karma yapmak için varsayılan statik işlevleri ve yöntemleri sağlar. Bu sınıf, [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)ve [cdefaultcomparetkits](../../atl/reference/cdefaultcomparetraits-class.md)'In Işlevlerini ve yöntemlerini türetir ve [celementnitelikler](../../atl/reference/celementtraits-class.md), [Cprimitiveelementnitelikler](../../atl/reference/cprimitiveelementtraits-class.md)ve [cheapptrelementnitelikler](../../atl/reference/cheapptrelementtraits-class.md)tarafından kullanılır.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
