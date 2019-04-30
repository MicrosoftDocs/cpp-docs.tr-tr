---
title: Derleyici Hatası C2059
ms.date: 03/26/2019
f1_keywords:
- C2059
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
ms.openlocfilehash: 2fb2aa86a1fd8f8e0710d787682fdd44abd941ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408673"
---
# <a name="compiler-error-c2059"></a>Derleyici Hatası C2059

sözdizimi hatası: 'belirteci'

Belirteç sözdizimi hatası nedeniyle.

Aşağıdaki örnek, bir hata iletisi bildirir satır oluşturur `j`.

```
// C2059e.cpp
// compile with: /c
// C2143 expected
// Error caused by the incorrect use of '*'.
   int j*; // C2059
```

Hatanın nedenini belirlemek için yalnızca hata iletisinde listelenen satır, aynı zamanda yukarıdaki satırları inceleyin. Satırları incelenerek sorun hakkında hiçbir fikrimiz döndürürse, hata iletisinde listelenen satır ve belki de yukarıdaki birkaç satıra yorum deneyin.

Hata iletisi üzerinde hemen izleyen bir sembolün oluşursa bir `typedef` değişkeni, kaynak kodunda değişkeni tanımlandığından emin olun.

Tanımlayıcı olarak yeniden kullanılan önişlemci sembolü adıdır C2059 tetiklenir. Aşağıdaki örnekte, derleyicinin görür `DIGITS.ONE` numarası 1 ', geçerli olmayan bir sabit listesi öğe adı:

```cpp
#define ONE 1

enum class DIGITS {
    ZERO,
    ONE // error C2059
};
```

Bir sembol olarak gerçekleşebilir nothing olarak değerlendirilirse C2059 alabilirsiniz, **/D**_sembol_ **=** derlemek için kullanılır.

```
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

Bir yapının bir işlevin varsayılan bağımsız değişkenler belirten bir uygulamayı derlediğinizde C2059 oluşabilen başka bir durumdur. Bağımsız değişken için varsayılan değeri bir ifade olmalıdır. Başlatıcı listesi — Örneğin, bir yapı başlatmak için kullanılan — bir ifade değil.  Bu sorunu gidermek için gerekli başlatma gerçekleştirmek için bir oluşturucu tanımlar.

Aşağıdaki örnek, C2059 oluşturur:

```
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

C2059 için hatalı oluşturulmuş tür dönüştürme ortaya çıkabilir.

Aşağıdaki örnek, C2059 oluşturur:

```
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

Nokta içeren bir ad alanı adı oluşturmaya çalışırsanız C2059 da meydana gelebilir.

Aşağıdaki örnek, C2059 oluşturur:

```
// C2059d.cpp
// compile with: /c
namespace A.B {}   // C2059

// OK
namespace A  {
   namespace B {}
}
```

C2059 bir adı olabilmek operatörün olduğunda meydana gelebilir (`::`, `->`, ve `.`) anahtar sözcüğüyle gelmelidir `template`, bu örnekte gösterildiği gibi:

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

Varsayılan olarak, C++ olduğunu varsayar `AY::Rebind` olmayan bir şablon; bu nedenle, aşağıdaki `<` daha az yorumlanır-işareti.  Derleyici açıkça, bildirmeniz gerekir `Rebind` böylece doğru açılı ayraç ayrıştırmak bir şablondur. Bu hatayı düzeltmek için `template` anahtar sözcüğü, burada gösterildiği gibi bağımlı tür adı:

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
