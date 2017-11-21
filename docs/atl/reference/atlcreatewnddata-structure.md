---
title: "_AtlCreateWndData yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs: C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a5b0811e88188bb29ef3153f739804cbdac66083
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData yapısı
Bu yapı ATL Pencereleme kodda sınıfı örneği veri içeriyor  
  
## <a name="syntax"></a>Sözdizimi  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>Üyeler  
 **m_pThis**  
 **Bu** sınıf örneği penceresi yordamlarda erişmek için kullanılan işaretçi.  
  
 `m_dwThreadID`  
 Geçerli sınıf örneği iş parçacığı kimliği.  
  
 **m_pNext**  
 Sonraki işaretçi `_AtlCreateWndData` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapıları](../../atl/reference/atl-structures.md)





