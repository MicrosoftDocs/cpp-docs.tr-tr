---
title: CancelTransitionPolicy numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs:
- C++
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64f588e67066fed690271aa7d78fcbe726c67177
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860352"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy Numaralandırması
Ne zaman uyumsuz bir işlem denemesi bir terminal durumuna geçiş gösterir tamamlandı veya hata bir istemci tarafından istenen iptal edilmiş durumda göre hareket etmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
enum CancelTransitionPolicy;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="values"></a>Değerler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`RemainCanceled`|Zaman uyumsuz işlemi şu anda istemci tarafından istenen bir iptal edilmiş durumda ise, bu bir terminal tamamlandı ya da hata durumuna geçiş aksine iptal edilmiş durumda tutulacağını belirtir gösterir.|  
|`TransitionFromCanceled`|Zaman uyumsuz işlemi şu anda istemci tarafından istenen bir iptal edilmiş durumda ise, bu durum, terminal durumuna iptal edildi durumu tamamlandı geçiş gösterir ya da bu bayrak yararlanan çağrı tarafından belirlenen hatası.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)