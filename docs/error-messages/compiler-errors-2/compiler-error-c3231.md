---
title: "Derleyici Hatası C3231 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3231
dev_langs: C++
helpviewer_keywords: C3231
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5d3cf8747f25fdccda1467e894f95d8bcfb3525c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3231"></a>Derleyici Hatası C3231
'arg': şablon tür bağımsız değişkeni bir genel tür parametresi kullanamazsınız  
  
 Şablonları derleme zamanında örneği, ancak genel türler çalışma zamanında örneği. Bu nedenle, şablon zaman genel tür son bilinen çalışma zamanında başlatılamaz olduğundan, şablon çağırabilirsiniz genel kod oluşturmak mümkün değil.  
  
 Aşağıdaki örnek C3231 oluşturur:  
  
```  
// C3231.cpp  
// compile with: /clr /LD  
template <class T> class A;  
  
generic <class T>  
ref class C {  
   void f() {  
      A<T> a;   // C3231  
   }  
};  
```