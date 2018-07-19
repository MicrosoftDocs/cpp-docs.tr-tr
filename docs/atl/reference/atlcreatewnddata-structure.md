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
ms.openlocfilehash: cf51197750e9595570a7b011c179c2ed4c7902c3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880014"
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData yapısı
Bu yapı ATL Pencereleme kodunda sınıfı örneği veri içeriyor  
  
## <a name="syntax"></a>Sözdizimi  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>Üyeler  
 `m_pThis`  
 **Bu** sınıf örneği pencere yordamları erişmek için kullanılan bir işaretçi.  
  
 `m_dwThreadID`  
 İş parçacığı kimliği geçerli sınıf örneğinin.  
  
 `m_pNext`  
 Sonraki işaretçisi `_AtlCreateWndData` nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve yapılar](../../atl/reference/atl-classes.md)





