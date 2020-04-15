---
title: CAutoPtrElementTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: ac29116dc9beedf587c42cc0e52f8c9dbaf3d782
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318884"
---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits Sınıfı

Bu sınıf, akıllı işaretçilerin koleksiyonlarını oluştururken yöntemler, statik işlevler ve yararlı typedefs sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<typename T>
class CAutoPtrElementTraits
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
İşaretçi türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtrElementÖzellikleri::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[CAutoPtrElementÖzellikler::OUTARGTYPE](#outargtype)|Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, akıllı işaretçiler içeren koleksiyon sınıfı nesnelerinoluşturulmasına yardımcı olmak için yöntemler, statik işlevler ve typedefs sağlar. [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) ve [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) sınıfları. `CAutoPtrElementTraits` Vektör yeni ve silme işleçleri gerektiren akıllı işaretçiler koleksiyonu oluşturuyorsanız, bunun yerine [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) kullanın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CDefaultCompareÖzellikler](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cautoptrelementtraitsinargtype"></a><a name="inargtype"></a>CAutoPtrElementÖzellikleri::INARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef CAutoPtr<T>& INARGTYPE;
```

## <a name="cautoptrelementtraitsoutargtype"></a><a name="outargtype"></a>CAutoPtrElementÖzellikler::OUTARGTYPE

Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
