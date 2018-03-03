---
title: "AsyncBase::ErrorCode yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ErrorCode
dev_langs:
- C++
helpviewer_keywords:
- ErrorCode method
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a2f94e3d62e6fb556246877a647ccdc97a47ef2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbaseerrorcode-method"></a>AsyncBase::ErrorCode Yöntemi
Geçerli zaman uyumsuz işlemi için hata kodunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline void ErrorCode(  
   HRESULT *error  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `error`  
 Bu işlem geçerli hata kodu depoladığı konumu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem iş parçacığı güvenlidir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)