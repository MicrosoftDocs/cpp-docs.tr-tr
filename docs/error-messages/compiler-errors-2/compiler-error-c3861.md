---
title: Derleyici Hatası C3861 | Microsoft Docs
ms.custom: ''
ms.date: 03/23/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3861
dev_langs:
- C++
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dbfbb11184928331b94b7addc747ffb7e44d6d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270270"
---
# <a name="compiler-error-c3861"></a>Derleyici Hatası C3861

> '*tanımlayıcısı*': tanımlayıcısı bulunamadı

Derleyici bile bağımsız değişkene bağlı arama özelliğini kullanarak bir tanımlayıcı başvuru çözümleyebilmesi değildi.

## <a name="remarks"></a>Açıklamalar

Bu hatayı düzeltmek için kullanımını karşılaştırın *tanımlayıcısı* çalışması ve yazım tanımlayıcı bildirimi için. Doğrulayın [kapsamını çözümleme işleçleri](../../cpp/scope-resolution-operator.md) ve ad alanı [yönergeleri kullanarak](../../cpp/namespaces-cpp.md#using_directives) doğru bir şekilde kullanılır. Tanımlayıcı bir üstbilgi dosyasında bildirilirse tanımlayıcı başvurulan önce üstbilgi dahil olduğundan emin olun. Harici olarak görünür olmasını tanımlayıcı istediyseniz kullandığı herhangi bir kaynak dosyada bildirildiğinden emin olun. Ayrıca tanımlayıcı bildiriminde ya da tanımı tarafından hariç olduğunu kontrol [koşullu derleme yönergeleri](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

C çalışma zamanı kitaplığı Visual Studio 2015'te eski işlevleri kaldırmak için değişiklikler C3861 neden olabilir. Bu hatayı gidermek için bu işlevler başvuruları kaldırın veya bunları varsa bunların güvenli alternatifler ile değiştirin. Daha fazla bilgi için bkz: [eski işlevleri](../../c-runtime-library/obsolete-functions.md).

Hata C3861 derleyici eski sürümlerinden proje geçişten sonra görünürse, desteklenen Windows sürümlerine ilgili sorunlar olabilir. Visual C++ artık hedefleme Windows 95, Windows 98, Windows ME, Windows NT veya Windows 2000 destekler. Varsa, **WINVER** veya **_WIN32_WINNT** makroları Windows'un bu sürümlerinde birine atanır, makroları değiştirmeniz gerekir. Daha fazla bilgi için bkz: [değiştirme WINVER ve _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md).

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

### <a name="identifier-not-in-scope"></a>Tanımlayıcı kapsam içinde değil

Aşağıdaki örnek, bir tanımlayıcı yalnızca kullanan diğer kaynak dosyalarında bildirilir sürece, tanım dosyası kapsamında görünür olduğundan C3861 oluşturur.

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

### <a name="namespace-qualification-required"></a>Namespace niteliğe gerekli

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

Artık kullanılmayan işlevler CRT Kitaplığı'ndan kaldırıldı.

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

Aşağıdaki örnek derleyici bağımsız değişkeni bağımlı aramasını kullanamadığından C3767 oluşturur `FriendFunc`:

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

Hatayı düzeltmek için sınıf kapsamı içindeki arkadaş bildirme ve ad alanı kapsamında tanımlayın:

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
