---
title: Derleyici Hatası C3446 | Microsoft Docs
ms.custom: ''
ms.date: 07/21/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3446
dev_langs:
- C++
helpviewer_keywords:
- C3445
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a7715ebbc094c2c3c91aa3a0bb42f7df97bef08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
  
