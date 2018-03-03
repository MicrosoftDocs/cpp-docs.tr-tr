---
title: "Windows iletileri makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6dde3255997b03eb827ef9e318de73b3badee23c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-messages-macros"></a>Windows iletileri makroları
Bu makrosu pencere iletileri iletir.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|İşleme için başka bir pencere için bir pencere tarafından alınan bir iletiyi iletme için kullanın.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>WM_FORWARDMSG  
 Bu makrosu işleme için başka bir pencere için bir pencere tarafından alınan ileti gönderir.  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan iletisi işlendi, sıfır değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `WM_FORWARDMSG` işleme için başka bir pencere için bir pencere tarafından alınan bir iletiyi iletmesini. LPARAM ve WPARAM parametreleri aşağıdaki gibi kullanılır:  
  
|Parametre|Kullanım|  
|---------------|-----------|  
|WPARAM|Kullanıcı tarafından tanımlanan verileri|  
|LPARAM|Bir işaretçi bir `MSG` bir ileti hakkında bilgi içeren yapısı|  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte, `m_hWndOther` şu iletiyi alıyor başka bir pencere temsil eder.  
  
 [!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
