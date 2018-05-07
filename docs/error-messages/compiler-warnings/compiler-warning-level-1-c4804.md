---
title: Derleyici Uyarısı (düzey 1) C4804 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4804
dev_langs:
- C++
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 677899230b2475c80f9bdd461a0c79740c4d3bec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4804"></a>Derleyici Uyarısı (düzey 1) C4804
'işlemi': işlem ' bool' türünün güvensiz kullanımı  
  
 Bu uyarı için kullanıldığında bir `bool` değişken veya beklenmeyen bir şekilde değer. Negatif birli işleç gibi işleçlerin kullanırsanız, örneğin, C4804 oluşturulur (**-**) veya tamamlama işleci (`~`). Derleyici ifadeyi hesaplar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4804 oluşturur:  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```