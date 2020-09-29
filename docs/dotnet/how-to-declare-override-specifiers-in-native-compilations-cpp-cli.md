---
title: 'Nasıl yapılır: geçersiz kılma belirticilerini bildirme (C++/CLı)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: 92bdc41cf9ebe2389f2d22dab211029899283266
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414600"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Nasıl yapılır: Yerel Derlemelerde Geçersiz Kılma Tanımlayıcılarını Bildirme (C++/CLI)

[Sealed](../extensions/sealed-cpp-component-extensions.md), [abstract](../extensions/abstract-cpp-component-extensions.md)ve [override](../extensions/override-cpp-component-extensions.md) , **/ZW** veya [/clr](../build/reference/clr-common-language-runtime-compilation.md)kullanmayan derlemelerde kullanılabilir.

> [!NOTE]
> ISO C++ 11 standart dili, [geçersiz kılma](../cpp/override-specifier.md) tanımlayıcısına ve [son](../cpp/final-specifier.md) tanımlayıcıya sahiptir ve her ikisi de `final` **`sealed`** yalnızca yerel olarak derlenmesi amaçlanan kod yerine Visual Studio kullanımı içinde desteklenir.

## <a name="example-sealed-is-valid"></a>Örnek: Sealed geçerli

### <a name="description"></a>Description

Aşağıdaki örnek, yerel derlemelerde **`sealed`** geçerli olduğunu gösterir.

### <a name="code"></a>Kod

```cpp
// sealed_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
   virtual void g();
};

class X : public I1 {
public:
   virtual void g() sealed {}
};

class Y : public X {
public:

   // the following override generates a compiler error
   virtual void g() {}   // C3248 X::g is sealed!
};
```

## <a name="example-override-is-valid"></a>Örnek: override geçerli

### <a name="description"></a>Description

Sonraki örnek, yerel derlemelerde `override` geçerli olduğunu gösterir.

### <a name="code"></a>Kod

```cpp
// override_native_keyword.cpp
#include <stdio.h>
__interface I1 {
   virtual void f();
};

class X : public I1 {
public:
   virtual void f() override {}   // OK
   virtual void g() override {}   // C3668 I1::g does not exist
};
```

## <a name="example-abstract-is-valid"></a>Örnek: Özet geçerli

### <a name="description"></a>Description

Bu örnek **`abstract`** , yerel derlemelerde geçerli olduğunu gösterir.

### <a name="code"></a>Kod

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Geçersiz kılma belirticileri](../extensions/override-specifiers-cpp-component-extensions.md)
