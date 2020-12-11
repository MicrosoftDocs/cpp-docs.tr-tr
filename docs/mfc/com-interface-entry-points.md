---
description: 'Daha fazla bilgi edinin: COM arabirimi giriş noktaları'
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
ms.openlocfilehash: 805ac906c3ccca246d1af71c689aaf768f789999
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160018"
---
# <a name="com-interface-entry-points"></a>COM Arabirimi Giriş Noktaları

Bir COM arabiriminin üye işlevleri için, bir `METHOD_PROLOGUE` içe aktarılmış arabirimin yöntemlerini çağırırken doğru genel durumu korumak için makrosunu kullanın.

Genellikle, türetilmiş nesneler tarafından uygulanan arabirimlerin üye işlevleri `CCmdTarget` , işaretçinin otomatik olarak başlatılmasını sağlamak için bu makroyu zaten kullanır `pThis` . Örneğin:

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
