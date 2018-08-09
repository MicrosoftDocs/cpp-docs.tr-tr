---
title: Asyncstatusınternal numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eeaef23178829163725b78685b3460913f53f2c2
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652805"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal Numaralandırması
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman uyumsuz işlemler durumu için iç sabit listeleri arasındaki eşlemeyi belirtir ve `Windows::Foundation::AsyncStatus` sabit listesi.  
  
## <a name="members"></a>Üyeler  
 `_Created`  
 Eşdeğerdir `::Windows::Foundation::AsyncStatus::Created`  
  
 `_Started`  
 Eşdeğerdir `::Windows::Foundation::AsyncStatus::Started`  
  
 `_Completed`  
 Eşdeğerdir `::Windows::Foundation::AsyncStatus::Completed`  
  
 `_Cancelled`  
 Eşdeğerdir `::Windows::Foundation::AsyncStatus::Cancelled`  
  
 `_Error`  
 Eşdeğerdir `::Windows::Foundation::AsyncStatus::Error`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)