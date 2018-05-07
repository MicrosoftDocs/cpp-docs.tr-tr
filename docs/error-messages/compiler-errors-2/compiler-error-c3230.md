---
title: Derleyici Hatası C3230 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3230
dev_langs:
- C++
helpviewer_keywords:
- C3230
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 494aa6a04b1ec4844e243807e103d4d106380739
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3230"></a>Derleyici Hatası C3230
'function': 'template' için şablon tür bağımsız değişkeni bir genel tür parametresi içeremez: 'param'  
  
 Şablonları derleme zamanında örneği, ancak genel türler çalışma zamanında örneği. Bu nedenle, şablon zaman genel tür son bilinen çalışma zamanında başlatılamaz olduğundan, şablon çağırabilirsiniz genel kod oluşturmak mümkün değil.  
  
 Aşağıdaki örnek C3230 oluşturur:  
  
```  
// C3230.cpp  
// compile with: /clr /LD  
template <class S>   
void f(S t);  
  
generic <class U>  
ref class C {  
   void f1(U x) {  
      f(x);   // C3230  
   }  
};  
```