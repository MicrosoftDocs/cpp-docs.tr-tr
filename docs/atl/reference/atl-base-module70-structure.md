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
ms.openlocfilehash: d48d863cdbe8e5528824b3ffbad10e1117277e0c
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885346"
---
# <a name="atlbasemodule70-structure"></a>_ATL_BASE_MODULE70 yapısı
ATL kullanan herhangi bir proje tarafından kullanılan  
  
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
 Sürüm oluşturma için kullanılan bir yapının boyutu.  
  
 `m_hInst`  
 `hInstance` Bu Modülü (exe veya dll).  
  
 `m_hInstResource`  
 Varsayılan örneği kaynağı tanıtıcısı.  
  
 `m_bNT5orWin98`  
 İşletim sistemi sürüm bilgisi. ATL tarafından dahili olarak kullanılır  
  
 `dwAtlBuildVer`  
 ATL sürümünü depolar Şu anda 0x0700.  
  
 `pguidVer`  
 ATL'nin iç GUID.  
  
 `m_csResource`  
 Erişimi eşitlemek için kullanılan `m_rgResourceInstance` dizisi. ATL tarafından dahili olarak kullanılır  
  
 `m_rgResourceInstance`  
 ATL uyumlu olduğu tüm kaynak örneklerinin kaynaklarında aramak için kullanılan dizisi. ATL tarafından dahili olarak kullanılır  
  
## <a name="remarks"></a>Açıklamalar  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module) _ATL_BASE_MODULE70 typedef tanımlanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve yapılar](../../atl/reference/atl-classes.md)





