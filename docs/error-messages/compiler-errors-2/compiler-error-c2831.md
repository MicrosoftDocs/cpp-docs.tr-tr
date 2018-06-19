---
title: Derleyici Hatası C2831 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2831
dev_langs:
- C++
helpviewer_keywords:
- C2831
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73cd133d5dc355dc11c0128aea0ddb44dccafe80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242816"
---
# <a name="compiler-error-c2831"></a>Derleyici Hatası C2831
'işleci işleci' varsayılan parametreleri olamaz  
  
 Yalnızca üç işleçleri varsayılan parametreleri sahip olabilir:  
  
-   [new](../../cpp/new-operator-cpp.md)  
  
-   Atama =  
  
-   Sol parantez)  
  
 Aşağıdaki örnek C2831 oluşturur:  
  
```  
// C2831.cpp  
// compile with: /c  
#define BINOP <=  
class A {  
public:  
   int i;  
   int operator BINOP(int x = 1) {   // C2831  
   // try the following line instead  
   // int operator BINOP(int x) {  
      return i+x;  
   }  
};  
```