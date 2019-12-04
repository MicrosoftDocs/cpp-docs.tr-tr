---
title: Derleyici hatası C2059
ms.date: 03/26/2019
f1_keywords:
- C2059
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
ms.openlocfilehash: 1d51d4c7873d43a655dc11fa8e0fa297b8a69bff
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735950"
---
# <a name="compiler-error-c2059"></a>Derleyici hatası C2059

sözdizimi hatası: ' token '

Belirteç bir sözdizimi hatasına neden oldu.

Aşağıdaki örnek, `j`bildiren çizgi için bir hata iletisi oluşturur.

```cpp
// C2059e.cpp
// compile with: /c
// C2143 expected
// Error caused by the incorrect use of '*'.
   int j*; // C2059
```

Hatanın nedenini öğrenmek için yalnızca hata iletisinde listelenen satırı değil, aynı zamanda yukarıdaki satırları inceleyin. Satırları incelemek sorun hakkında hiçbir clue yoksa, hata iletisinde listelenen satırı ve belki de büyük olasılıkla birçok satırı açıklama olarak oluşturmayı deneyin.

Hata iletisi bir `typedef` değişkenini hemen izleyen bir sembol üzerinde oluşursa, değişkenin kaynak kodunda tanımlandığından emin olun.

Bir Önişlemci sembol adı tanımlayıcı olarak yeniden kullanıldığında C2059 tetiklenir. Aşağıdaki örnekte, derleyici `DIGITS.ONE` 1 sayısı olarak görür ve bu, Enum öğesi adı olarak geçerli değildir:

```cpp
#define ONE 1

enum class DIGITS {
    ZERO,
    ONE // error C2059
};
```

C2059, bir sembol hiçbir şey için hesaplanırsa, **/d**_symbol_ **=** derlemek için kullanıldığında meydana gelebilir.

```cpp
// C2059a.cpp
// compile with: /DTEST=
#include <stdio.h>

int main() {
   #ifdef TEST
      printf_s("\nTEST defined %d", TEST);   // C2059
   #else
      printf_s("\nTEST not defined");
   #endif
}
```

Bir işlevin varsayılan bağımsız değişkenlerinde bir yapıyı belirten bir uygulama derlerken C2059 'in gerçekleşebileceği başka bir durum da olabilir. Bir bağımsız değişken için varsayılan değer bir ifade olmalıdır. Bir başlatıcı listesi — Örneğin, bir yapıyı başlatmak için kullanılan bir ifade değil.  Bu sorunu çözmek için gerekli başlatmayı gerçekleştirmek üzere bir Oluşturucu tanımlayın.

Aşağıdaki örnek C2059 oluşturur:

```cpp
// C2059b.cpp
// compile with: /c
struct ag_type {
   int a;
   float b;
   // Uncomment the following line to resolve.
   // ag_type(int aa, float bb) : a(aa), b(bb) {}
};

void func(ag_type arg = {5, 7.0});   // C2059
void func(ag_type arg = ag_type(5, 7.0));   // OK
```

C2059, hatalı oluşturulmuş bir tür dönüştürme için gerçekleşebilir.

Aşağıdaki örnek C2059 oluşturur:

```cpp
// C2059c.cpp
// compile with: /clr
using namespace System;
ref class From {};
ref class To : public From {};

int main() {
   From^ refbase = gcnew To();
   To^ refTo = safe_cast<To^>(From^);   // C2059
   To^ refTo2 = safe_cast<To^>(refbase);   // OK
}
```

Ayrıca, bir nokta içeren bir ad alanı adı oluşturmaya çalıştığınızda C2059 de oluşabilir.

Aşağıdaki örnek C2059 oluşturur:

```cpp
// C2059d.cpp
// compile with: /c
namespace A.B {}   // C2059

// OK
namespace A  {
   namespace B {}
}
```

Bir ada sahip olabilecek bir operatör (`::`, `->`ve `.`), aşağıdaki örnekte gösterildiği gibi anahtar `template`sözcüğü gelmelidir:

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::Rebind<X>::Other AX; // error C2059
};
```

Varsayılan olarak, C++ `AY::Rebind` şablon olmadığını varsayar; Bu nedenle, aşağıdaki `<` küçüktür işareti olarak yorumlanır.  Derleyiciye, açılı ayracın doğru ayrıştırabilmesi için `Rebind` bir şablon olduğunu açıkça bildirmeniz gerekir. Bu hatayı düzeltmek için, aşağıda gösterildiği gibi, bağımlı türün adı üzerinde `template` anahtar sözcüğünü kullanın:

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::template Rebind<X>::Other AX; // correct
};
```
