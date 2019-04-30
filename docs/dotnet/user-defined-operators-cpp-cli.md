---
title: Kullanıcı Tanımlı İşleçler (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
ms.openlocfilehash: cf80eb4c440c1308e8ea06a563c18569e4e4ddf2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384510"
---
# <a name="user-defined-operators-ccli"></a>Kullanıcı Tanımlı İşleçler (C++/CLI)

Yönetilen türler için kullanıcı tanımlı işleçler statik üyeleri veya örnek üyeler olarak veya genel kapsamda izin verilmez. Ancak, yalnızca statik işleçleri meta veriler Visual C++ dışında bir dilde yazılmış istemcilere erişilebilir.

Bir başvuru türü statik bir kullanıcı tarafından tanımlanan işlecin parametrelerinden biri olmalıdır:

- Bir işleyici (`type` ^) kapsayan türde bir örnek.

- Bir başvuru türü yöneltme (`type`^ & veya türü ^ %) için bir tanıtıcı kapsayan türde bir örnek.

Bir değer türü statik bir kullanıcı tarafından tanımlanan işlecin parametrelerinden biri olmalıdır:

- Kapsayan değer türü olarak aynı türde.

- Bir işaretçi türü yöneltmesi (`type`^) kapsayan türü.

- Bir başvuru türü yöneltme (`type`% veya `type`&) kapsayan türü.

- Bir başvuru türü yöneltme (`type`^ % veya `type`^ &) işlemek için.

Aşağıdaki işleçleri tanımlayabilirsiniz:

|İşleç|Birli/ikili Forms?|
|--------------|--------------------------|
|!|Birli|
|!=|İkili|
|%|İkili|
|&|Tekli veya ikili|
|&&|İkili|
|*|Tekli veya ikili|
|+|Tekli veya ikili|
|++|Birli|
|,|İkili|
|-|Tekli veya ikili|
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

Aşağıdaki örnek kullandığınızda, yalnızca operatör birleştirmesinden gösterir **/CLR** derlemek için. Operatör birleştirmesinden ikili işleci atama formu oluşturur, varsa tanımlı değil, atama işlecinin sol tarafında sahip olduğu bir CLR türü.

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
