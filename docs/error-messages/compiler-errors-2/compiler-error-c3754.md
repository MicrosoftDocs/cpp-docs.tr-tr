---
title: Derleyici Hatası C3754 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3754
dev_langs:
- C++
helpviewer_keywords:
- C3754
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8555732fbe3321c65a4da9689b0b8816ff356532
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3754"></a>Derleyici Hatası C3754
Oluşturucu temsilci: üye işlevi 'function', 'type' türünün bir örneğinde çağrılamaz  
  
 İşlevi içermeyen bir tür için bir işaretçi aracılığıyla işlevine bir çağrı yapıldı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3754 oluşturur:  
  
```  
// C3754a.cpp  
// compile with: /clr  
using namespace System;  
  
delegate void MyDel();  
  
interface class MyInterface {};  
  
ref struct MyClass : MyInterface {  
   void f() {}  
};  
  
int main() {  
   MyInterface^ p = gcnew MyClass;  
   MyDel^ q = gcnew MyDel(p, &MyClass::f);   // C3754  
   // try the following line instead  
//   MyDel^ q = gcnew MyDel(safe_cast<MyClass^>(p), &MyClass::f);  
}  
```  
