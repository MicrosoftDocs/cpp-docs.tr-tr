---
title: -Clr (C++/CLI) Ile C stili atamalar
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- C-style casts and /clr
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
ms.openlocfilehash: 2b7e492c62047e3b38224637f842d8a7fcbae84f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172600"
---
# <a name="c-style-casts-with-clr-ccli"></a>/clr ile C Türü Atamalar (C++/CLI)

Aşağıdaki konu yalnızca ortak dil çalışma zamanı için geçerlidir.

CLR türleriyle kullanıldığında, derleyici C stili tür dönüştürme 'yı aşağıda listelenen atamalardan birine eşlemeyi dener, aşağıdaki sırayla:

1. const_cast

2. safe_cast

3. safe_cast Plus const_cast

4. static_cast

5. static_cast Plus const_cast

Yukarıda listelenen türlerden hiçbiri geçerli değilse ve ifadenin türü ve hedef türü CLR başvuru türleridir, C stili tür dönüştürme işlemi bir çalışma zamanı denetimi (roclass MSIL yönergesi) ile eşleşir. Aksi halde, C stili bir tür dönüştürme geçersiz olarak değerlendirilir ve derleyici bir hata verir.

## <a name="remarks"></a>Açıklamalar

C stili tür dönüştürme önerilmez. [/Clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md)ile derlerken [safe_cast](safe-cast-cpp-component-extensions.md)kullanın.

Aşağıdaki örnek, bir **const_cast**eşlenen C stili bir tür dönüştürmeyi gösterir.

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

Aşağıdaki örnek, bir **safe_cast**eşlenen C stili bir tür dönüştürmeyi gösterir.

```cpp
// cstyle_casts_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Object ^ o = "hello";
   String ^ s = (String^)o;
}
```

Aşağıdaki örnek, bir **safe_cast** ve **Const_cast**eşleyen bir C stili tür dönüştürme gösterir.

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

Aşağıdaki örnek, bir **static_cast**eşlenen C stili bir tür dönüştürmeyi gösterir.

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

Aşağıdaki örnek, bir **static_cast** ve **Const_cast**eşleyen bir C stili tür dönüştürme gösterir.

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

Aşağıdaki örnekte, bir çalışma zamanı denetimi ile eşleşen bir C stili tür dönüştürme gösterilmektedir.

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

Aşağıdaki örnekte, derleyicinin bir hata vermesine neden olan geçersiz bir C stili atama gösterilmektedir.

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

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
