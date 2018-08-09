---
title: Chainınterfaces::Verify yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 81b3a166215f7731a43333e230621072d760260c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013538"
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify Yöntemi
Her arabirim şablon parametreleri tarafından tanımlanan doğrular *I0* aracılığıyla *I9* devraldığı `IUnknown` ve/veya `IInspectable`ve *I0* devralır *I1* aracılığıyla *I9*.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrulama işlemi başarısız olursa bir **static_assert** hatayı açıklayan bir hata iletisi gösterir.  

 Şablon parametreleri *I0* ve *I1* gereklidir ve parametreleri *I2* aracılığıyla *I9* isteğe bağlıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)