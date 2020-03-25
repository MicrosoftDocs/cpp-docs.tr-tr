---
title: nullptr (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
ms.openlocfilehash: 02da716959deb7fcffa7a63a8308279a765c4569
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172120"
---
# <a name="nullptr--ccli-and-ccx"></a>nullptr (C++/CLI ve C++/CX)

**Nullptr** anahtar sözcüğü bir *null işaretçi değeri*temsil eder. Bir nesne tanıtıcısı, iç işaretçi veya yerel işaretçi türünün bir nesneyi işaret etmez olduğunu göstermek için null işaretçi değeri kullanın.

Yönetilen ya da yerel kodla **nullptr** kullanın. Derleyici, yönetilen ve yerel null işaretçi değerleri için uygun ancak farklı yönergeler yayar. Bu anahtar sözcüğünün ISO standart C++ sürümünü kullanma hakkında daha fazla bilgi için bkz. [nullptr](../cpp/nullptr.md).

**__Nullptr** anahtar sözcüğü, **nullptr**ile aynı anlamı olan, ancak yalnızca yerel koda uygulanan Microsoft 'a özgü bir anahtar sözcüktür. Yerel C/ **nullptr** C++ Code ile nullptr kullanarak ve sonra [/clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ile derlerseniz, derleyici **nullptr** 'nin yerel veya yönetilen bir null işaretçi değeri içerip içermediğini belirleyemez. Derleyicisini derleyiciye eklemek için, bir yönetilen değer belirtmek için **nullptr** kullanın veya yerel bir değer belirtmek için **__nullptr** .

**Nullptr** anahtar sözcüğü Visual Basic ' de **Nothing** ve içinde C# **null** değeri ile eşdeğerdir.

## <a name="usage"></a>Kullanım

**Nullptr** anahtar sözcüğü, bir tutamaç, yerel işaretçi veya işlev bağımsız değişkeninin kullanılabileceği her yerde kullanılabilir.

**Nullptr** anahtar sözcüğü bir tür değil ve ile kullanım için desteklenmiyor:

- [sizeof](../cpp/sizeof-operator.md)

- [typeid](../cpp/typeid-operator.md)

- `throw nullptr` (`throw (Object^)nullptr;` çalışacaktır ancak)

**Nullptr** anahtar sözcüğü aşağıdaki işaretçi türlerinin başlatılmasında kullanılabilir:

- Yerel işaretçi

- Windows Çalışma Zamanı tanıtıcısı

- Yönetilen tanıtıcı

- Yönetilen iç işaretçi

Başvuru kullanılmadan önce bir işaretçi veya tanıtıcı başvurusunun null olup olmadığını test etmek için **nullptr** anahtar sözcüğü kullanılabilir.

Hata denetimi için null işaretçi değerlerini kullanan diller arasındaki işlev çağrıları doğru şekilde yorumlanmalıdır.

Bir tanıtıcıyı sıfıra başlatamıyor; yalnızca **nullptr** kullanılabilir. Bir nesne tanıtıcısına 0 sabiti ataması, kutulanmış `Int32` ve `Object^`bir tür üretir.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir tanıtıcı, yerel işaretçi veya işlev bağımsız değişkeninin kullanılabileceği her yerde **nullptr** anahtar sözcüğünün kullanılabileceğini gösterir. Örnek, bir başvuruyu kullanılmadan önce denetlemek için **nullptr** anahtar sözcüğünün kullanılabileceğini gösterir.

```cpp
// mcpp_nullptr.cpp
// compile with: /clr
value class V {};
ref class G {};
void f(System::Object ^) {}

int main() {
// Native pointer.
   int *pN = nullptr;
// Managed handle.
   G ^pG = nullptr;
   V ^pV1 = nullptr;
// Managed interior pointer.
   interior_ptr<V> pV2 = nullptr;
// Reference checking before using a pointer.
   if (pN == nullptr) {}
   if (pG == nullptr) {}
   if (pV1 == nullptr) {}
   if (pV2 == nullptr) {}
// nullptr can be used as a function argument.
   f(nullptr);   // calls f(System::Object ^)
}
```

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, **nullptr** ve sıfır 'nin yerel işaretçilerde birbirinin yerine kullanılabileceğini gösterir.

```cpp
// mcpp_nullptr_1.cpp
// compile with: /clr
class MyClass {
public:
   int i;
};

int main() {
   MyClass * pMyClass = nullptr;
   if ( pMyClass == nullptr)
      System::Console::WriteLine("pMyClass == nullptr");

   if ( pMyClass == 0)
      System::Console::WriteLine("pMyClass == 0");

   pMyClass = 0;
   if ( pMyClass == nullptr)
      System::Console::WriteLine("pMyClass == nullptr");

   if ( pMyClass == 0)
      System::Console::WriteLine("pMyClass == 0");
}
```

```Output
pMyClass == nullptr

pMyClass == 0

pMyClass == nullptr

pMyClass == 0
```

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, **nullptr** türünün herhangi bir tür için bir tanıtıcı veya herhangi bir yerel işaretçi olarak yorumlandığını gösterir. Farklı türlere yönelik tanıtıcılarla işlev aşırı yüklemesi söz konusu olduğunda bir belirsizlik hatası oluşturulur. **Nullptr** 'nin açıkça bir türe dönüştürülmesi gerekir.

```cpp
// mcpp_nullptr_2.cpp
// compile with: /clr /LD
void f(int *){}
void f(int ^){}

void f_null() {
   f(nullptr);   // C2668
   // try one of the following lines instead
   f((int *) nullptr);
   f((int ^) nullptr);
}
```

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, tür, **nullptr** öğesine izin verildiğini gösterir ve bu tür bir işaretçi veya tanıtıcıyı, **nullptr** değerini içeren atama türüne döndürür.

```cpp
// mcpp_nullptr_3.cpp
// compile with: /clr /LD
using namespace System;
template <typename T>
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type

int main() {
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)

   // Delete the following line to resolve.
   f(nullptr);

   f(0);   // T = int, call f(int)
}
```

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, **nullptr** 'nin bir işlev parametresi olarak kullanılabileceğini gösterir.

```cpp
// mcpp_nullptr_4.cpp
// compile with: /clr
using namespace System;
void f(Object ^ x) {
   Console::WriteLine("test");
}

int main() {
   f(nullptr);
}
```

```Output
test
```

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, tanıtıcıların bildirildiği ve açık olarak başlamadığı durumlarda, varsayılan olarak **nullptr**'nin varsayılan olarak başlatıldığını gösterir.

```cpp
// mcpp_nullptr_5.cpp
// compile with: /clr
using namespace System;
ref class MyClass {
public:
   void Test() {
      MyClass ^pMyClass;   // gc type
      if (pMyClass == nullptr)
         Console::WriteLine("NULL");
   }
};

int main() {
   MyClass ^ x = gcnew MyClass();
   x -> Test();
}
```

```Output
NULL
```

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, `/clr`ile derlerken, yerel işaretçiye **nullptr** 'nin atanabileceği gösterilmektedir.

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: (gerekli değildir; `/ZW` ve `/clr`dahil olmak üzere tüm kod oluşturma seçenekleri tarafından desteklenir)

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)
