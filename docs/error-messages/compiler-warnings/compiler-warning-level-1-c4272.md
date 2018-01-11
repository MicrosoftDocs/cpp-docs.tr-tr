---
title: "Derleyici Uyarısı (düzey 1) C4272 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4272
dev_langs: C++
helpviewer_keywords: C4272
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb34c2a754513e00e593a718499eeea750da3647
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4272"></a>Derleyici Uyarısı (düzey 1) C4272
'function': __declspec(dllimport); işaretli yerel arama kuralı, bir işlev içeri aktarırken belirtmeniz gerekir.  
  
 İle işaretlenen bir işlev dışarı aktarmak için bir hata olduğunu [__clrcall](../../cpp/clrcall.md) çağırma kuralı ve derleyici sorunları bu uyarı olarak işaretlenmiş bir işlev içeri aktarmaya çalışırsanız `__clrcall`.  
  
 Aşağıdaki örnek C4272 oluşturur:  
  
```  
// C4272.cpp  
// compile with: /c /W1 /clr  
__declspec(dllimport) void __clrcall Test();   // C4272  
__declspec(dllimport) void Test2();   // OK  
```