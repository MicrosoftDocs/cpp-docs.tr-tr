---
title: _ATL_COM_MODULE70 yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_ATL_COM_MODULE70
- ATL._ATL_COM_MODULE70
- _ATL_COM_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_COM_MODULE70 structure
- ATL_COM_MODULE70 structure
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06c0fa2af67ddd649783c9e062a1b93b87dd0b39
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="atlcommodule70-structure"></a>_ATL_COM_MODULE70 yapısı
ATL COM ilgili kodda tarafından kullanılan  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct _ATL_COM_MODULE70 {
    UINT cbSize;
    HINSTANCE m_hInstTypeLib;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;
    _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;
    CRITICAL_SECTION m_csObjMap;
};
```  
  
## <a name="members"></a>Üyeler  
 `cbSize`  
 Sürüm oluşturma için kullanılan yapısı, boyutu.  
  
 `m_hInstTypeLib`  
 Bu modül için tür kitaplığı tanıtıcı örneğine.  
  
 **m_ppAutoObjMapFirst**  
 Bu modülü için nesne eşleme girdilerini başlangıcını belirten dizi öğesi adresidir.  
  
 **m_ppAutoObjMapLast**  
 Bu modülü için nesne eşleme girdilerini sonuna belirten dizi öğesi adresidir.  
  
 `m_csObjMap`  
 Nesne eşleme girdilerini erişimi serileştirmek için kritik bölüm. ATL tarafından dahili olarak kullanılır  
  
## <a name="remarks"></a>Açıklamalar  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module) typedef tanımlanan `_ATL_COM_MODULE70`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar](../../atl/reference/atl-structures.md)





