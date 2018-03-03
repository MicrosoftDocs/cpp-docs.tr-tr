---
title: "Asyncstatusınternal numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd277fecb0bc63d5ee823af98df8aa298b285964
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal Numaralandırması
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman uyumsuz işlemler durumu için iç numaralandırmalar arasında bir eşleme belirtir ve **Windows::Foundation::AsyncStatus** numaralandırması.  
  
## <a name="members"></a>Üyeler  
 `_Created`  
 Eşdeğer:: Windows::Foundation::AsyncStatus:: oluşturuldu  
  
 `_Started`  
 Eşdeğer:: Windows::Foundation::AsyncStatus:: başlatıldı  
  
 `_Completed`  
 Eşdeğer:: Windows::Foundation::AsyncStatus:: tamamlandı  
  
 `_Cancelled`  
 Eşdeğer:: Windows::Foundation::AsyncStatus:: iptal edildi  
  
 `_Error`  
 Eşdeğer:: Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)