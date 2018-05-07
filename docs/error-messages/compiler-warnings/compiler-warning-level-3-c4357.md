---
title: Derleyici Uyarısı (Düzey 3) C4357 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4357
dev_langs:
- C++
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79bb609b051def4f84924c1d9ebbcd9574d2ce77
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4357"></a>Derleyici Uyarısı (Düzey 3) C4357
param dizisi için biçimsel bağımsız değişken listesi değişkeninde 'del 'function' oluşturulurken göz ardı' temsilci seçme  
  
 `ParamArray` Özniteliği yoksayıldı ve `function` değişken bağımsız değişkenlerle çağrılamaz.  
  
 Aşağıdaki örnek C4357 oluşturur:  
  
```  
// C4357.cpp  
// compile with: /clr /W3 /c  
using namespace System;  
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357  
  
public delegate void g(int i, array<Object^>^ varargs);   // OK  
```