---
title: lock sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a860f79b740e0f34eef33b7a96e0236835f1f6b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129703"
---
# <a name="lock-class"></a>lock Sınıfı
Bu sınıf, birden çok iş parçacığı bir nesneye erişimi eşitlemek için bir kilit almayı otomatikleştirir.  Oluşturulan, kilit alır ve sürümler yok kilidi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `lock` yalnızca CLR nesneleri için kullanılabilir ve yalnızca CLR kod içinde kullanılabilir.  
  
 Dahili olarak, kilit sınıfı kullanır <xref:System.Threading.Monitor> erişimi eşitlemek için. Daha ayrıntılı bilgi için bu konudaki eşitleme konusuna bakın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [kilitleme](../dotnet/lock.md)   
 [lock Üyeleri](../dotnet/lock-members.md)