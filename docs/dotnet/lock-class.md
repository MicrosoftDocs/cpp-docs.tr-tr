---
title: "lock sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs: C++
helpviewer_keywords: lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c9e21612c227081e3558a8f7f3161f922711c20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [lock üyeleri](../dotnet/lock-members.md)