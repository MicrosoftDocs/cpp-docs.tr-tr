---
title: 'Nasıl yapılır: - clr derlemesinde yerel tür kullanma'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
ms.openlocfilehash: 0079be21b474858684e1abaaeb363820764a701d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459963"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>Nasıl yapılır: /clr Derlemesinde Yerel Tür Kullanma

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

## <a name="see-also"></a>Ayrıca Bkz.

[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)