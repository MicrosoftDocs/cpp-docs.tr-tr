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
ms.openlocfilehash: d7da4fe52d25d9ffdf6371aa40f41d7082f1165c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226847"
---
# <a name="cptrlist-class"></a>CPtrList sınıfı

Void işaretçilerinin listesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CPtrList : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin üye işlevleri, `CPtrList` sınıf [CObList](../../mfc/reference/coblist-class.md)öğesinin üye işlevlerine benzerdir. Bu benzerlik nedeniyle, `CObList` üye işlevi özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işaretçiyi işlev parametresi veya dönüş değeri olarak gördüğünüz her yerde, bir işaretçisi yerine **`void`** .

`CObject*& CObList::GetHead() const;`

Örneğin, öğesine çevirir

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>Açıklamalar

`CPtrList`çalışma zamanı türü erişimini ve bir nesneye dökümünü desteklemek için IMPLEMENT_DYNAMIC makrosunu ekler `CDumpContext` . Tek bir işaretçi listesi öğelerinin dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

İşaretçi listeleri serileştirilemiyor.

Bir `CPtrList` nesne silindiğinde veya öğeleri kaldırıldığında, başvurdukları varlıkların değil yalnızca işaretçiler kaldırılır.

Kullanma hakkında daha fazla bilgi için `CPtrList` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CPtrList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObList sınıfı](../../mfc/reference/coblist-class.md)
