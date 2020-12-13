---
description: 'Daha fazla bilgi edinin: Cautoptrelementnitelikler sınıfı'
title: Cautoptrelementnitelikler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: 2478f8251f0094aaa5cabf1c0dcc873c9c526cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147140"
---
# <a name="cautoptrelementtraits-class"></a>Cautoptrelementnitelikler sınıfı

Bu sınıf, akıllı işaretçiler koleksiyonları oluştururken yararlı yöntemler, statik işlevler ve tür tanımları sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

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

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[Cautoptrelementnitelikler:: ıNARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[Cautoptrelementnitelikler:: OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, akıllı işaretçiler içeren koleksiyon sınıfı nesnelerinin oluşturulmasını oluşturmak için yöntemler, statik işlevler ve tür tanımları sağlar. [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) ve [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) sınıfları öğesinden türetilir `CAutoPtrElementTraits` . Vektör New ve delete işleçleri gerektiren akıllı işaretçiler koleksiyonu oluşturuluyorsa bunun yerine [Cautovectorptrelementnitelikler](../../atl/reference/cautovectorptrelementtraits-class.md) kullanın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cdefaultcomparetoyits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[Cdefaultelementnitelikler](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cautoptrelementtraitsinargtype"></a><a name="inargtype"></a> Cautoptrelementnitelikler:: ıNARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef CAutoPtr<T>& INARGTYPE;
```

## <a name="cautoptrelementtraitsoutargtype"></a><a name="outargtype"></a> Cautoptrelementnitelikler:: OUTARGTYPE

Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[Cdefaultelementnitelikler sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
