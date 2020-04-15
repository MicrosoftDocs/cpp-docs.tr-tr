---
title: 'Nasıl yapılır: Geçersiz Kılma Belirtileyicilerini Bildir (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: 9f3f6855f257d0af250b9bbdd2c0360b308ce775
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374444"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Nasıl yapılır: Yerel Derlemelerde Geçersiz Kılma Tanımlayıcılarını Bildirme (C++/CLI)

[mühürlü](../extensions/sealed-cpp-component-extensions.md), [özet](../extensions/abstract-cpp-component-extensions.md)ve [geçersiz kılma](../extensions/override-cpp-component-extensions.md) **/ZW** veya [/clr](../build/reference/clr-common-language-runtime-compilation.md)kullanmayan derlemelerde mevcuttur.

> [!NOTE]
> ISO C++11 Standart dili [geçersiz kılma](../cpp/override-specifier.md) tanımlayıcısına ve [son](../cpp/final-specifier.md) tanımlayıcıya sahiptir ve her ikisi de `final` yalnızca `sealed` yerel olarak derlenecek kod yerine Visual Studio Use'da desteklenir.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, `sealed` yerel derlemelerde geçerli olduğunu gösterir.

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

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Sonraki örnek, `override` yerel derlemelerde geçerli olduğunu gösterir.

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

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Bu örnek, `abstract` yerel derlemelerde geçerli olduğunu gösterir.

### <a name="code"></a>Kod

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Geçersiz Kılma Tanımlayıcıları](../extensions/override-specifiers-cpp-component-extensions.md)
