---
title: "Chainınterfaces::Verify yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs: C++
helpviewer_keywords: Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1f6cd836d946265f26925e6bc7a9ef8191df93b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Chainınterfaces yapısı](../windows/chaininterfaces-structure.md)