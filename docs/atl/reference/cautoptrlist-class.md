---
title: CAutoPtrList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: a7e5c2db31100da8901deaae61527c65655faa7e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551417"
---
# <a name="cautoptrlist-class"></a>CAutoPtrList sınıfı

Bu sınıf, akıllı işaretçiler listesini oluştururken kullanışlı yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

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
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir oluşturucu sağlar ve türeyen yöntemlerinden [CAtlList](../../atl/reference/catllist-class.md) ve [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) akıllı işaretçiler depolama liste nesnesinin oluşturmaya yardımcı olmak için. Sınıf [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) benzer bir işlev için bir dizi nesnesi sağlar.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="cautoptrlist"></a>  CAutoPtrList::CAutoPtrList

Oluşturucu.

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Varsayılan değer 10 blok boyutu.

### <a name="remarks"></a>Açıklamalar

Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarını ölçüsüdür. Büyük blok boyutları için bellek ayırma yordamlarını aramalarını azaltır, ancak daha fazla kaynağı kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[CAtlList Sınıfı](../../atl/reference/catllist-class.md)<br/>
[CAutoPtrElementTraits Sınıfı](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
