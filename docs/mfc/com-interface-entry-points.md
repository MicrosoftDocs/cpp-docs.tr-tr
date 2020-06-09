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
ms.openlocfilehash: 132dd7394119081dcaeb098c2088782ff5d40ae4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619337"
---
# <a name="com-interface-entry-points"></a>COM Arabirimi Giriş Noktaları

Bir COM arabiriminin üye işlevleri için, bir `METHOD_PROLOGUE` içe aktarılmış arabirimin yöntemlerini çağırırken doğru genel durumu korumak için makrosunu kullanın.

Genellikle, türetilmiş nesneler tarafından uygulanan arabirimlerin üye işlevleri `CCmdTarget` , işaretçinin otomatik olarak başlatılmasını sağlamak için bu makroyu zaten kullanır `pThis` . Örnek:

[!code-cpp[NVC_MFCConnectionPoints#5](codesnippet/cpp/com-interface-entry-points_1.cpp)]

Daha fazla bilgi için bkz. MFC/OLE uygulamasında [Teknik dekont 38](tn038-mfc-ole-iunknown-implementation.md) `IUnknown` .

`METHOD_PROLOGUE`Makro şöyle tanımlanır:

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \
```

Makronun genel durumu yönetmeyle ilgili bölümü:

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

Bu ifadede, *m_pModuleState* kapsayan nesnenin üye değişkeni olduğu varsayılır. `CCmdTarget`Temel sınıf tarafından uygulanır ve nesnesi örneği oluşturulduğunda, tarafından uygun değere başlatılır `COleObjectFactory` .

## <a name="see-also"></a>Ayrıca bkz.

[MFC modüllerinin durum verilerini yönetme](managing-the-state-data-of-mfc-modules.md)
