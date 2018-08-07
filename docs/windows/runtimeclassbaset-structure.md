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
ms.openlocfilehash: ec10faf9733bbff3fb271b5465ee70a338c37898
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604999"
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