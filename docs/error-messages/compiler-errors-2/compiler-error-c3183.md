---
title: Derleyici Hatası C3183 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3183
dev_langs:
- C++
helpviewer_keywords:
- C3183
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4520922550dfcb5050c5e8a122910acf4b124934
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3183"></a>Derleyici Hatası C3183
adlandırılmamış sınıf, yapı veya birleşim tanımlayamazsınız içinde yönetilen veya WinRT ' type'  
  
Katıştırılmış bir türü bir yönetilen veya WinRT türü adlandırılmalıdır.  
  
Aşağıdaki örnek C3183 oluşturur:  
  
```  
// C3183a.cpp  
// compile with: /clr /c  
ref class Test  
{  
   ref class  
   {  // C3183, delete class or name it  
      int a;  
      int b;  
   };  
};  
```  
