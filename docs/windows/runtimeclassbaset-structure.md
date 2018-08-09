---
title: RuntimeClassBaseT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
dev_langs:
- C++
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4d7113e1c8ca29cf8b6c27efd543dbc3de7810b3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011136"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
### <a name="parameters"></a>Parametreler  
 *RuntimeClassTypeT*  
 Bir veya daha fazla belirten bayraklar alanı [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin yardımcı yöntemleri sağlar `QueryInterface` işlemler ve başlangıç arabirim kimliği.  
  
## <a name="members"></a>Üyeler  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `RuntimeClassBaseT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru (Windows çalışma zamanı kitaplığı)](http://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)