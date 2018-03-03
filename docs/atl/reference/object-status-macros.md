---
title: "Nesne durumu makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1139c30fa5d23f3320cef76d09fb5bd86c8c4bc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="object-status-macros"></a>Nesne durumu makroları
Bu makrosu ActiveX denetimlerine ait bayrakları ayarlar.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|ATL ActiveX denetimlerinde ayarlamak için kullanılan **OLEMISC** bayrakları.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  

##  <a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS  
 ATL ActiveX denetimlerinde OLEMISC bayrakları ayarlamak için kullanılır.  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>Parametreler  
 *MiscStatus*  
 Uygun olan tüm OLEMISC bayraklar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu bir ActiveX denetimini OLEMISC bayrakları ayarlamak için kullanılır. Başvurmak [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) daha fazla ayrıntı için.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
