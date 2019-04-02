---
title: -Clr ile C stili yayınlar (C + +/ CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
ms.openlocfilehash: 31dc0db16e960e640c08249e78e710950778a927
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787855"
---
# <a name="c-style-casts-with-clr-ccli"></a>/clr ile C Türü Atamalar (C++/CLI)

Aşağıdaki konu, yalnızca ortak dil çalışma zamanı için geçerlidir.

CLR Türleri ile kullanıldığında, derleyici C tarzı dönüştürme şu sırayla aşağıda listelenen yayınları birine eşlemeye çalışır:

1. const_cast

2. safe_cast

3. safe_cast artı const_cast

4. static_cast

5. static_cast artı const_cast

Yukarıda listelenen yayınları hiçbiri geçerli olup olmadığını ve ifade türü ve hedef türü CLR başvuru türleri ise, bir çalışma zamanı denetimi için (castclass MSIL yönergesi) C stili tür dönüştürme eşler. Aksi takdirde, C stili tür dönüştürme geçersiz olarak kabul edilir ve derleyici bir hata verir.

## <a name="remarks"></a>Açıklamalar

C stili tür dönüştürme önerilmez. İle derlerken [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md), kullanın [safe_cast](safe-cast-cpp-component-extensions.md).

Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir. bir **const_cast**.

```cpp
// cstyle_casts_1.cpp
// compile with: /clr
using namespace System;

ref struct R {};
int main() {
   const R^ constrefR = gcnew R();
   R^ nonconstR = (R^)(constrefR);
}
```

Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir. bir **safe_cast**.

```cpp
// cstyle_casts_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Object ^ o = "hello";
   String ^ s = (String^)o;
}
```

Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir. bir **safe_cast** yanı sıra **const_cast**.

```cpp
// cstyle_casts_3.cpp
// compile with: /clr
using namespace System;

ref struct R {};
ref struct R2 : public R {};

int main() {
   const R^ constR2 = gcnew R2();
   try {
   R2^ b2DR = (R2^)(constR2);
   }
   catch(InvalidCastException^ e) {
      System::Console::WriteLine("Invalid Exception");
   }
}
```

Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir. bir **static_cast**.

```cpp
// cstyle_casts_4.cpp
// compile with: /clr
using namespace System;

struct N1 {};
struct N2 {
   operator N1() {
      return N1();
   }
};

int main() {
   N2 n2;
   N1 n1 ;
   n1 = (N1)n2;
}
```

Aşağıdaki örnek, bir C eşleyen tarzı dönüştürme gösterir. bir **static_cast** yanı sıra **const_cast**.

```cpp
// cstyle_casts_5.cpp
// compile with: /clr
using namespace System;
struct N1 {};

struct N2 {
   operator const N1*() {
      static const N1 n1;
      return &n1;
   }
};

int main() {
   N2 n2;
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast
}
```

Aşağıdaki örnek, bir C çalışma zamanı denetlemek için eşlenen tarzı dönüştürme gösterir.

```cpp
// cstyle_casts_6.cpp
// compile with: /clr
using namespace System;

ref class R1 {};
ref class R2 {};

int main() {
   R1^ r  = gcnew R1();
   try {
      R2^ rr = ( R2^)(r);
   }
   catch(System::InvalidCastException^ e) {
      Console::WriteLine("Caught expected exception");
   }
}
```

Aşağıdaki örnek, bir geçersiz C, derleyici neden olan hata verecek tarzı dönüştürme gösterir.

```cpp
// cstyle_casts_7.cpp
// compile with: /clr
using namespace System;
int main() {
   String^s = S"hello";
   int i = (int)s;   // C2440
}
```

## <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)