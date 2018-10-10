---
title: Derleyici Hatası C2059 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2059
dev_langs:
- C++
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78640f61cb1d0f81fc405cbc3cfce16be0de5022
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890081"
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

Bir sembol olarak gerçekleşebilir nothing olarak değerlendirilirse C2059 alabilirsiniz, **/D** `symbol` **=** derlemek için kullanılır.

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