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
ms.openlocfilehash: 150169442aa68395b4dc8a4f4c74951e877f18f5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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