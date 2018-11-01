---
title: COM Arabirimi Giriş Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: b608b200094cc522d5b70e154d342108fd00892f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484779"
---
# <a name="com-interface-entry-points"></a>COM Arabirimi Giriş Noktaları

COM arabirimi üye işlevleri için kullanmak [METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue) dışarı aktarılan arabirimin yöntemleri çağrılırken uygun genel durumunu korumak üzere makrosu.

Genellikle, uygulanan arabirimlerin üye işlevleri tarafından `CCmdTarget`-türetilmiş nesneler zaten kullanıyorsanız bu makroyu otomatik başlatma sağlamak `pThis` işaretçi. Örneğin:

[!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]

Ek bilgi için bkz: [Teknik Not 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) üzerinde MFC/OLE `IUnknown` uygulaması.

`METHOD_PROLOGUE` Makro olarak tanımlanır:

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \

```

Genel durum yönetilmesiyle makrosu bölümüdür:

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

Bu ifadede *m_pModuleState* bir üye değişkeni kapsayan nesnenin olduğu varsayılır. Tarafından uygulanan `CCmdTarget` temel sınıfı ve uygun değere göre başlatılan `COleObjectFactory`, nesnesi örneği oluşturulduğunda.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

