---
title: Derleyici Hatası C2186 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2186
dev_langs:
- C++
helpviewer_keywords:
- C2186
ms.assetid: 284bfb7e-ab85-4fcb-9864-1ddf7f6c94ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f497cfcf0849ff5ffc46d8c9a1c8b6e1c8ceafb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167635"
---
# <a name="compiler-error-c2186"></a>Derleyici Hatası C2186
'işleci': 'void' türünde geçersiz işlenen  
  
 Sahip bir `void` işlenen.  
  
 Aşağıdaki örnek C2186 oluşturur:  
  
```  
// C2186.cpp  
// compile with: /c  
void func1( void );  
int  func2( void );  
int i = 2 + func1();   // C2186 func1() is type void  
int j = 2 + func2();   // OK both operands are type int  
```