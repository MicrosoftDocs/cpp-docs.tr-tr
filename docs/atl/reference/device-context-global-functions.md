---
title: Cihaz bağlamı genel işlevleri | Microsoft Docs
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
ms.openlocfilehash: 8944ecdb4f9996800264986a7a687df6020b0591
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209939"
---
# <a name="device-context-global-functions"></a>Cihaz bağlamı genel işlevleri
Bu işlev, belirli bir cihaz için bir cihaz bağlamı oluşturur.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Bir cihaz bağlamı oluşturur.|  
  
##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC  
 Belirtilen cihaz için bir cihaz bağlamı oluşturur [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) yapısı.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Parametreler  
 *hdc*  
 [in] Bir cihaz bağlamı NULL veya var olan işleyici.  
  
 *ptd*  
 [in] Bir işaretçi `DVTARGETDEVICE` hedef cihaz hakkındaki bilgileri içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen cihaz için bir cihaz bağlamı için bir tanıtıcı döndürür `DVTARGETDEVICE`. Cihaz belirtilmezse, varsayılan görüntüleme cihazında tanıtıcısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Yapısı NULL ise ve *hdc* NULL ise, varsayılan görüntüleme cihazı için bir cihaz bağlamı oluşturur.  
  
 Varsa *hdc* NULL değil ve *ptd* NULL ise mevcut bir işlevi döndürür *hdc*.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
   
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
