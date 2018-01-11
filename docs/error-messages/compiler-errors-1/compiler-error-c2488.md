---
title: "Derleyici Hatası C2488 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2488
dev_langs: C++
helpviewer_keywords: C2488
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 49365295e09f9e4f1d2bf3319c80e40a1e562091
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2488"></a>Derleyici Hatası C2488
'tanımlayıcısı': 'naked' yalnızca uygulanabilir üyesi olmayan işlev tanımları  
  
 [Naked](../../cpp/naked-cpp.md) öznitelik, bir işlev bildirimi uygulandı.  
  
 Aşağıdaki örnek C2488 oluşturur:  
  
```  
// C2488.cpp  
// compile with: /c  
// processor: x86  
__declspec( naked ) void func();   // C2488  declaration, not definition  
__declspec( naked ) void i;   // C2488  i is not a function  
  
__declspec( naked ) void func() {}   // OK  
```