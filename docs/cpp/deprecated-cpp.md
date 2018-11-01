---
title: deprecated (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: 34f9c10cd898b0359463d5933141822576fa4a11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485859"
---
# <a name="deprecated-c"></a>deprecated (C++)

Bu konu hakkında Microsoft'a özgü olan declspec bildirimi kullanım dışı. C ++ 14 hakkında bilgi için `[[deprecated]]` özniteliği ve ne zaman ve Microsoft'a özgü declspec veya pragması, bu öznitelik kullanılacağı hakkında yönergeler [C++ Standart öznitelikleri](attributes.md).

Aşağıda belirtilen durumlarla **kullanım dışı** bildirimi aynı işlevleri sunar [kullanım dışı](../preprocessor/deprecated-c-cpp.md) pragma:

- **Kullanım dışı** bildirimi belirtmenize olanak tanır işlev aşırı yüklemelerinin belirli tür olarak kullanım dışı pragma formun tüm aşırı yüklenmiş bir işlev adı formları için geçerlidir ancak.

- **Kullanım dışı** bildirimi derleme zamanında görüntülenecek bir ileti belirtmenize olanak sağlar. İleti metnini makrodan olabilir.

- Makrolar, yalnızca ile kullanım dışı olarak işaretlenebilir **kullanım dışı** pragması.

Derleyici, kullanım dışı bir tanıtıcı veya standart kullanımını karşılaştığında, [ `[[deprecated]]` ](attributes.md) öznitelik, bir [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) uyarısı oluşturulur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, kullanım dışı işlev kullanıldığında derleme zamanında görüntülenecek bir ileti belirtme ve İşlevler kullanım dışı bırakıldı olarak işaretlemek nasıl gösterir.

```cpp
// deprecated.cpp
// compile with: /W3
#define MY_TEXT "function is deprecated"
void func1(void) {}
__declspec(deprecated) void func1(int) {}
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}
__declspec(deprecated(MY_TEXT)) void func3(int) {}

int main() {
   func1();
   func1(1);   // C4996
   func2(1);   // C4996
   func3(1);   // C4996
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, kullanım dışı sınıfı kullanıldığında derleme zamanında görüntülenecek bir ileti belirtme ve sınıfları kullanım dışı bırakıldı olarak işaretlemek nasıl gösterir.

```cpp
// deprecate_class.cpp
// compile with: /W3
struct __declspec(deprecated) X {
   void f(){}
};

struct __declspec(deprecated("** X2 is deprecated **")) X2 {
   void f(){}
};

int main() {
   X x;   // C4996
   X2 x2;   // C4996
}
```

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)