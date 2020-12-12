---
description: 'Daha fazla bilgi edinin: User-Defined Işleçleri (C++/CLı)'
title: Kullanıcı Tanımlı İşleçler (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
ms.openlocfilehash: e94a4d28517fc253fb8284a604b01a5f9d76de22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204231"
---
# <a name="user-defined-operators-ccli"></a>Kullanıcı Tanımlı İşleçler (C++/CLI)

Yönetilen türler için Kullanıcı tanımlı işleçlere statik üyeler veya örnek Üyeler veya genel kapsam olarak izin verilir. Ancak, Visual C++ dışında bir dilde yazılan istemciler için meta veriler aracılığıyla yalnızca statik işleçlere erişilebilir.

Bir başvuru türünde, statik Kullanıcı tanımlı bir işlecin parametrelerinden biri aşağıdakilerden biri olmalıdır:

- `type`Kapsayan tür örneğine bir tanıtıcı (^).

- Bir başvuru türü yöneltme ( `type` ^& veya tür ^%) kapsayan türdeki bir örneğe yönelik tanıtıcıya.

Değer türünde, statik Kullanıcı tanımlı bir işlecin parametrelerinden biri aşağıdakilerden biri olmalıdır:

- Kapsayan değer türü ile aynı türde.

- Kapsayan türe bir işaretçi türü yöneltme ( `type` ^).

- Kapsayan tür için bir başvuru türü yöneltme ( `type` % veya `type`&).

- Tanıtıcı için bir başvuru türü yöneltme ( `type` ^% veya `type` ^&).

Aşağıdaki işleçleri tanımlayabilirsiniz:

|Operatör|Birli/Ikili formlar?|
|--------------|--------------------------|
|!|Birli|
|!=|İkili|
|%|İkili|
|&|Birli ve Ikili|
|&&|İkili|
|*|Birli ve Ikili|
|+|Birli ve Ikili|
|++|Birli|
|,|İkili|
|-|Birli ve Ikili|
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
|yanlış|Birli|
|true|Birli|
|&#124;|İkili|
|&#124;&#124;|İkili|
|~|Birli|

## <a name="example-user-defined-operators"></a>Örnek: Kullanıcı tanımlı işleçler

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

## <a name="example-operator-synthesis"></a>Örnek: Işleç sensıs

Aşağıdaki örnek, yalnızca derlemek için **/clr** kullandığınızda kullanılabilir olan işleç birleştirini gösterir. İşleç birleştirme, atama işlecinin sol tarafındaki bir CLR türüne sahip olmadığı bir ikili işlecin atama formunu oluşturur.

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

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)
