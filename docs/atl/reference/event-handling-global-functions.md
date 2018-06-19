---
title: Olay işleme genel işlevlerini | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb2c7834e7d5475810973a42ef179ea4f5f0079f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358344"
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

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop  
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
