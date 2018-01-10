---
title: "Derleyici Hatası C3673 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3673
dev_langs: C++
helpviewer_keywords: C3673
ms.assetid: bb6d2079-05af-4e2c-be0e-75c892e6c590
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05a29c07a5e6717e3b04b16bf7dd72293023b2e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3673"></a>Derleyici Hatası C3673
'type': sınıf kopya oluşturucu yok  
  
 Kullanıcı tanımlı oluşturucusu, CLR ref türlerin kopyalamak için gereklidir. Daha fazla bilgi için bkz: [başvuru türleri için C++ yığın anlamları](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3673 oluşturur.  
  
```  
// C3673.cpp  
// compile with: /clr  
public ref struct R {  
public:  
   R() {}  
   // Uncomment the following line to resolve.  
   // R(R% p) {}  
};  
  
int main() {  
   R r;  
   R s = r;   // C3673  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3673 oluşturur.  
  
```  
// C3673_b.cpp  
// compile with: /clr /c  
// C3673 expected  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
ref class MyAttr : public Attribute {  
public:  
   MyAttr() {}  
   // Uncomment the following line to resolve.  
   // MyAttr(int i) {}  
   property int Priority;  
   property int Version;  
};  
  
[MyAttr]   
ref class ClassA {};   // OK, no arguments  
  
[MyAttr(Priority = 1)]   
ref class ClassB {};   // OK, named argument  
  
[MyAttr(123)]  
ref class ClassC {};   // Positional argument  
  
[MyAttr(123, Version = 1)]  
ref class ClassD {};   // Positional and named  
```