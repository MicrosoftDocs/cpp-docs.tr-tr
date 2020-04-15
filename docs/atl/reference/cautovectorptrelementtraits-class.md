---
title: CAutoVectorPtrElementTraits Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
ms.openlocfilehash: 956fe39c4d3ba89bb9def2f996dca59905753edb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318752"
---
# <a name="cautovectorptrelementtraits-class"></a>CAutoVectorPtrElementTraits Sınıfı

Bu sınıf, vektör yeni ve silme işleçleri kullanarak akıllı işaretçilerin koleksiyonlarını oluştururken yöntemler, statik işlevler ve typedefs yararlıdır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class CAutoVectorPtrElementTraits :
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
İşaretçi türü.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CAutoVectorPtrElementÖzellikler::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[CAutoVectorPtrElementÖzellikler::OUTARGTYPE](#outargtype)|Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, akıllı işaretçiler içeren koleksiyon sınıfı nesnelerinoluşturulmasına yardımcı olmak için yöntemler, statik işlevler ve typedefs sağlar. [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)aksine, bu sınıf vektör yeni ve silme işleçleri kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CDefaultCompareÖzellikler](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cautovectorptrelementtraitsinargtype"></a><a name="inargtype"></a>CAutoVectorPtrElementÖzellikler::INARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

## <a name="cautovectorptrelementtraitsoutargtype"></a><a name="outargtype"></a>CAutoVectorPtrElementÖzellikler::OUTARGTYPE

Toplama sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[CDefaultElementTraits Sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CAutoVectorPtr Sınıfı](../../atl/reference/cautovectorptr-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
