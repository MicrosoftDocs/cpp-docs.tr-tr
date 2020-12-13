---
description: 'Daha fazla bilgi edinin: CHeapPtrList sınıfı'
title: CHeapPtrList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
ms.openlocfilehash: 7e3a97280f7abcd4b7efebf6726ac062215912d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141602"
---
# <a name="cheapptrlist-class"></a>CHeapPtrList sınıfı

Bu sınıf, yığın işaretçileri listesi oluştururken yararlı yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

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

*Öğe*<br/>
Kullanılacak bellek ayırma sınıfı. Varsayılan değer [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)' dir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtrList:: CHeapPtrList](#cheapptrlist)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, öbek işaretçilerini depolayan bir koleksiyon sınıfı nesnesinin oluşturulmasına yardımcı olmak için bir oluşturucu sağlar ve [CAtlList](../../atl/reference/catllist-class.md) ve [Cheapptrelementnitelikler](../../atl/reference/cheapptrelementtraits-class.md) 'ten Yöntemler türetiliyor.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlList](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a> CHeapPtrList:: CHeapPtrList

Oluşturucu.

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarının bir ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlList sınıfı](../../atl/reference/catllist-class.md)<br/>
[CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)<br/>
[Cheapptrelementnitelikler sınıfı](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
