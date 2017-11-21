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
ms.openlocfilehash: 18413443abb074d16c0d813de660555f8ba2b4c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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