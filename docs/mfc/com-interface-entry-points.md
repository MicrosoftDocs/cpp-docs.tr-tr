---
title: "COM arabirimi giriş noktaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 010df3546a6ac2b6276281c39efdd76abd5ec222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="com-interface-entry-points"></a>COM Arabirimi Giriş Noktaları
COM arabirimi üye işlevleri için kullanmak [METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue) dışarı aktarılan bir arabirim yöntemleri çağrılırken uygun genel durumunu korumak üzere makrosu.  
  
 Üye işlevleri arabirimleri genellikle, uygulanan tarafından `CCmdTarget`-türetilen nesneler zaten kullanıyorsanız bu makrosu otomatik olarak başlatılması sağlamak için `pThis` işaretçi. Örneğin:  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]  
  
 Ek bilgi için bkz: [Teknik Not 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) MFC/OLE üzerinde **IUnknown** uygulaması.  
  
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

