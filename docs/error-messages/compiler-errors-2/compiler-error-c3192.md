---
title: Derleyici Hatası C3192 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3192
dev_langs:
- C++
helpviewer_keywords:
- C3192
ms.assetid: 8b0083d4-706f-46f6-858a-e1d9af464cf8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e014e9ad54963212ef580e14870138273e882a47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250934"
---
# <a name="compiler-error-c3192"></a>Derleyici Hatası C3192
sözdizimi hatası: ' ^' öneki işleci değil (şunu mu demek istediniz ' *'?)  
  
 Bir tanıtıcı başvuru operatör olarak kullanılamaz.  
  
 Aşağıdaki örnek C3192 oluşturur:  
  
```  
// C3192.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   MyClass () {}  
   MyClass(MyClass%) {}  
};  
  
int main() {  
   MyClass ^ s = gcnew MyClass;   
   MyClass b = ^s;   // C3192  
  
   // OK  
   MyClass b2 = *s;  
}  
```