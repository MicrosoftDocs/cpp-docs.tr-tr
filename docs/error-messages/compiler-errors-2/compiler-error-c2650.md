---
title: Derleyici Hatası C2650 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2650
dev_langs:
- C++
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee76b2d80ff76033f6776b91ee90e52ef5e200cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232241"
---
# <a name="compiler-error-c2650"></a>Derleyici Hatası C2650
'işleci': sanal işlev olamaz  
  
 A `new` veya `delete` işleci bildirilen `virtual`. Bu işleçleri `static` üye işlevleri ve olamaz `virtual`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2650 oluşturur:  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```