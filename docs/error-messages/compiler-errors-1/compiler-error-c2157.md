---
title: Derleyici Hatası C2157 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2157
dev_langs:
- C++
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62e2867ed7e95f6b135581260103c9d5e1386fb9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168548"
---
# <a name="compiler-error-c2157"></a>Derleyici Hatası C2157
'function': pragma listesinde kullanmadan önce bildirilmesi gerekir  
  
 İşlev adı işlevleri için listesinde başvurulmadan önce bildirilmemiş bir [alloc_text](../../preprocessor/alloc-text.md) pragması.  
  
 Aşağıdaki örnek C2157 oluşturur:  
  
```  
// C2157.cpp  
// compile with: /c  
#pragma alloc_text( "func", func)   // C2157  
  
// OK  
extern "C" void func();  
#pragma alloc_text( "func", func)  
```