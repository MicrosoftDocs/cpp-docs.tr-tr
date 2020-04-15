---
title: CPrimitiveElementTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
ms.openlocfilehash: 6b45d93420d1832091cc451a3e6eb309f61d07a3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331435"
---
# <a name="cprimitiveelementtraits-class"></a>CPrimitiveElementTraits Sınıfı

Bu sınıf, ilkel veri türlerinden oluşan bir koleksiyon sınıfı için varsayılan yöntemler ve işlevler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyon sınıfı nesnesinde depolanacak veri türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir koleksiyon sınıfı nesnesinde depolanan ilkel veri türü öğelerini taşımak, kopyalamak, karşılaştırmak ve karma hale getirir için varsayılan statik işlevler ve yöntemler sağlar.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CDefaultCompareÖzellikler](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cprimitiveelementtraitsinargtype"></a><a name="inargtype"></a>CPrimitiveElementTraits::INARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef T INARGTYPE;
```

## <a name="cprimitiveelementtraitsoutargtype"></a><a name="outargtype"></a>CPrimitiveElementTraits::OUTARGTYPE

Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
