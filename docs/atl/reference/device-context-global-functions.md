---
title: "Cihaz bağlamı genel işlevler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9aa685604580423262ab694d1285897cd29eef63
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="device-context-global-functions"></a>Cihaz bağlamı genel işlevler
Bu işlev belirli bir aygıt için bir cihaz bağlamı oluşturur.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Bir cihaz bağlamı oluşturur.|  
  
##  <a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 Belirtilen cihaz için cihaz bağlamı oluşturan [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) yapısı.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Parametreler  
 *hdc*  
 [in] Var olan bir cihaz bağlamı tanıtıcısı veya **NULL**.  
  
 `ptd`  
 [in] Bir işaretçi **DVTARGETDEVICE** hedef aygıt hakkındaki bilgileri içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen cihaz için cihaz bağlamı için işleyici döner **DVTARGETDEVICE**. Hiçbir aygıt belirtilmezse, varsayılan görüntü aygıtına işleyicisini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Yapı ise **NULL** ve *hdc* olan **NULL**, varsayılan görüntüleme cihazı için cihaz bağlamı oluşturur.  
  
 Varsa *hdc* değil **NULL** ve `ptd` olan **NULL**, varolan işlevi döndürür *hdc*.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
   
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
