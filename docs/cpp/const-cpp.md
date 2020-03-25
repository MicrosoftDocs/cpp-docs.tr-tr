---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: cc1f117cc5f26edf9cd85461281b925c97fa5225
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180310"
---
# <a name="const-c"></a>const (C++)

Bir veri bildirimini değiştirirken **const** anahtar sözcüğü nesnenin veya değişkenin değiştirilemeyecek olduğunu belirtir.

## <a name="syntax"></a>Sözdizimi

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>const değerleri

**Const** anahtar sözcüğü bir değişkenin değerinin sabit olduğunu belirtir ve derleyiciye programcının değiştirmesini engellemesini söyler.

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

İçinde C++, sabit değerleri tanımlamak için [#define](../preprocessor/hash-define-directive-c-cpp.md) Önişlemci yönergesi yerine **const** anahtar sözcüğünü kullanabilirsiniz. **Const** ile tanımlanan değerler tür denetimine tabidir ve sabit ifadelerin yerine kullanılabilir. ' C++De, bir dizi boyutunu **const** değişkeni ile aşağıdaki gibi belirtebilirsiniz:

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

C 'de, sabit değerler varsayılan olarak dış bağlantı olarak, yalnızca kaynak dosyalarında görünebilirler. ' C++De, sabit değerler varsayılan olarak iç bağlantıya sahiptir ve bu da bunların başlık dosyalarında görünmesine izin verir.

**Const** anahtar sözcüğü, işaretçi bildirimlerinde de kullanılabilir.

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

**Const** olarak belirtilen bir değişken işaretçisi, yalnızca **const**olarak da belirtilen bir işaretçiye atanabilir.

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

**Const**olarak belirtilen nesneler için yalnızca sabit üye işlevlerini çağırabilirsiniz. Bu, sabit nesnenin hiçbir şekilde değiştirilmemesini sağlar.

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

Sabit olmayan bir nesne için sabit ya da sabit olmayan üye işlevleri çağırabilirsiniz. Ayrıca **const** anahtar sözcüğünü kullanarak bir üye işlevini aşırı yükleyebilirsiniz; Bu, sabit ve sabit olmayan nesneler için işlevin farklı bir sürümünün çağrılmasına izin verir.

**Const** anahtar sözcüğüyle oluşturucular veya Yıkıcılar bildiremezsiniz.

## <a name="const-member-functions"></a>const üye işlevleri

**Const** anahtar sözcüğüyle bir üye işlevi bildirmek, işlevin çağrıldığı nesneyi değiştirmeyerek "salt okunurdur" bir işlev olduğunu belirtir. Sabit bir üye işlevi, statik olmayan veri üyelerini değiştiremez veya sabit olmayan herhangi bir üye işlevi çağırabilir. Sabit bir üye işlevi bildirmek için bağımsız değişken listesinin kapatma parantezinden sonra **const** anahtar sözcüğünü yerleştirin. Hem bildiriminde hem de tanımda **const** anahtar sözcüğü gereklidir.

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

Bir değişkeni C kaynak kodu dosyasında **const** olarak bildirdiğinizde şu şekilde yapabilirsiniz:

```cpp
const int i = 2;
```

Daha sonra bu değişkeni başka bir modülde aşağıdaki şekilde kullanabilirsiniz:

```cpp
extern const int i;
```

Ancak, içinde C++aynı davranışı almak için **const** değişkeninizi şöyle bildirmeniz gerekir:

```cpp
extern const int i = 2;
```

Bir **dış** değişkeni bir C kaynak kodu dosyasında kullanmak üzere C++ bir kaynak kod dosyasında bildirmek istiyorsanız şunu kullanın:

```cpp
extern "C" const int x=10;
```

C++ derleyici tarafından değiştirmeyi adını engellemek için.

## <a name="remarks"></a>Açıklamalar

Bir üye işlevinin parametre listesini takip eden **const** anahtar sözcüğü, işlevin çağrıldığı nesneyi değiştirmediği belirtir.

**Const**hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [const ve volatile İşaretçileri](../cpp/const-and-volatile-pointers.md)

- [Tür niteleyicileri (C dil başvurusu)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)
