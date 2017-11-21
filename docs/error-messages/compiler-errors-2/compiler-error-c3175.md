---
title: "Derleyici Hatası C3175 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3175
dev_langs: C++
helpviewer_keywords: C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2b8ff8052a9d54e12a4eca6a54701708096352a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3175"></a>Derleyici Hatası C3175
'function1': yönetilen bir türde bir yöntem yönetilmeyen işlevi 'function2' çağrılamıyor  
  
 Yönetilmeyen İşlevler yönetilen sınıflar üye işlevlerini çağrılamaz.  
  
 Aşağıdaki örnek C3175 oluşturur:  
  
```  
// C3175_2.cpp  
// compile with: /clr  
  
ref struct A {  
   static void func() {  
   }  
};  
  
#pragma unmanaged   // remove this line to resolve  
  
void func2() {  
   A::func();   // C3175  
}  
  
#pragma managed  
  
int main() {  
   A ^a = gcnew A;  
   func2();  
}  
```  
