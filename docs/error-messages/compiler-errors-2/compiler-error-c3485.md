---
title: "Derleyici Hatası C3485 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3485
dev_langs: C++
helpviewer_keywords: C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fb872161cc82878c7809e6ebcae901db0ba772f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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