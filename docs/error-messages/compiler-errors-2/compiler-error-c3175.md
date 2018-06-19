---
title: Derleyici Hatası C3175 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3175
dev_langs:
- C++
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 199895ecba509b291d3853f0adabb2b68eee1e49
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246409"
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
