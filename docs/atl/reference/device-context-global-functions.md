---
title: Cihaz bağlamı genel işlevler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37d54fbe9391cb53cca1d84401e90bb6fd47a479
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358595"
---
# <a name="device-context-global-functions"></a>Cihaz bağlamı genel işlevler
Bu işlev belirli bir aygıt için bir cihaz bağlamı oluşturur.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Bir cihaz bağlamı oluşturur.|  
  
##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC  
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
