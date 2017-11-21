---
title: "Nesne durumu makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs: C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc74d545388199eab2aca63ecdea1fdd62a9ef23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
