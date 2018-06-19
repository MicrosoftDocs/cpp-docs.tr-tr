---
title: Derleyici Hatası C2669 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2669
dev_langs:
- C++
helpviewer_keywords:
- C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 642d2dd99c93b5af021503ffbb4975d1ff3c0db4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233412"
---
# <a name="compiler-error-c2669"></a>Derleyici Hatası C2669
üye işlevini anonim birleşim içinde izin verilmiyor  
  
[Anonim birleşimler](../../cpp/unions.md#anonymous_unions) üye işlevleri sahip olamaz.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C2669 oluşturur:  
  
```cpp  
// C2669.cpp  
struct X {  
   union {  
      int i;  
      void f() {   // C2669, remove function  
         i = 0;   
      }  
   };  
};  
```  
  