---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: db79e228f1fabc4b2da0a7778126a1b576a67768
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229044"
---
# <a name="const-c"></a>const (C++)

Bir veri bildirimini değiştirirken **`const`** anahtar sözcüğü nesne veya değişkenin değiştirilebilir olmadığı belirtir.

## <a name="syntax"></a>Sözdizimi

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>const değerleri

**`const`** Anahtar sözcüğü bir değişkenin değerinin sabit olduğunu belirtir ve derleyiciye programcının değiştirmesini engellemesini söyler.

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

C++ ' da, **`const`** sabit değerleri tanımlamak için [#define](../preprocessor/hash-define-directive-c-cpp.md) Önişlemci yönergesi yerine anahtar sözcüğünü kullanabilirsiniz. İle tanımlanan değerler **`const`** tür denetimine tabidir ve sabit ifadelerin yerine kullanılabilir. C++ ' da, bir dizinin boyutunu **`const`** Şu şekilde belirtebilirsiniz:

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

C 'de, sabit değerler varsayılan olarak dış bağlantı olarak, yalnızca kaynak dosyalarında görünebilirler. C++ ' da, sabit değerler varsayılan olarak iç bağlantıya sahiptir ve bu da bunların başlık dosyalarında görünmesine izin verir.

**`const`** Anahtar sözcüğü işaretçi bildirimlerinde de kullanılabilir.

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

Olarak belirtilen bir değişken işaretçisi, **`const`** yalnızca olarak da belirtilen bir işaretçiye atanabilir **`const`** .

```cpp
// constant_values4.cpp
#include <stdio.h>
int main() {
   const char *mybuf = "test";
   char *yourbuf = "test2";
   printf_s("%s\n", mybuf);

   const char *bptr = mybuf;   // Pointer to constant data
   printf_s("%s\n", bptr);

   // *bptr = 'a';   // Error
}
```

İşlevin işaretçiden geçirilen bir parametreyi değiştirmesini engellemek için işlev parametreleri olarak sabit verilere yönelik işaretçiler kullanabilirsiniz.

Olarak bildirildiği nesneler için **`const`** yalnızca sabit üye işlevlerini çağırabilirsiniz. Bu, sabit nesnenin hiçbir şekilde değiştirilmemesini sağlar.

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

Sabit olmayan bir nesne için sabit ya da sabit olmayan üye işlevleri çağırabilirsiniz. Anahtar sözcüğünü kullanarak bir üye işlevini de aşırı yükleyebilirsiniz **`const`** ; Bu, işlevin farklı bir sürümünün sabit ve sabit olmayan nesneler için çağrılmasına izin verir.

Anahtar sözcüğü ile oluşturucular veya Yıkıcılar bildiremezsiniz **`const`** .

## <a name="const-member-functions"></a>const üye işlevleri

Anahtar sözcükle bir üye işlevi bildirmek **`const`** , işlevin çağrıldığı nesneyi değiştirmeyerek "salt okunurdur" bir işlev olduğunu belirtir. Sabit bir üye işlevi, statik olmayan veri üyelerini değiştiremez veya sabit olmayan herhangi bir üye işlevi çağırabilir. Sabit bir üye işlevi bildirmek için, **`const`** anahtar sözcüğünü bağımsız değişken listesinin kapatma parantezinden sonra koyun. **`const`** Anahtar sözcüğü hem bildirimde hem de tanımda gereklidir.

```cpp
// constant_member_function.cpp
class Date
{
public:
   Date( int mn, int dy, int yr );
   int getMonth() const;     // A read-only function
   void setMonth( int mn );   // A write function; can't be const
private:
   int month;
};

int Date::getMonth() const
{
   return month;        // Doesn't modify anything
}
void Date::setMonth( int mn )
{
   month = mn;          // Modifies data member
}
int main()
{
   Date MyDate( 7, 4, 1998 );
   const Date BirthDate( 1, 18, 1953 );
   MyDate.setMonth( 4 );    // Okay
   BirthDate.getMonth();    // Okay
   BirthDate.setMonth( 4 ); // C2662 Error
}
```

## <a name="c-and-c-const-differences"></a>C ve C++ const farkları

Bir değişkeni **`const`** C kaynak kodu dosyasında bildirdiğinizde, bunu şöyle yapabilirsiniz:

```cpp
const int i = 2;
```

Daha sonra bu değişkeni başka bir modülde aşağıdaki şekilde kullanabilirsiniz:

```cpp
extern const int i;
```

Ancak C++ ' da aynı davranışı almak için **`const`** değişkeninizi şöyle bildirmeniz gerekir:

```cpp
extern const int i = 2;
```

**`extern`** C kaynak kodu dosyasında kullanmak üzere bir C++ kaynak kodu dosyasında bir değişken bildirmek istiyorsanız şunu kullanın:

```cpp
extern "C" const int x=10;
```

C++ derleyicisi tarafından değiştirmeyi adını engellemek için.

## <a name="remarks"></a>Açıklamalar

Bir üye işlevin parametre listesini takip ettiğinizde, **`const`** anahtar sözcüğü işlevin çağrıldığı nesneyi değiştirmediği belirtir.

Hakkında daha fazla bilgi için **`const`** aşağıdaki konulara bakın:

- [const ve volatile Işaretçileri](../cpp/const-and-volatile-pointers.md)

- [Tür niteleyicileri (C dil başvurusu)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)
