---
title: Derleyici Hatası C3861
ms.date: 03/23/2018
f1_keywords:
- C3861
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
ms.openlocfilehash: 4ebfd3b0129e25cf543cac803a3b33fb074f3d70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50530812"
---
# <a name="compiler-error-c3861"></a>Derleyici Hatası C3861

> '*tanımlayıcı*': tanımlayıcı bulunamadı

Derleyici bile bağımsız değişkene bağlı arama kullanılarak bir tanımlayıcı, bir başvuru çözmeniz mümkün değildi.

## <a name="remarks"></a>Açıklamalar

Bu hatayı düzeltmek için kullanımını karşılaştırma *tanımlayıcı* çalışması ve yazım denetimi için tanımlayıcı bildirim için. Doğrulayın [kapsam çözümleme işleçleri](../../cpp/scope-resolution-operator.md) ve ad alanı [yönergeleri kullanarak](../../cpp/namespaces-cpp.md#using_directives) doğru şekilde kullanılır. Tanımlayıcı bir üstbilgi dosyasında bildirirse, tanımlayıcı başvurulan önce üst bilgisi dahil olduğundan emin olun. Tanımlayıcı dışarıdan görünür olmasını geliyorsa, bunu kullanan herhangi bir kaynak dosyada bildirilir emin olun. Ayrıca tanımlayıcı bildirim veya tanımdan tarafından tutulduğunu değil denetleyin [koşullu derleme yönergeleri](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

C çalışma zamanı kitaplığı Visual Studio 2015'te eski işlevleri kaldırmak için değişiklikleri C3861 neden olabilir. Bu hatayı gidermek için bu işlevlere başvuruları kaldırın veya bunları varsa bunların güvenli alternatifler ile değiştirin. Daha fazla bilgi için [artık kullanılmayan işlevleri](../../c-runtime-library/obsolete-functions.md).

Hatası C3861 derleyici eski sürümlerinden proje geçişten sonra görünüyorsa, desteklenen Windows sürümleri için ilgili sorunlar olabilir. Visual C++ artık hedefleme Windows 95, Windows 98, Windows ME, Windows NT veya Windows 2000 destekler. Varsa, **WINVER** veya **_WIN32_WINNT** makroları Windows'ın bu sürümlerinin birine atanır, makroları değiştirmeniz gerekir. Daha fazla bilgi için [değiştirme WINVER ve _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md).

## <a name="examples"></a>Örnekler

### <a name="undefined-identifier"></a>Tanımlanmamış tanımlayıcı

Aşağıdaki örnek, tanımlayıcı tanımlanmadığından C3861 oluşturur.

```cpp
// C3861.cpp
void f2(){}
int main() {
   f();    // C3861
   f2();   // OK
}
```

### <a name="identifier-not-in-scope"></a>Tanımlayıcısı kapsamda değil

Aşağıdaki örnek, bir tanımlayıcı yalnızca kullanan başka kaynak dosyalarında bildirildiği sürece, tanımı dosya kapsamında görünür olduğundan C3861 oluşturur.

```cpp
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {
   std::cout << f() << std::endl;    // C3861
}
```

```cpp
// C3861_a2.cpp
int f() {  // declared and defined here
   return 42;
}
```

### <a name="namespace-qualification-required"></a>Namespace nitelik gerekli

C++ Standart Kitaplığı'nda özel durum sınıfları gerektiren `std` ad alanı.

```cpp
// C3861_b.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   try {
      throw exception("Exception");   // C3861
      // try the following line instead
      // throw std::exception("Exception");
   }
   catch (...) {
      std::cout << "caught an exception" << std::endl;
   }
}
```

### <a name="obsolete-function-called"></a>Adlı eski işlevi

Artık kullanılmayan işlevleri CRT Kitaplığı'ndan kaldırıldı.

```cpp
// C3861_c.cpp
#include <stdio.h>
int main() {
   char line[21]; // room for 20 chars + '\0'
   gets( line );  // C3861
   // Use gets_s instead.
   printf( "The line entered was: %s\n", line );
}
```

### <a name="adl-and-friend-functions"></a>ADL ve arkadaş işlevleri

Aşağıdaki örnek, C3767 oluşturur, derleyici bağımsız değişken bağımlı arama için kullanamazsınız çünkü `FriendFunc`:

```cpp
namespace N {
   class C {
      friend void FriendFunc() {}
      friend void AnotherFriendFunc(C* c) {}
   };
}

int main() {
   using namespace N;
   FriendFunc();   // C3861 error
   C* pC = new C();
   AnotherFriendFunc(pC);   // found via argument-dependent lookup
}
```

Hatayı düzeltmek için arkadaş sınıf kapsamı içinde bildirme ve ad alanı kapsamında tanımlayın:

```cpp
class MyClass {
   int m_private;
   friend void func();
};

void func() {
   MyClass s;
   s.m_private = 0;
}

int main() {
   func();
}
```
