---
title: nullptr (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
ms.openlocfilehash: 05aaaa8a0d0056e0f5318f5e9329d90824760728
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040828"
---
# <a name="nullptr--ccli-and-ccx"></a>nullptr (C + +/ CLI ve C + +/ CX)

**Nullptr** anahtar sözcüğü temsil eden bir *null işaretçi değeri*. Bir null işaretçi değeri bir nesne tanıtıcısı, iç işaretçi veya yerel bir işaretçi türü bir nesneye göstermiyor belirtmek için kullanın.

Kullanım **nullptr** yönetilen veya yerel kod ile. Yönetilen ve yerel bir null işaretçi değerleri için uygun ancak farklı yönergeleri derleyici gösterir. Bu anahtar sözcük ISO standard C++ sürümü kullanma hakkında daha fazla bilgi için bkz: [nullptr](../cpp/nullptr.md).

**__Nullptr** anahtar sözcüğü, aynı anlama sahiptir Microsoft'a özgü anahtar sözcük **nullptr**, ancak yalnızca yerel kod için geçerlidir. Kullanırsanız **nullptr** ile yerel C/C++ kod ve ardından derleme [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği, derleyicinin belirleyemiyor olmadığını **nullptr** yerel gösterir veya boş işaretçi değerini yönetilen. Amacınız derleyicinin Temizle yapmak için **nullptr** yönetilen bir değeri belirtmek için veya **__nullptr** yerel bir değer belirtebilirsiniz.

**Nullptr** anahtar sözcüğü, eşdeğer **hiçbir şey** Visual Basic'te ve **null** C#.

## <a name="usage"></a>Kullanım

**Nullptr** anahtar sözcüğü bir tanıtıcı, yerel işaretçisi veya işlev bağımsız değişkeni kullanılabilir her yerde kullanılabilir.

**Nullptr** anahtar sözcüğü bir tür değil ve ile kullanım için desteklenmez:

- [sizeof](../cpp/sizeof-operator.md)

- [typeid](../cpp/typeid-operator.md)

- `throw nullptr` (ancak `throw (Object^)nullptr;` çalışır)

**Nullptr** anahtar sözcüğü aşağıdaki işaretçi türleri başlatma içinde kullanılabilir:

- Yerel işaretçi

- Windows çalışma zamanı tanıtıcısı

- Yönetilen işleyici

- İç işaretçi yönetilen

**Nullptr** anahtar sözcüğü, başvuru kullanılmadan önce bir işaretçi veya işleç başvuru null ise, test etmek için kullanılabilir.

İşlev çağrıları hata denetimi için null işaretçi değerleri kullanan diller arasında doğru yorumlanması gerektiğini.

Sıfırdan bir tanıtıcı başlatılamıyor; yalnızca **nullptr** kullanılabilir. Bir nesne tanıtıcısına sabit 0 atama üretir bir kutu `Int32` ve bir atamanın `Object^`.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği gösteren **nullptr** anahtar sözcüğü bir tanıtıcı her yerde kullanılabilir, yerel işaretçisi veya işlev bağımsız değişkeni kullanılabilir. Bu örnek, gösterir **nullptr** anahtar sözcüğü, kullanılmadan önce bir başvuru denetlemek için kullanılabilir.

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

Aşağıdaki kod örneği gösteren **nullptr** ve sıfır kullanılabilir birbirinin yerine yerel işaretçilerde.

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

Aşağıdaki kod örneği gösteren **nullptr** herhangi bir tür için bir tanıtıcı veya herhangi bir tür için yerel bir işaretçi olarak yorumlanır. İşlev farklı türlere sahip olması durumunda aşırı yüklemesi, bir belirsizlik hata oluşturulur. **Nullptr** açıkça bir türe yayınlanması gerekir.

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

Aşağıdaki kod örneği, atama gösterir **nullptr** izin verilir ve bir işaretçi veya işleç içeren bir atama türü döndürür **nullptr** değeri.

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

Aşağıdaki kod örneği gösteren **nullptr** işlevi parametre olarak kullanılabilir.

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

Aşağıdaki kod örneği tanıtıcıları bildirildi ve açıkça başlatılır, bunlar için varsayılan olduğunu gösteren **nullptr**.

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

Aşağıdaki kod örneği gösteren **nullptr** ile derleme yaparken yerel bir işaretçiye atanabilir `/clr`.

```cpp
// mcpp_nullptr_6.cpp
// compile with: /clr
int main() {
   int * i = 0;
   int * j = nullptr;
}
```

## <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: (Gerekli; dahil olmak üzere tüm kod oluşturma seçenekleri tarafından desteklenen `/ZW` ve `/clr`)

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)<br/>
[nullptr](../cpp/nullptr.md)