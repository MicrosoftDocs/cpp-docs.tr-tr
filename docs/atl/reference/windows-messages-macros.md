---
title: "Windows iletileri makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlbase/ATL::WM_FORWARDMSG
dev_langs: C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 66e212b1f8bd2e749bc87fec92b935aa466522b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
