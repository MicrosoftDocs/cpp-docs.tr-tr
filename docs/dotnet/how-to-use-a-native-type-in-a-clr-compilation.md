---
title: 'Nasıl yapılır: -Clr derlemesinde yerel tür kullanma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
ms.openlocfilehash: 9979113ac4ffc062ddfe8654279af03036984f38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387207"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>Nasıl yapılır: Bir/CLR derlemesinde yerel tür kullanma

Yerel bir tür tanımlayabilirsiniz bir **/CLR** derleme ve bu yerel türün derleme içindeki herhangi bir kullanımından geçerlidir. Ancak, yerel türler başvurulan meta veriler için kullanılamaz.

Her derleme, bu her yerel bir tür tanımı içermelidir.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Tanımlar ve yerel bir tür kullanan bir bileşenin bu örneği oluşturur.

```
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

## <a name="example"></a>Örnek

Bu örnek bileşeni kullanan bir istemci tanımlar. Derlenecek dosyada tanımlı olmadığı sürece, yerel tür erişmek için bir hata olduğuna dikkat edin.

```
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

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
