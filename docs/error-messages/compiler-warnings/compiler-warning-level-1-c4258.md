---
title: "Derleyici Uyarısı (düzey 1) C4258 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4258
dev_langs: C++
helpviewer_keywords: C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e8b987b1ad156106e4944443b778275b7643d116
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4258"></a>Derleyici Uyarısı (düzey 1) C4258
'değişkeni': tanımından döngü göz ardı için; çevreleyen kapsamdaki tanımından kullanılan"  
  
 Altında [/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve [/ZC: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md), tanımlanan değişkenler bir [için](../../cpp/for-statement-cpp.md) döngü Git sonra kapsam dışında **için** döngü sona erer. Döngü değişkeninin kapsayan bir döngü içinde tanımlanan ancak aynı ada sahip bir değişken yeniden içeren kapsam kullanılıyorsa bu uyarıyı oluşur **için** döngü. Örneğin:  
  
```  
// C4258.cpp  
// compile with: /Zc:forScope /W1  
int main()  
{  
   int i;  
   {  
      for (int i =0; i < 1; i++)  
         ;  
      i = 20;   // C4258 i (in for loop) has gone out of scope  
   }  
}  
```