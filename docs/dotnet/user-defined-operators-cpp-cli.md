---
title: "Kullanıcı tanımlı işleçler (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73a397664d5e5a9074731b6eac879fe965580f05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="user-defined-operators-ccli"></a>Kullanıcı Tanımlı İşleçler (C++/CLI)
Yönetilen türler için kullanıcı tanımlı işleçler statik üyeleri veya örnek üyeleri olarak ya da genel kapsamlı izin verilir. Ancak, yalnızca statik işleçleri meta veriler üzerinden Visual C++ dışındaki bir dilde yazılmış istemcilere erişilebilir.  
  
 Bir başvuru türü statik bir kullanıcı tarafından tanımlanan işleci parametrelerden biri bunlardan biri olmalıdır:  
  
-   Bir tanıtıcı (`type` ^) kapsayan türünün bir örneği için.  
  
-   Bir başvuru türü yöneltme (`type`^ & veya türü ^ %) kapsayan türünün bir örneği için bir tanıtıcı için.  
  
 Bir değer türü statik bir kullanıcı tarafından tanımlanan işleci parametrelerden biri bunlardan biri olmalıdır:  
  
-   Aynı türde kapsayan değer türü.  
  
-   İşaretçi türü yöneltme (`type`^) kapsayan türü.  
  
-   Bir başvuru türü yöneltme (`type`% veya `type`&) kapsayan türü.  
  
-   Bir başvuru türü yöneltme (`type`^ % veya `type`^ &) işlenecek.  
  
 Aşağıdaki işleçleri tanımlayabilirsiniz:  
  
|İşleç|Birli/ikili Forms?|  
|--------------|--------------------------|  
|!|Birli|  
|!=|İkili|  
|%|İkili|  
|&|Birli ve ikili|  
|&&|İkili|  
|*|Birli ve ikili|  
|+|Birli ve ikili|  
|++|Birli|  
|,|İkili|  
|-|Birli ve ikili|  
|--|Birli|  
|->|Birli|  
|/|İkili|  
|<|İkili|  
|<<|İkili|  
|\<=|İkili|  
|=|İkili|  
|==|İkili|  
|>|İkili|  
|>=|İkili|  
|>>|İkili|  
|^|İkili|  
|false|Birli|  
|true|Birli|  
|&#124;|İkili|  
|&#124;&#124;|İkili|  
|~|Birli|  
  
## <a name="example"></a>Örnek  
  
```cpp  
// mcppv2_user-defined_operators.cpp  
// compile with: /clr  
using namespace System;  
public ref struct X {  
   X(int i) : m_i(i) {}  
   X() {}  
  
   int m_i;  
  
   // static, binary, user-defined operator  
   static X ^ operator + (X^ me, int i) {  
      return (gcnew X(me -> m_i + i));  
   }  
  
   // instance, binary, user-defined operator  
   X^ operator -( int i ) {  
      return gcnew X(this->m_i - i);  
   }  
  
   // instance, unary, user-defined pre-increment operator  
   X^ operator ++() {  
      return gcnew X(this->m_i++);  
   }  
  
   // instance, unary, user-defined post-increment operator  
   X^ operator ++(int i) {  
      return gcnew X(this->m_i++);  
   }  
  
   // static, unary user-defined pre- and post-increment operator  
   static X^ operator-- (X^ me) {  
      return (gcnew X(me -> m_i - 1));  
   }  
};  
  
int main() {  
   X ^hX = gcnew X(-5);  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX + 1;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX - (-1);  
   System::Console::WriteLine(hX -> m_i);  
  
   ++hX;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX++;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX--;  
   System::Console::WriteLine(hX -> m_i);  
  
   --hX;  
   System::Console::WriteLine(hX -> m_i);  
}  
```  
  
```Output  
-5  
-4  
-3  
-2  
-1  
-2  
-3  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek yalnızca kullandığınızda kullanılabilir olan işleci Birleştirici gösterir **/CLR** derlemek için. İşleç Birleştirici atama formun ikili işleç oluşturur, varsa tanımlı değil, burada atama işlecinin sol tarafındaki bir CLR türü.  
  
```cpp  
// mcppv2_user-defined_operators_2.cpp  
// compile with: /clr  
ref struct A {  
   A(int n) : m_n(n) {};  
   static A^ operator + (A^ r1, A^ r2) {  
      return gcnew A( r1->m_n + r2->m_n);  
   };  
   int m_n;  
};  
  
int main() {  
   A^ a1 = gcnew A(10);  
   A^ a2 = gcnew A(20);  
  
   a1 += a2;   // a1 = a1 + a2   += not defined in source  
   System::Console::WriteLine(a1->m_n);  
}  
```  
  
```Output  
30  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve yapılar](../windows/classes-and-structs-cpp-component-extensions.md)