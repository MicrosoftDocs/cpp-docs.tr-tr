---
title: COM arabirimi giriş noktaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7f52aee6a276410ba6a90fd662a2fad8d258e92
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929893"
---
# <a name="com-interface-entry-points"></a>COM Arabirimi Giriş Noktaları
COM arabirimi üye işlevleri için kullanmak [METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue) dışarı aktarılan bir arabirim yöntemleri çağrılırken uygun genel durumunu korumak üzere makrosu.  
  
 Üye işlevleri arabirimleri genellikle, uygulanan tarafından `CCmdTarget`-türetilen nesneler zaten kullanıyorsanız bu makrosu otomatik olarak başlatılması sağlamak için `pThis` işaretçi. Örneğin:  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]  
  
 Ek bilgi için bkz: [Teknik Not 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) MFC/OLE üzerinde `IUnknown` uygulaması.  
  
 `METHOD_PROLOGUE` Makrosu olarak tanımlanır:  
  
 `#define METHOD_PROLOGUE(theClass, localClass) \`  
  
 `theClass* pThis = \`  
  
 `((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \`  
  
 `AFX_MANAGE_STATE(pThis->m_pModuleState) \`  
  
 Genel durum yönetilmesiyle makrosu kısmı şöyledir:  
  
 `AFX_MANAGE_STATE( pThis->m_pModuleState )`  
  
 Bu ifadede *m_pModuleState* bir üye değişkenine kapsayan nesnenin olduğu varsayılır. Tarafından uygulanan `CCmdTarget` temel sınıfı ve uygun değere tarafından başlatılan `COleObjectFactory`, nesne örneği oluşturulduğunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

