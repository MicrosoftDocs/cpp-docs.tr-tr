---
title: "_ATL_MODULE70 yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs: C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8122f733282fa819c3d789a90e60171ee006e27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atlmodule70-structure"></a>_ATL_MODULE70 yapısı
Her ATL modülü tarafından kullanılan verileri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct _ATL_MODULE70 {
    UINT cbSize;
    LONG m_nLockCnt;
    _ATL_TERMFUNC_ELEM* m_pTermFuncs;
    CComCriticalSection m_csStaticDataInitAndTypeInfo;
};
```  
  
## <a name="members"></a>Üyeler  
 `cbSize`  
 Sürüm oluşturma için kullanılan yapısı, boyutu.  
  
 `m_nLockCnt`  
 Başvuru sayısı ne kadar süreyle modülü Canlı kalmalı belirlemek için.  
  
 **m_pTermFuncs**  
 ATL kapatıldığında çağrılacak kayıtlı işlevler izler.  
  
 **m_csStaticDataInitAndTypeInfo**  
 Birden çok iş parçacıklı durumlarda iç veri erişimi koordine etmek için kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 [_ATL_MODULE](atl-typedefs.md#_atl_module) typedef tanımlanan `_ATL_MODULE70`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar](../../atl/reference/atl-structures.md)







