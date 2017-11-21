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
ms.openlocfilehash: cd49b93beb54776bf17a9ee2bc5c9816f0964451
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md)