---
title: "Derleyici Hatası C2461 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2461
dev_langs: C++
helpviewer_keywords: C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e5e1593e37bd3a02897d023e308593e23d3d73b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2461"></a>Derleyici Hatası C2461
  
> '*sınıfı*': Oluşturucusu sözdizimi biçimsel parametresi eksik  
  
 Sınıf oluşturucusu resmi parametreleri belirtmiyor. Bir oluşturucu bildirimi biçimsel parametresi listesi belirtmelisiniz. Liste boş olabilir.  
  
Bu sorunu gidermek için bildirimi sonra parantez çifti eklemek *sınıfı*:: **sınıfı*.  
  
## <a name="example"></a>Örnek  
  
Aşağıdaki örnek, C2461 düzeltmek gösterilmektedir:  
  
```cpp  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;     // C2461  
   C::C();   // OK  
};  
```