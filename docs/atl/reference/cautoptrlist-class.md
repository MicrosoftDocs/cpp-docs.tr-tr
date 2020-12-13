---
description: 'Daha fazla bilgi edinin: CAutoPtrList sınıfı'
title: CAutoPtrList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 51544d464904d0ebfd31b82152088a0dfa638969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152522"
---
# <a name="cautoptrlist-class"></a>CAutoPtrList sınıfı

Bu sınıf, akıllı işaretçiler listesi oluştururken yararlı yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

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

|Ad|Açıklama|
|----------|-----------------|
|[CAutoPtrList:: CAutoPtrList](#cautoptrlist)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir oluşturucu sağlar ve akıllı işaretçiler depolayan bir liste nesnesinin oluşturulmasına yardımcı olmak için [CAtlList](../../atl/reference/catllist-class.md) ve [Cautoptrelementnitelikler](../../atl/reference/cautoptrelementtraits-class.md) 'teki yöntemleri türetiliyor. [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) sınıfı, bir dizi nesnesi için benzer bir işlev sağlar.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a> CAutoPtrList:: CAutoPtrList

Oluşturucu.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu, varsayılan olarak 10 ' dur.

### <a name="remarks"></a>Açıklamalar

Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarının bir ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[CAtlList sınıfı](../../atl/reference/catllist-class.md)<br/>
[Cautoptrelementnitelikler sınıfı](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
