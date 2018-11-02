---
title: const (C++)
ms.date: 11/04/2016
f1_keywords:
- const_cpp
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
ms.openlocfilehash: 759ee503acb12f6c1a30fbbfaf87a8f66433e571
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463251"
---
# <a name="const-c"></a>const (C++)

Bir veri bildirimi değiştirirken **const** anahtar sözcüğü, nesne veya değişkenin değiştirilebilir olmadığını belirtir.

## <a name="syntax"></a>Sözdizimi

```
const declaration ;
member-function const ;
```

## <a name="const-values"></a>const değerleri

**Const** anahtar sözcüğü, bir değişkenin değeri sabittir ve Programcı bunu değiştirmesini önlemek için derleyiciye belirtir.

```cpp
// constant_values1.cpp
int main() {
   const int i = 5;
   i = 10;   // C3892
   i++;   // C2105
}
```

C++'ta kullanabileceğiniz **const** anahtar sözcüğü yerine [#define](../preprocessor/hash-define-directive-c-cpp.md) sabit değerler tanımlamak üzere önişlemci yönergesi. İle tanımlanan değerleri **const** tür denetimi tabi olan ve sabit ifadeler yerine kullanılabilir. C++'da bir dizinin boyutunu belirtebilirsiniz. bir **const** değişkeni aşağıdaki gibi:

```cpp
// constant_values2.cpp
// compile with: /c
const int maxarray = 255;
char store_char[maxarray];  // allowed in C++; not allowed in C
```

C'de, dış bağlantısı sabit değerleri varsayılan şekilde bunlar yalnızca kaynak dosyalarında görünebilir. C++'da sabit değerler varsayılan iç bağlantısı için hangi üstbilgi dosyalarında görünmesini sağlar.

**Const** anahtar sözcüğü işaretçi bildirimlerinde de kullanılabilir.

```cpp
// constant_values3.cpp
int main() {
   char *mybuf = 0, *yourbuf;
   char *const aptr = mybuf;
   *aptr = 'a';   // OK
   aptr = yourbuf;   // C3892
}
```

Olarak bildirilen bir değişken işaretçisi **const** olarak bildirilmiş bir işaretçiye atanabilir **const**.

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

İşlev işaretçisi geçirilen bir parametreyi değiştirmesini önlemek için sabit veri işaretçileri işlevi parametre olarak kullanabilirsiniz.

Olarak bildirilen nesneler için **const**, yalnızca sabit üye işlevleri çağırabilir. Bu sabit nesne hiçbir zaman değiştirilmez sağlar.

```cpp
birthday.getMonth();    // Okay
birthday.setMonth( 4 ); // Error
```

Sabit veya nonconstant üye nonconstant bir nesne için işlevleri çağırabilir. Üye işlevini kullanarak da aşırı yükleyebilirler **const** anahtar sözcüğü; Bu, sabit ve nonconstant nesneler için çağrılacak işlev farklı bir sürümü sağlar.

Oluşturucuları veya yıkıcıları ile bildiremezsiniz **const** anahtar sözcüğü.

## <a name="const-member-functions"></a>sabit üye işlevleri

Bir üye işlevi bildirmek **const** anahtar sözcüğü, işlev için adlandırılan nesnesini değiştirmek olmadığı bir "salt okunur" işlev olduğunu belirtir. Sabit üye işlevi herhangi bir statik olmayan veri üyesi değiştiremez veya herhangi bir üye, sabit olmayan işlevlerini çağırın. Sabit üye işlevi bildirmek için yerleştirin **const** bağımsız değişken listesinin kapatma parantezinden sonra anahtar sözcüğü. **Const** hem bildirim hem de tanımı anahtar sözcüğü gereklidir.

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

## <a name="c-and-c-const-differences"></a>C ve C++ const farklılıkları

Olarak bir değişken bildirdiğinizde **const** C kaynak kodu dosyasında olarak bunu:

```cpp
const int i = 2;
```

Ardından bu değişkeni başka bir modülde şu şekilde kullanabilirsiniz:

```cpp
extern const int i;
```

Ancak C++'da aynı davranışı sağlamak için bildirmeniz gerekir, **const** değişken olarak:

```cpp
extern const int i = 2;
```

Bildirmek istiyorsanız bir **extern** değişken bir C++ kaynak kod dosyasında kullanmak C kaynak kodu dosyasında, kullanın:

```cpp
extern "C" const int x=10;
```

C++ derleyicisi tarafından ad değiştirmeyi önlemek için.

## <a name="remarks"></a>Açıklamalar

Bir üye işlevin parametre listesi, takip ederken **const** anahtar sözcüğü işlevin kendisi için çağrıldığında nesnesini değiştirmek olmadığı belirtir.

Daha fazla bilgi için **const**, aşağıdaki konulara bakın:

- [const ve volatile İşaretçileri](../cpp/const-and-volatile-pointers.md)

- [Tür niteleyicileri (C Dil Başvurusu)](../c-language/type-qualifiers.md)

- [volatile](../cpp/volatile-cpp.md)

- [#define](../preprocessor/hash-define-directive-c-cpp.md)

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)