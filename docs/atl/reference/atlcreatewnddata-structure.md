---
title: _AtlCreateWndData yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66388c12def72a9da5b5aeb7e4713ca61c23a6e0
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
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
 [Sınıflar ve yapılar](../../atl/reference/atl-classes.md)





