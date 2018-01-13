---
title: "_ATL_WIN_MODULE70 yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs: C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 733808006a3c301972c4ab3b3f8de3320d9fde46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atlwinmodule70-structure"></a>_ATL_WIN_MODULE70 yapısı
ATL Pencereleme kodda tarafından kullanılan  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```  
  
## <a name="members"></a>Üyeler  
 `cbSize`  
 Sürüm oluşturma için kullanılan yapısı, boyutu.  
  
 `m_csWindowCreate`  
 Pencere kayıt koda erişim serileştirmek için kullanılır. ATL tarafından dahili olarak kullanılır  
  
 **m_pCreateWndList**  
 Windows için kendi nesneleri bağlamak için kullanılır. ATL tarafından dahili olarak kullanılır  
  
 **m_rgWindowClassAtoms**  
 Böylece sonlandırmanın düzgün kaydedilmemiş olabilir pencere sınıfı kaydı izlemek için kullanılır. ATL tarafından dahili olarak kullanılır  
  
## <a name="remarks"></a>Açıklamalar  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module) typedef tanımlanan `_ATL_WIN_MODULE70`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar](../../atl/reference/atl-structures.md)





