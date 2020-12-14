---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3861'
title: Derleyici hatası C3861
ms.date: 03/23/2018
f1_keywords:
- C3861
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
ms.openlocfilehash: bba259496de09e86b59f9cad1ac1bf89a697a1da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222911"
---
# <a name="compiler-error-c3861"></a>Derleyici hatası C3861

> '*tanımlayıcı*': tanımlayıcı bulunamadı

Derleyici, bağımsız değişkene bağlı arama kullanarak bile bir tanımlayıcıya başvuruyu çözümleyemedi.

## <a name="remarks"></a>Açıklamalar

Bu hatayı onarmak için *tanımlayıcı* kullanımını, büyük/küçük harf ve yazım için tanımlayıcı bildirimine karşılaştırın. [Kapsam çözümleme işleçleri](../../cpp/scope-resolution-operator.md) ve [yönergeleri kullanarak](../../cpp/namespaces-cpp.md#using_directives) ad alanı için doğru kullanıldığını doğrulayın. Tanımlayıcı bir başlık dosyasında bildirilirse, tanımlayıcıya başvurulmadan önce üstbilginin dahil edildiğini doğrulayın. Tanımlayıcının dışarıdan görünür olması amaçlıbulunursa, onu kullanan herhangi bir kaynak dosyasında bildirildiği için emin olun. Ayrıca, tanımlayıcı bildiriminin veya tanımın [koşullu derleme yönergeleri](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)tarafından dışlanmadığından emin olun.

Visual Studio 2015 ' deki C çalışma zamanı kitaplığından kullanılmayan işlevleri kaldırma değişiklikleri C3861 neden olabilir. Bu hatayı çözmek için, bu işlevlere başvuruları kaldırın veya varsa bunları güvenli alternatiflerle değiştirin. Daha fazla bilgi için bkz. [eski işlevler](../../c-runtime-library/obsolete-functions.md).

Derleyicinin eski sürümlerinden proje geçişten sonra hata C3861 görüntülenirse, desteklenen Windows sürümleriyle ilgili sorunlarla karşılaşabilirsiniz. Visual C++ artık Windows 95, Windows 98, Windows ME, Windows NT veya Windows 2000 'in hedeflenmesini desteklemiyor. Bu Windows sürümlerinden birine yönelik **WINVER** veya **_WIN32_WINNT** makrolarınız atanırsa, makroları değiştirmelisiniz. Daha fazla bilgi için bkz. [WINVER ve _WIN32_WINNT değiştirme](../../porting/modifying-winver-and-win32-winnt.md).

## <a name="examples"></a>Örnekler

### <a name="undefined-identifier"></a>Tanımlanmamış tanımlayıcı

Aşağıdaki örnek, tanımlayıcı tanımlanmadığı için C3861 oluşturur.

```cpp
// C3861.cpp
void f2(){}
int main() {
   f();    // C3861
   f2();   // OK
}
```

### <a name="identifier-not-in-scope"></a>Tanımlayıcı kapsamda değil

Aşağıdaki örnek, bir tanımlayıcı yalnızca tanımının dosya kapsamında görünmediği, onu kullanan diğer kaynak dosyalarında bildirildiği müddetçe, C3861 oluşturur.

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

### <a name="namespace-qualification-required"></a>Ad alanı nitelendirme gerekli

C++ standart kitaplığı 'ndaki özel durum sınıfları `std` ad alanını gerektirir.

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

### <a name="obsolete-function-called"></a>Kullanımdan kaldırılmış işlev çağrıldı

Kullanılmayan işlevler CRT kitaplığından kaldırılmıştır.

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

Aşağıdaki örnek C3767 oluşturur, çünkü derleyici bağımsız değişkene bağımlı arama kullanamaz `FriendFunc` :

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

Hatayı düzeltemedi, arkadaşınızı sınıf kapsamında bildirin ve ad alanı kapsamında tanımlayın:

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
