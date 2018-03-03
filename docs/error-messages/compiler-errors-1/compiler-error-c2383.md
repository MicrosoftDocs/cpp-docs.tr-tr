---
title: "Derleyici Hatası C2383 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7f89545b9428bd5e901c72d895b5c23317646c26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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