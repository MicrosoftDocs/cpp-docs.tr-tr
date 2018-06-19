---
title: Windows iletileri makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21bb273b94f871e253ab927238c96256f46e2b3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360223"
---
# <a name="windows-messages-macros"></a>Windows iletileri makroları
Bu makrosu pencere iletileri iletir.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|İşleme için başka bir pencere için bir pencere tarafından alınan bir iletiyi iletme için kullanın.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG  
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
