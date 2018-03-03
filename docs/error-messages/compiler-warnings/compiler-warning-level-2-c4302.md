---
title: "Derleyici Uyarısı (Düzey 2) C4302 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4302
dev_langs:
- C++
helpviewer_keywords:
- C4302
ms.assetid: f5e1c939-e134-4cca-ba1e-9b15a81549ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b72b6149e1f904bb78d8c4c1f909faf8b9c0efe0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4302"></a>Derleyici Uyarısı (Düzey 2) C4302
'dönüştürme': gelen 'türü: 1' kesme '2 türü için '  
  
 Derleyici bir büyük türüne dönüştürme küçük bir türe algıladı. Bilgiler kaybolmuş olabilir.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4302 oluşturur:  
  
```  
// C4302.cpp  
// compile with: /W2  
#pragma warning(default : 4302)  
int main() {  
   int i;  
   char c = (char) &i;     // C4302  
   short s = (short) &i;   // C4302  
}  
```