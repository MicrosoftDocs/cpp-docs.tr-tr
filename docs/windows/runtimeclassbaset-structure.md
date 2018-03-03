---
title: "RuntimeClassBaseT yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8798372b96074cb8424b4e747b188abcaf826849
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `RuntimeClassTypeT`  
 Bir veya daha fazla belirten bayrakları alanı [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin yardımcı yöntemleri sağlar `QueryInterface` işlemleri ve alma arabirimi kimlikleri.  
  
## <a name="members"></a>Üyeler  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `RuntimeClassBaseT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (Windows çalışma zamanı kitaplığı)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)