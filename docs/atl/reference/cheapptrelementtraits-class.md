---
description: 'Daha fazla bilgi edinin: Cheapptrelementnitelikler sınıfı'
title: Cheapptrelementnitelikler sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
ms.openlocfilehash: 7ca3d194a284f06e6b5baa0530cb49bc93d8510a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141615"
---
# <a name="cheapptrelementtraits-class"></a>Cheapptrelementnitelikler sınıfı

Bu sınıf, yığın işaretçileri koleksiyonları oluştururken yararlı yöntemler, statik işlevler ve tür tanımları sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<typename T, class Allocator = ATL::CCRTAllocator>
class CHeapPtrElementTraits :
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Koleksiyon sınıfında depolanacak nesne türü.

*Öğe*<br/>
Kullanılacak bellek ayırma sınıfı. Varsayılan değer [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)' dir.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[Cheapptrelementnitelikler:: ıNARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|
|[Cheapptrelementnitelikler:: OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, yığın işaretçileri içeren koleksiyon sınıfı nesnelerinin oluşturulmasını oluşturmak için yöntemler, statik işlevler ve tür tanımları sağlar. Sınıfı `CHeapPtrList` öğesinden türetilir `CHeapPtrElementTraits` .

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cdefaultcomparetoyits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[Cdefaultelementnitelikler](../../atl/reference/cdefaultelementtraits-class.md)

`CHeapPtrElementTraits`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cheapptrelementtraitsinargtype"></a><a name="inargtype"></a> Cheapptrelementnitelikler:: ıNARGTYPE

Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.

```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```

## <a name="cheapptrelementtraitsoutargtype"></a><a name="outargtype"></a> Cheapptrelementnitelikler:: OUTARGTYPE

Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[Cdefaultelementnitelikler sınıfı](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CComHeapPtr sınıfı](../../atl/reference/ccomheapptr-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
