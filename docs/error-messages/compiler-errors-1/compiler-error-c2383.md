---
title: Derleyici Hatası C2383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81624ccd7f4857cb2f7d8474d393a9743ab1a2b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2383"></a>Derleyici Hatası C2383
'*sembol*': varsayılan bağımsız değişkenler üzerinde bu simgeyi izin verilmez  
  
 C++ derleyicisi varsayılan bağımsız değişkenler işaretçileri işlevlere izin vermiyor.  
  
 Bu kod sürümlerinde Visual Studio 2005 önce Visual C++ derleyicisi tarafından kabul edildi ancak şimdi hata verir. Visual C++ tüm sürümlerinde çalışır kodu için bir işaretçi işlev bağımsız değişkeni için varsayılan bir değer atamayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, C2383 oluşturur ve olası bir çözüm gösterilmektedir:  
  
```cpp  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```