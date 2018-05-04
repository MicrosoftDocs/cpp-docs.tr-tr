---
title: _ATL_BASE_MODULE70 yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_ATL_BASE_MODULE70
- ATL._ATL_BASE_MODULE70
- _ATL_BASE_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_BASE_MODULE70 structure
- _ATL_BASE_MODULE70 structure
ms.assetid: 4539282f-15b8-4d7c-aafa-a85dc56f4980
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b4e0173ecca5256ed942c23dbaf377850ee8192
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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





