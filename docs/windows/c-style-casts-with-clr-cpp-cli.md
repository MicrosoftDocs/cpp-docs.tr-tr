---
title: -Clr ile C stili yayınlar (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 28a92f115e2d5fdd3185285f245abf6d282efa7a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595012"
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

C stili tür dönüştürme önerilmez. İle derlerken [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md), kullanın [safe_cast](../windows/safe-cast-cpp-component-extensions.md).

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

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)