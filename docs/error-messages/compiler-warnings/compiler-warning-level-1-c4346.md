---
title: Derleyici Uyarısı (düzey 1) C4346
ms.date: 11/04/2016
f1_keywords:
- C4346
helpviewer_keywords:
- C4346
ms.assetid: 68ee562d-cca9-4a2a-9a1b-14ad1a1e7396
ms.openlocfilehash: 3ab519f612d5272b0562728917cc777f1de86b79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187251"
---
# <a name="compiler-warning-level-1-c4346"></a>Derleyici Uyarısı (düzey 1) C4346

' name ': bağımlı ad bir tür değil

Bağımsız bir ad bir tür olarak değerlendirilme ise [TypeName](../../cpp/typename.md) anahtar sözcüğü gereklidir. Tüm görsellerde C++aynı şekilde çalışacak kod için, bildirime `typename` ekleyin.

Aşağıdaki örnek C4346 oluşturur:

```cpp
// C4346.cpp
// compile with: /WX /LD
template<class T>
struct C {
   T::X* x;   // C4346
   // try the following line instead
   // typename T::X* x;
};
```

Aşağıdaki örneklerde **TypeName** anahtar sözcüğünün gerekli olduğu diğer örnekler gösterilmektedir:

```cpp
// C4346b.cpp
// compile with: /LD /W1
template<class T>
const typename T::X& f(typename T::Z* p);   // Required in both places

template<class T, int N>
struct L{};

template<class T>
struct M : public L<typename T::Type, T::Value>
{   // required on type argument, not on non-type argument
   typedef typename T::X   Type;
   Type f();   // OK: "Type" is a type-specifer
   typename T::X g();   // typename required
   operator typename T::Z();   // typename required
};
```

ve bu,

```cpp
// C4346c.cpp
// compile with: /LD /WX
struct Y {
   typedef int Y_t;
};

template<class T>
struct A {
   typedef Y A_t;
};

template<class T>
struct B {
   typedef /*typename*/ A<T>::A_t B_t;   // C4346 typename needed here
   typedef /*typename*/ B_t::Y_t  B_t2;   // typename also needed here
};
```
