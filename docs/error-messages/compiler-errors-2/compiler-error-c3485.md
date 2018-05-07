---
title: Derleyici Hatası C3485 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4cd9de6f300fed673d588df60d7acca15b104b61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3485"></a>Derleyici Hatası C3485
lambda tanımı herhangi MS niteleyicileri sahip olamaz  
  
 Kullanarak bir `const` veya `volatile` niteleyicisi lambda ifadesi tanımının bir parçası olarak.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Kaldırma `const` veya `volatile` niteleyicisi tanımından lambda ifadesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, C3485 oluşturur, bunu kullandığından `const` niteleyicisi lambda ifadesi tanımının bir parçası olarak:  
  
```  
// C3485.cpp  
  
int main()  
{  
   auto x = []() const mutable {}; // C3485  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)