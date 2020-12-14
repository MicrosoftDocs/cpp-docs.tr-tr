---
description: 'Daha fazla bilgi edinin: CPtrList sınıfı'
title: CPtrList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPtrList
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
ms.openlocfilehash: 27849db4687860ab68feb548de1ed8ad209b73a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343257"
---
# <a name="cptrlist-class"></a>CPtrList sınıfı

Void işaretçilerinin listesini destekler.

## <a name="syntax"></a>Syntax

```
class CPtrList : public CObject
```

## <a name="members"></a>Üyeler

Öğesinin üye işlevleri, `CPtrList` sınıf [CObList](../../mfc/reference/coblist-class.md)öğesinin üye işlevlerine benzerdir. Bu benzerlik nedeniyle, `CObList` üye işlevi özellikleri için başvuru belgelerini kullanabilirsiniz. Bir `CObject` işaretçiyi işlev parametresi veya dönüş değeri olarak gördüğünüz her yerde, bir işaretçisi yerine **`void`** .

`CObject*& CObList::GetHead() const;`

Örneğin, öğesine çevirir

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>Açıklamalar

`CPtrList` çalışma zamanı türü erişimini ve bir nesneye dökümünü desteklemek için IMPLEMENT_DYNAMIC makrosunu ekler `CDumpContext` . Tek bir işaretçi listesi öğelerinin dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

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
