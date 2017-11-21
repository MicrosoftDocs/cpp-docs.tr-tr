---
title: "Derleyici Uyarısı (Düzey 3) C4357 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4357
dev_langs: C++
helpviewer_keywords: C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4bb0d272a019da08a953d1be6f321135cc7595d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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