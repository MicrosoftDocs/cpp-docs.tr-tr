---
title: "Olay işleme genel işlevlerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6670ef283d24f57b407ad70693421feae427855f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="event-handling-global-functions"></a>Olay işleme genel işlevler
Bu işlev bir olay işleyicisi sağlar.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarda aşağıdaki tabloda listelenen işlevi kullanılamaz.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|Bir nesne bildirilmesini, bu sırada gerektiğinde pencere iletileri gönderme bekler.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 Nesne için sinyal gönderilmesini bekler, bu arada pencere iletilerini gerektiği şekilde dağıtır.  
  
> [!IMPORTANT]
>  Windows çalışma zamanı'nda yürütme uygulamalarında bu işlevi kullanılamaz.  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>Parametreler  
 `hEvent`  
 [in] Beklemek için nesne işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** nesne işaret varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerçekleşir ve bunu gerçekleştiği bildirim almak bir nesnenin olayı bekle istiyor ancak bekleme sırasında dağıtılması pencere iletileri izin vermek yararlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlevler](../../atl/reference/atl-functions.md)
