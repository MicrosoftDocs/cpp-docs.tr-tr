---
title: "Derleyici Hatası C2701 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2701
dev_langs: C++
helpviewer_keywords: C2701
ms.assetid: 31cf2ab7-ced9-4f75-aa51-e169e20407fb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9aff17907695e48661af7d6e9a6538af4f22ba4c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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