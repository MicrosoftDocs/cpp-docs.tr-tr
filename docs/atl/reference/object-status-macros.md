---
title: Nesne durumu makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eddfc28c659d0c1eb54794d8fc76a9f3a4f9e73b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360880"
---
# <a name="object-status-macros"></a>Nesne durumu makroları
Bu makrosu ActiveX denetimlerine ait bayrakları ayarlar.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|ATL ActiveX denetimlerinde ayarlamak için kullanılan **OLEMISC** bayrakları.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS  
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
