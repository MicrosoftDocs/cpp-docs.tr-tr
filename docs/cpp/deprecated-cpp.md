---
title: deprecated (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: 44cb33bae43b32b12dda95423aec5484f61aa596
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90683422"
---
# <a name="deprecated-c"></a>deprecated (C++)

Bu konu, Microsoft 'a özgü kullanım dışı declspec bildirimi ile ilgilidir. C++ 14 özniteliği hakkında daha fazla bilgi edinmek `[[deprecated]]` ve bu özniteliğin Microsoft 'a özgü declspec veya pragma ile ne zaman kullanılacağı üzerine kılavuzluk, bkz. [C++ standart öznitelikleri](attributes.md).

Aşağıda belirtilen özel durumlarla birlikte, **`deprecated`** bildirim [kullanım dışı](../preprocessor/deprecated-c-cpp.md) pragma ile aynı işlevselliği sunar:

- Bildirim, işlev **`deprecated`** aşırı yüklemelerinin belirli biçimlerini kullanım dışı olarak belirtmenizi sağlar, ancak pragma formu bir işlev adının tüm aşırı yüklenmiş formlarına uygulanır.

- **`deprecated`** Bildirim, derleme zamanında görüntülenecek bir ileti belirtmenize olanak tanır. İletinin metni bir makrodan olabilir.

- Makrolar yalnızca pragma ile kullanım dışı olarak işaretlenebilir **`deprecated`** .

Derleyici kullanım dışı bir tanımlayıcının veya standart özniteliğin kullanımıyla karşılaşırsa [`[[deprecated]]`](attributes.md) , bir [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) uyarısı oluşturulur.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, işlevlerin kullanım dışı olarak işaretlenme ve kullanım dışı işlevin kullanıldığı zaman derleme zamanında görüntülenecek bir iletinin nasıl belirtilmeyeceği gösterilmektedir.

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

Aşağıdaki örnekte, sınıfların kullanım dışı olarak işaretlenme ve kullanım dışı bırakılan sınıf kullanıldığında derleme zamanında görüntülenecek bir iletinin nasıl belirtilmeyeceği gösterilmektedir.

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)
