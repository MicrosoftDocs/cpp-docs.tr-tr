---
title: "EventTargetArray::Begin yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::Begin
dev_langs:
- C++
helpviewer_keywords:
- Begin method
ms.assetid: 1cc7fdfd-a2c4-4b28-93cf-1c82842294ba
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96bf73de31733fb10eba0156de90b5d0f196b4ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="eventtargetarraybegin-method"></a>EventTargetArray::Begin Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ComPtr<IUnknown>* Begin();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Olay işleyicileri iç dizisi ilk öğe adresi.  
  
## <a name="remarks"></a>Açıklamalar  
 Olay işleyicileri iç dizisinde ilk öğe adresini alır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** event.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EventTargetArray sınıfı](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)