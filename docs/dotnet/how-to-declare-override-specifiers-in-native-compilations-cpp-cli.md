---
title: 'Nasıl yapılır: Geçersiz kılma tanımlayıcılarını bildirme (C + +/ CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- override specifiers in native compilation, overriding
ms.assetid: d0551836-9ac7-41eb-a6e9-a4b3ef60767d
ms.openlocfilehash: db74ef226242ec8f4f70f2769fbc8ba102a808c8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777187"
---
# <a name="how-to-declare-override-specifiers-in-native-compilations-ccli"></a>Nasıl yapılır: Yerel derlemelerde geçersiz kılma tanımlayıcılarını bildirme (C + +/ CLI)

[korumalı](../extensions/sealed-cpp-component-extensions.md), [soyut](../extensions/abstract-cpp-component-extensions.md), ve [geçersiz kılma](../extensions/override-cpp-component-extensions.md) kullanmayan derlemelerde kullanılabilir **/ZW** veya [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
>  ISO C ++ 11 standart dil sahip [geçersiz kılma](../cpp/override-specifier.md) tanımlayıcısı ve [son](../cpp/final-specifier.md) tanımlayıcısı ve hem de Visual Studio kullanımda desteklenir `final` yerine `sealed` kodda yöneliktir yalnızca yerel olarak derlenmiş.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, gösterir `sealed` yerel derlemelerde geçerlidir.

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

Sonraki örnek, gösterir `override` yerel derlemelerde geçerlidir.

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

Bu örnek, gösterir `abstract` yerel derlemelerde geçerlidir.

### <a name="code"></a>Kod

```cpp
// abstract_native_keyword.cpp
class X abstract {};

int main() {
   X * MyX = new X;   // C3622 cannot instantiate abstract class
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Geçersiz kılma tanımlayıcıları](../extensions/override-specifiers-cpp-component-extensions.md)
