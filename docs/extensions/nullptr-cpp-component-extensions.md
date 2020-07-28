---
title: nullptr (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
ms.openlocfilehash: 5e7a5d3f9a42968dee35f82d3f19d0fdb6da5d0c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214236"
---
# <a name="nullptr--ccli-and-ccx"></a>nullptr (C++/CLI ve C++/CX)

**`nullptr`** Anahtar sözcüğü bir *null işaretçi değeri*temsil eder. Bir nesne tanıtıcısı, iç işaretçi veya yerel işaretçi türünün bir nesneyi işaret etmez olduğunu göstermek için null işaretçi değeri kullanın.

**`nullptr`** Yönetilen ya da yerel kodla kullanın. Derleyici, yönetilen ve yerel null işaretçi değerleri için uygun ancak farklı yönergeler yayar. Bu anahtar sözcüğünün ISO standardı C++ sürümünü kullanma hakkında daha fazla bilgi için bkz. [nullptr](../cpp/nullptr.md).

**__Nullptr** anahtar sözcüğü, ile aynı anlamı olan **`nullptr`** , ancak yalnızca yerel koda uygulanan, Microsoft 'a özgü bir anahtar sözcüktür. **`nullptr`** Yerel C/C++ kodu ile kullanırsanız ve [/clr](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği ile derlerseniz, derleyici **`nullptr`** yerel veya yönetilen bir null işaretçi değeri olup olmadığını belirleyemez. Derleyicisini derleyiciye eklemek için, **`nullptr`** yönetilen bir değer belirtmek için veya yerel bir değer belirtmek için **__nullptr** kullanın.

**`nullptr`** Anahtar sözcüğü, Visual Basic ve C# ' de **null** değeri **yok** ile eşdeğerdir.

## <a name="usage"></a>Kullanım

**`nullptr`** Anahtar sözcüğü, bir tutamaç, yerel işaretçi veya işlev bağımsız değişkeninin kullanılabileceği her yerde kullanılabilir.

**`nullptr`** Anahtar sözcüğü bir tür değildir ve ile kullanım için desteklenmez:

- [sizeof](../cpp/sizeof-operator.md)

- [typeid](../cpp/typeid-operator.md)

- `throw nullptr`(ancak `throw (Object^)nullptr;` çalışacaktır)

**`nullptr`** Anahtar sözcüğü, aşağıdaki işaretçi türlerinin başlatılmasında kullanılabilir:

- Yerel işaretçi

- Windows Çalışma Zamanı tanıtıcısı

- Yönetilen tanıtıcı

- Yönetilen iç işaretçi

**`nullptr`** Anahtar sözcüğü, bir işaretçi veya tanıtıcı başvurusunun, başvurunun kullanılmadan önce null olup olmadığını test etmek için kullanılabilir.

Hata denetimi için null işaretçi değerlerini kullanan diller arasındaki işlev çağrıları doğru şekilde yorumlanmalıdır.

Bir tanıtıcıyı sıfıra başlatamıyor; yalnızca **`nullptr`** kullanılabilir. Bir nesne tanıtıcısına 0 sabiti atanması kutulanmış `Int32` ve ' a bir tür üretir `Object^` .

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, **`nullptr`** anahtar sözcüğünün bir tanıtıcı, yerel işaretçi veya işlev bağımsız değişkeninin kullanılabileceği her yerde kullanılabileceğini gösterir. Örnek, **`nullptr`** anahtar sözcüğünün, bir başvuruyu kullanılmadan önce denetlemek için kullanılabileceğini gösterir.

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

Aşağıdaki kod örneği, **`nullptr`** Yerel işaretçilerde birbirinin yerine, ve sıfır kullanılabileceğini gösterir.

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

Aşağıdaki kod örneği, herhangi bir türe **`nullptr`** veya herhangi bir türe yerel işaretçiye yönelik bir tanıtıcı olarak yorumlanan gösterilmektedir. Farklı türlere yönelik tanıtıcılarla işlev aşırı yüklemesi söz konusu olduğunda bir belirsizlik hatası oluşturulur. ' In **`nullptr`** açıkça bir türe dönüştürülmesi gerekir.

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

Aşağıdaki kod örneği, atama **`nullptr`** için izin verildiğini gösterir ve değeri içeren atama türüne bir işaretçi veya tanıtıcı döndürür **`nullptr`** .

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

Aşağıdaki kod örneği, **`nullptr`** bir işlev parametresi olarak kullanılabilecek gösterir.

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

Aşağıdaki kod örneği, tanıtıcıların bildirildiği ve açıkça başlatıldığı zaman, varsayılan olarak başlatıldığını gösterir **`nullptr`** .

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

Aşağıdaki kod örneği, **`nullptr`** ile derleme yaptığınızda yerel bir işaretçiye atanabileceği gösterilmektedir `/clr` .

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: (gerekli değil; tüm kod oluşturma seçenekleri tarafından desteklenir, `/ZW` ve dahil `/clr` )

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)
