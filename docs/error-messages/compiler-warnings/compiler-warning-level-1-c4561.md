---
title: Derleyici Uyarısı (düzey 1) C4561 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4561
dev_langs:
- C++
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4862d7f570faea3e362a505e67bddaf504b32de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4561"></a>Derleyici Uyarısı (düzey 1) C4561
'__fastcall' ile uyumsuz ' / clr' seçeneği: dönüştürme '\__stdcall'  
  
 [__Fastcall](../../cpp/fastcall.md) işlevi çağırma kuralı ile kullanılamaz [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği. Derleyici çağrıları yoksayar `__fastcall`. Bu uyarıyı çözmenin çağrıları ya da kaldırma **__fastcall** veya olmadan derleme **/CLR**.  
  
 Aşağıdaki örnek C4561 oluşturur:  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```