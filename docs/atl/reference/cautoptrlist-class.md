---
title: CAutoPtrList Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 48c7ad6fe13c5f5fbbe5829c25ce1c27896841be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318799"
---
# <a name="cautoptrlist-class"></a>CAutoPtrList Sınıfı

Bu sınıf, akıllı işaretçilerin bir listesini yaparken yararlı yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>Parametreler

*E*<br/>
İşaretçi türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf bir oluşturucu sağlar ve akıllı işaretçileri depolayan bir liste nesnesinin oluşturulmasına yardımcı olmak için [CAtlList](../../atl/reference/catllist-class.md) ve [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) yöntemleri türetilmiştir. [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) sınıfı bir dizi nesnesi için benzer bir işlev sağlar.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a>CAutoPtrList::CAutoPtrList

Oluşturucu.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Varsayılan değer 10 olan blok boyutu.

### <a name="remarks"></a>Açıklamalar

Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarının ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlList Sınıfı](../../atl/reference/catllist-class.md)<br/>
[CAutoPtrElementTraits Sınıfı](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
