---
title: "Derleyici Uyarısı (düzey 1) C4393 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4393
dev_langs:
- C++
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bfd5357ca15cc73f23040f66f89b0a5a41bb963a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4393"></a>Derleyici Uyarısı (düzey 1) C4393
'var': const değişmez değer veri üyesi üzerinde; hiçbir etkisi yoktur göz ardı  
  
 A [değişmez değer](../../windows/literal-cpp-component-extensions.md) veri üyesi de olarak const belirtildi.  Değişmez değer veri üyesi const gelir olduğundan, eklemek bildirimine const gerekmez.  
  
 Aşağıdaki örnek C4393 oluşturur:  
  
```  
// C4393.cpp  
// compile with: /clr /W1 /c  
ref struct Y1 {  
   literal const int staticConst = 10;   // C4393  
   literal int staticConst2 = 10;   // OK  
};  
```