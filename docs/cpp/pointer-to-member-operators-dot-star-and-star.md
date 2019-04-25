---
title: İşaretçi-üye işleçleri:. * ve -&gt;*
ms.date: 11/04/2016
f1_keywords:
- .*
- ->*
helpviewer_keywords:
- expressions [C++], pointer
- pointer-to-member operators [C++]
- .* operator
- expressions [C++], operators
- ->* operator
ms.assetid: 2632be3f-1c81-4523-b56c-982a92a68688
ms.openlocfilehash: 60dad0e3134662957ee21396d330af795e80918e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267669"
---
# <a name="pointer-to-member-operators--and--gt"></a>İşaretçi-üye işleçleri:. * ve -&gt;*

## <a name="syntax"></a>Sözdizimi

```
expression .* expression
expression ->* expression
```

## <a name="remarks"></a>Açıklamalar

İşaretçi-üye işleçleri. * ve ->\*, ifadenin sol tarafında belirtilen nesne için belirli bir sınıf üyesinin değerini döndürür.  Sağ tarafta sınıfın bir üyesi belirtilmelidir.  Aşağıdaki örnekte, bu işleçlerin nasıl kullanılacağı gösterilmektedir.

```cpp
// expre_Expressions_with_Pointer_Member_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

class Testpm {
public:
   void m_func1() { cout << "m_func1\n"; }
   int m_num;
};

// Define derived types pmfn and pmd.
// These types are pointers to members m_func1() and
// m_num, respectively.
void (Testpm::*pmfn)() = &Testpm::m_func1;
int Testpm::*pmd = &Testpm::m_num;

int main() {
   Testpm ATestpm;
   Testpm *pTestpm = new Testpm;

// Access the member function
   (ATestpm.*pmfn)();
   (pTestpm->*pmfn)();   // Parentheses required since * binds
                        // less tightly than the function call.

// Access the member data
   ATestpm.*pmd = 1;
   pTestpm->*pmd = 2;

   cout  << ATestpm.*pmd << endl
         << pTestpm->*pmd << endl;
   delete pTestpm;
}
```

## <a name="output"></a>Çıkış

```Output
m_func1
m_func1
1
2
```

Yukarıdaki örnekte bir üye işaretçisi olan `pmfn`, `m_func1` üye işlevini çağırmak için kullanılır. Diğer bir üye işaretçisi olan `pmd`, `m_num` üyesine erişmek için kullanılır.

. * ikili işleci, sınıf türünden bir nesne olması gereken ilk işlenenini, üye işleci türünde olması gereken ikinci işleneniyle birleştirir.

İkili işleç -> *, sınıf türünden bir nesneye bir işaretçi olması gereken ilk işleneni, ile bir üye işaretçisi türü olması gereken ikinci işleneniyle birleştirir.

.* işlecini içeren bir ifadede, ilk işlenen ikinci işlenende belirtilen üyenin işaretçisinin sınıf türünde olmalı ve bu işaretçi tarafından erişilebilmelidir veya bu sınıftan belirsiz bir şekilde yürütülen ve bu sınıf tarafından erişilebilen bir türde olmalıdır.

-> İçeren bir ifadede * işleci, ilk işlenen ikinci işlenende türü türün "sınıf türü işaretçisi" belirtilmelidir veya bu türü kesin bir şekilde bu sınıftan türetilmelidir.

## <a name="example"></a>Örnek

Aşağıdaki sınıfları ve program parçasını göz önünde bulundurun:

```cpp
// expre_Expressions_with_Pointer_Member_Operators2.cpp
// C2440 expected
class BaseClass {
public:
   BaseClass(); // Base class constructor.
   void Func1();
};

// Declare a pointer to member function Func1.
void (BaseClass::*pmfnFunc1)() = &BaseClass::Func1;

class Derived : public BaseClass {
public:
   Derived();  // Derived class constructor.
   void Func2();
};

// Declare a pointer to member function Func2.
void (Derived::*pmfnFunc2)() = &Derived::Func2;

int main() {
   BaseClass ABase;
   Derived ADerived;

   (ABase.*pmfnFunc1)();   // OK: defined for BaseClass.
   (ABase.*pmfnFunc2)();   // Error: cannot use base class to
                           // access pointers to members of
                           // derived classes.

   (ADerived.*pmfnFunc1)();   // OK: Derived is unambiguously
                              // derived from BaseClass.
   (ADerived.*pmfnFunc2)();   // OK: defined for Derived.
}
```

Sonucu. * veya ->\* işaretçi-üye işleçleri olan nesne veya işlev üye işaretçisinin bildiriminde belirtilen türde. Bu nedenle, yukarıdaki örnekte `ADerived.*pmfnFunc1()` ifadesinin sonucu void döndüren bir işlev işaretçisidir. Bu, ikinci işlenen l değerindeyse bir l değeridir.

> [!NOTE]
>  Üye işleçleri işaretçilerinden birinin sonucu işlevse, sonuç yalnızca işlev çağrısı işlecinin işleneni olarak kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)