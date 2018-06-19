---
title: Derleyici Hatası C2701 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2701
dev_langs:
- C++
helpviewer_keywords:
- C2701
ms.assetid: 31cf2ab7-ced9-4f75-aa51-e169e20407fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42529b3cd6e0fae7ff47ef47b60bc0a0acb42b53
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231311"
---
# <a name="compiler-error-c2701"></a>Derleyici Hatası C2701
'function': işlevi şablonu yerel bir sınıfın bir arkadaş olamaz  
  
 Yerel bir sınıf bir şablon işlevi arkadaş işlev olarak sahip olamaz.  
  
 Aşağıdaki örnek C2701 oluşturur:  
  
```  
// C2701.cpp  
// compile with: /c  
template<typename T>   // OK  
void f1(const T &);  
  
void MyFunction() {  
   class MyClass {  
      template<typename T> friend void f2(const T &);   // C2701  
   };  
}  
```