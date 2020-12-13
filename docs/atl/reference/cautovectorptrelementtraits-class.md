---
description: ': Cautovectorptrelementnitelikler sınıfı hakkında daha fazla bilgi edinin'
title: Cautovectorptrelementnitelikler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
ms.openlocfilehash: 571b85c1b11968289d372f9c349ffcdb754dc381
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147101"
---
# <a name="cautovectorptrelementtraits-class"></a>Cautovectorptrelementnitelikler sınıfı

Bu sınıf, vector New ve DELETE işleçlerini kullanarak akıllı işaretçilerin koleksiyonları oluştururken yararlı yöntemler, statik işlevler ve tür tanımları sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

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

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[Cautovectorptrelementnitelikler:: ıNARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[Cautovectorptrelementnitelikler:: OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, akıllı işaretçiler içeren koleksiyon sınıfı nesnelerinin oluşturulmasını oluşturmak için yöntemler, statik işlevler ve tür tanımları sağlar. [Cautoptrelementnitelikler](../../atl/reference/cautoptrelementtraits-class.md)'in aksine, bu sınıf vektör New ve DELETE işleçlerini kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cdefaultcomparetoyits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[Cdefaultelementnitelikler](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cautovectorptrelementtraitsinargtype"></a><a name="inargtype"></a> Cautovectorptrelementnitelikler:: ıNARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

## <a name="cautovectorptrelementtraitsoutargtype"></a><a name="outargtype"></a> Cautovectorptrelementnitelikler:: OUTARGTYPE

Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[Cdefaultelementnitelikler sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CAutoVectorPtr sınıfı](../../atl/reference/cautovectorptr-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
