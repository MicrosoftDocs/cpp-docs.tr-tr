---
title: "_ATL_BASE_MODULE70 yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs: C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a85aa23baf294f5f1f4dc2eb49c6004d7633280
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 yapısı
ATL kullanan tüm projesi tarafından kullanılan  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct _ATL_BASE_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInst;
    HINSTANCE m_hInstResource;
    bool m_bNT5orWin98;
    DWORD dwAtlBuildVer;
    GUID* pguidVer;
    CRITICAL_SECTION m_csResource;
    CSimpleArray<HINSTANCE> m_rgResourceInstance;
};
```  
  
## <a name="members"></a>Üyeler  
 `cbSize`  
 Sürüm oluşturma için kullanılan yapısı, boyutu.  
  
 `m_hInst`  
 **HINSTANCE** bu Modülü (exe ya da dll).  
  
 `m_hInstResource`  
 Varsayılan örnek kaynağı tanıtıcısı.  
  
 **m_bNT5orWin98**  
 İşletim sistemi sürüm bilgileri. ATL tarafından dahili olarak kullanılır  
  
 **dwAtlBuildVer**  
 ATL sürümünü depolar Şu anda 0x0700.  
  
 **pguidVer**  
 ATL'ın iç GUID.  
  
 **m_csResource**  
 Erişimi eşitlemek için kullanılan **m_rgResourceInstance** dizi. ATL tarafından dahili olarak kullanılır  
  
 **m_rgResourceInstance**  
 ATL uyumlu olduğu tüm kaynak durumlarda kaynakları aramak için kullanılan dizisi. ATL tarafından dahili olarak kullanılır  
  
## <a name="remarks"></a>Açıklamalar  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) typedef tanımlanan `_ATL_BASE_MODULE70`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar](../../atl/reference/atl-structures.md)





