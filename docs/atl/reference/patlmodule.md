---
title: _pAtlModule | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ATLBASE/ATL::_pAtlModule
dev_langs: C++
helpviewer_keywords:
- pAtlModule variable
- _pAtlModule variable
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fda7463fbf4ad9d60092572266a78c2c67b9ad59
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="patlmodule"></a>_pAtlModule
Geçerli modül için bir işaretçi depolama genel değişkeni.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(selectany) CAtlModule* _pAtlModule  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu genel değişkeni yöntemlere işlevselliği sağlamak için kullanılabilir, (artık kullanılmayan) sınıfı [CComModule](../../atl/reference/ccommodule-class.md) Visual C++ 6.0 ile sunulan.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#97](../../atl/codesnippet/cpp/patlmodule_1.cpp)]  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel değişkenler](../../atl/reference/atl-global-variables.md)



