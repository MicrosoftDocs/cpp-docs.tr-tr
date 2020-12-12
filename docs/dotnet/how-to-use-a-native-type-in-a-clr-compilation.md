---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır:/clr derlemesinde yerel tür kullanma'
title: 'Nasıl yapılır: bir-clr derlemesinde yerel tür kullanma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
ms.openlocfilehash: 8e8479bb64166faec841d9d69ce38b3e8e57e048
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286286"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>Nasıl yapılır: /clr Derlemesinde Yerel Tür Kullanma

Bir **/clr** derlemesinde yerel bir tür tanımlayabilir ve derleme içindeki bu yerel türün herhangi bir kullanımı geçerlidir. Ancak, yerel türler başvurulan meta verilerden kullanılmak üzere kullanılamaz.

Her derleme, kullanacağı her yerel türün tanımını içermelidir.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="examples"></a>Örnekler

Bu örnek, yerel bir türü tanımlayan ve kullanan bir bileşen oluşturur.

```cpp
// use_native_type_in_clr.cpp
// compile with: /clr /LD
public struct NativeClass {
   static int Test() { return 98; }
};

public ref struct ManagedClass {
   static int i = NativeClass::Test();
   void Test() {
      System::Console::WriteLine(i);
   }
};
```

Bu örnek, bileşeni tüketen bir istemciyi tanımlar. Compiland içinde tanımlanmadığı müddetçe yerel türe erişmek için bir hata olduğuna dikkat edin.

```cpp
// use_native_type_in_clr_2.cpp
// compile with: /clr
#using "use_native_type_in_clr.dll"
// Uncomment the following 3 lines to resolve.
// public struct NativeClass {
//    static int Test() { return 98; }
// };

int main() {
   ManagedClass x;
   x.Test();

   System::Console::WriteLine(NativeClass::Test());   // C2653
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ birlikte çalışabilirliği kullanma (örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
