---
title: "CancelTransitionPolicy numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs: C++
helpviewer_keywords: CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7f21959daf740155a70787f7c35f8467d1fb2149
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)