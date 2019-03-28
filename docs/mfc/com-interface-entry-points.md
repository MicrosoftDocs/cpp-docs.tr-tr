---
title: COM Arabirimi Giriş Noktaları
ms.date: 03/27/2019
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: eb8fc425d6b9849f6367d9b207e5181652386be3
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58564742"
---
# <a name="com-interface-entry-points"></a>COM Arabirimi Giriş Noktaları

COM arabirimi üye işlevleri için kullanmak `METHOD_PROLOGUE` dışarı aktarılan arabirimin yöntemleri çağrılırken uygun genel durumunu korumak üzere makrosu.

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

## <a name="see-also"></a>Ayrıca bkz.

[MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)
