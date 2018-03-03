---
title: "Derleyici Hatası C3446 | Microsoft Docs"
ms.custom: 
ms.date: 07/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3446
dev_langs:
- C++
helpviewer_keywords:
- C3445
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 590f9b4012c7a00cb73a61b0d275ff9c5ee9cf9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3446"></a>Derleyici Hatası C3446  
  
>'*sınıfı*': varsayılan üye başlatıcıdan değer sınıfı üyeleri için izin verilmiyor  
  
Visual Studio 2015 ve önceki sürümlerinde, derleyici izin (ancak göz ardı) bir değer sınıfı üyesi için varsayılan üye başlatıcıdan. Varsayılan olarak başlatılması değer sınıfı her zaman sıfır-üyeleri başlatır; Varsayılan bir oluşturucu izin verilmez. Visual Studio 2017 ' varsayılan üye başlatıcıları Bu örnekte gösterildiği gibi bir derleyici hatası Yükselt:

## <a name="example"></a>Örnek  
 Aşağıdaki örnek Visual Studio 2017 ve daha sonra C3446 oluşturur:  
  
```cpp  
// C3446.cpp  
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer  
                  // is not allowed for a member of a value class
       int j {0}; // C3446           
};
```  
  
Hatayı düzeltmek için Başlatıcı kaldırın:  
  
```cpp  
// C3446b.cpp  
value struct V
{
       int i;  
       int j;
};
```  
  
