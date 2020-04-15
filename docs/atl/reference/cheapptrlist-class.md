---
title: CHeapPtrList Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
ms.openlocfilehash: 0500ab8f76049aeaf1c89355ea5450a93243b734
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326867"
---
# <a name="cheapptrlist-class"></a>CHeapPtrList Sınıfı

Bu sınıf, yığın işaretçileri listesini yaparken yararlı yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<typename E, class Allocator = ATL::CCRTAllocator>
class CHeapPtrList
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```

#### <a name="parameters"></a>Parametreler

*E*<br/>
Koleksiyon sınıfında depolanacak nesne türü.

*Ayırıcı*<br/>
Kullanılacak bellek ayırma sınıfı. Varsayılan [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)olduğunu.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir oluşturucu sağlar ve [catlList](../../atl/reference/catllist-class.md) ve [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) bir koleksiyon sınıfı nesne yığın işaretçileri depolama oluşturulmasına yardımcı olmak için yöntemler türetilmiştir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlList](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a>CHeapPtrList::CHeapPtrList

Oluşturucu.

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarının ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlList Sınıfı](../../atl/reference/catllist-class.md)<br/>
[CHeapPtr Sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrElementTraits Sınıfı](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
