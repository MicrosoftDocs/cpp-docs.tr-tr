---
title: "lock sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c2f2a8e371803d33a2c42508ec595681ada3bab8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lock-class"></a>lock Sınıfı
Bu sınıf, birden çok iş parçacığı bir nesneye erişimi eşitlemek için bir kilit almayı otomatikleştirir.  Oluşturulan, kilit alır ve sürümler yok kilidi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `lock`yalnızca CLR nesneleri için kullanılabilir ve yalnızca CLR kod içinde kullanılabilir.  
  
 Dahili olarak, kilit sınıfı kullanır <xref:System.Threading.Monitor> erişimi eşitlemek için. Daha ayrıntılı bilgi için bu konudaki eşitleme konusuna bakın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [kilitleme](../dotnet/lock.md)   
 [lock Üyeleri](../dotnet/lock-members.md)