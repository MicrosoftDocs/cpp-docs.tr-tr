---
title: Derleyici Hatası C2488 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2488
dev_langs:
- C++
helpviewer_keywords:
- C2488
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cb64ea76ae38901b2db14ec4b68bba9db69f39c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225299"
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