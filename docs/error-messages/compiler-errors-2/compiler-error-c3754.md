---
title: "Derleyici Hatası C3754 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3754
dev_langs: C++
helpviewer_keywords: C3754
ms.assetid: 14b877bc-9277-40ec-af1c-196a58b45f10
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 01fe6b5568da2e55d5ade4eca22a84ea4a0041e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
