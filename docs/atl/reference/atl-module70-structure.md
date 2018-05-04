---
title: _ATL_MODULE70 yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- _ATL_MODULE70
- ATL::_ATL_MODULE70
- ATL._ATL_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- ATL_MODULE70 structure
- _ATL_MODULE70 structure
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f189ef58ab83a6e77852c109e6da3ae86dc5555d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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







