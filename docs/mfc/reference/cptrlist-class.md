---
title: CPtrList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPtrList
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
ms.openlocfilehash: dfd545e1758ea257a89606655bf735829dbe8840
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586400"
---
# <a name="cptrlist-class"></a>CPtrList sınıfı

Void işaretçilerin listelerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CPtrList : public CObject
```

## <a name="members"></a>Üyeler

Üye işlevlerinin `CPtrList` sınıfın üye işlevleri için benzer [CObList](../../mfc/reference/coblist-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CObList` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi bir işlev parametre veya dönüş değeri olarak alternatif bir işaretçiye **void**.

`CObject*& CObList::GetHead() const;`

Örneğin, için çevirir

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>Açıklamalar

`CPtrList` ımplement_dynamıc makrosu, çalışma zamanı tür erişimi ve dökme için desteği kapsayan bir `CDumpContext` nesne. Tek tek işaretçi liste öğelerini dökümü gerekiyorsa, 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.

İşaretçi listeleri nelze serializovat.

Olduğunda bir `CPtrList` nesnesi silindiğinde veya yalnızca işaretçiler öğelerine kaldırıldığında kaldırılır, bunlar başvuru varlıkları.

Kullanma hakkında daha fazla bilgi için `CPtrList`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CPtrList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObList Sınıfı](../../mfc/reference/coblist-class.md)
