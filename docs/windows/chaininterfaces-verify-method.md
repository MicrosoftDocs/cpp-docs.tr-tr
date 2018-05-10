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
ms.openlocfilehash: c83479434a936f32fb0f7367d8cd02c6676c74e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify Yöntemi
Her bir arabirime şablon parametreleri tarafından tanımlanan doğrular `I0` aracılığıyla `I9` IUnknown ve/veya Iınspectable ve, devralan `I0` devraldığı `I1` aracılığıyla `I9`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrulama işlemi başarısız olursa, bir `static_assert` hatayı açıklayan bir hata iletisi gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon parametreleri `I0` ve `I1` gereklidir ve parametreleri `I2` aracılığıyla `I9` isteğe bağlıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)