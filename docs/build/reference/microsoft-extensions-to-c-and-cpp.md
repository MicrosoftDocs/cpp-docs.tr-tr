---
description: 'Hakkında daha fazla bilgi edinin: C ve C++ için Microsoft uzantıları'
title: C ve C++ için Microsoft uzantıları
ms.date: 06/14/2018
helpviewer_keywords:
- or_eq operator
- ~ operator, extensions to C/C++
- '& operator, extensions to C/C++'
- '&= operator'
- iso646.h header
- Xor operator, Microsoft extensions to C/C++
- '!= operator'
- '! operator, extension to C++'
- Or operator, Microsoft extensions to C/C++
- ^ operator, extensions to C/C++
- ^= operator, C++ extensions
- xor_eq operator
- and_eq operator
- Microsoft extensions to C/C++
- '|= operator'
- '|| operator'
- And operator, extensions to C/C++
- NOT operator
- '&& operator'
- extensions, C language
- Visual C++, extensions to C/C++
- '| operator, extensions'
- not_eq operator
- Visual C, Microsoft extensions
- extensions
- compl method
ms.assetid: e811a74a-45ba-4c00-b206-2f2321b8689a
ms.openlocfilehash: fac6edbdfd559f3cebd18dcdc3b8cfca2a9336dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190698"
---
# <a name="microsoft-extensions-to-c-and-c"></a>C ve C++ için Microsoft uzantıları

Visual C++, ANSI C ve ANSI C++ standartlarını aşağıda gösterildiği gibi genişletir.

## <a name="keywords"></a>Anahtar sözcükler

Birkaç anahtar sözcük eklenir. [Anahtar kelimeler](../../cpp/keywords-cpp.md)listesinde, iki önde gelen alt çizgi olan anahtar sözcükler Visual C++ uzantılardır.

## <a name="out-of-class-definition-of-static-const-integral-or-enum-members"></a>Statik const integral (veya Enum) üyelerinin sınıf tanımının dışında

Standart (**/za**) altında, veri üyeleri için aşağıda gösterildiği gibi bir sınıf dışı tanımı yapmanız gerekir:

```cpp
class CMyClass  {
   static const int max = 5;
   int m_array[max];
}
// . . .
const int CMyClass::max;   // out of class definition
```

**/Ze** altında, sınıf dışı tanımı statik, const Entegrali ve const enum veri üyeleri için isteğe bağlıdır. Yalnızca statik ve const olan integralların ve Numaralandırmaların bir sınıfta başlatıcıları olabilir; başlatma ifadesi bir const ifadesi olmalıdır.

Bir üstbilgi dosyasında bir sınıf tanımı sağlandığında ve üstbilgi dosyası birden çok kaynak dosyaya dahil edildiğinde hatalardan kaçınmak için [selectany](../../cpp/selectany.md)kullanın. Örneğin:

```cpp
__declspec(selectany) const int CMyClass::max = 5;
```

## <a name="casts"></a>Podcast

Hem C++ derleyicisi hem de C derleyicisi, bu tür ANSI olmayan yayınları destekler:

- L değerleri üretmek için ANSI olmayan atamalar. Örneğin:

   ```C
   char *p;
   (( int * ) p )++;
   ```

   > [!NOTE]
   > Bu uzantı yalnızca C dilinde kullanılabilir. Bir işaretçiyi farklı bir türe işaretçi gibi değiştirmek için C++ kodunda aşağıdaki ANSI C standart formunu kullanabilirsiniz.

   Yukarıdaki örnek, ANSI C standardına uymak için aşağıdaki şekilde yeniden yazılabilir.

   ```C
   p = ( char * )(( int * )p + 1 );
   ```

- Bir işlev işaretçisinin bir veri işaretçisine ANSI olmayan yayınları. Örneğin:

   ```C
   int ( * pfunc ) ();
   int *pdata;
   pdata = ( int * ) pfunc;
   ```

   Aynı saçı gerçekleştirmek ve ayrıca ANSI uyumluluğunu sürdürmek için, bir `uintptr_t` veri işaretçisine dönüştürmeden önce işlev işaretçisini öğesine çevirebilirsiniz:

   ```C
   pdata = ( int * ) (uintptr_t) pfunc;
   ```

## <a name="variable-length-argument-lists"></a>Değişken uzunlukta bağımsız değişken listeleri

Hem C++ derleyicisi hem de C derleyicisi, değişken sayıda bağımsız değişken belirten bir işlev bildirimci destekler ve bunun yerine bir tür sağlayan bir işlev tanımı gelir:

```cpp
void myfunc( int x, ... );
void myfunc( int x, char * c )
{ }
```

## <a name="single-line-comments"></a>Tek satır açıklamaları

C derleyicisi, iki eğik çizgi (//) karakteri kullanılarak tanıtılan tek satırlık açıklamaları destekler:

```C
// This is a single-line comment.
```

## <a name="scope"></a>Kapsam

C derleyicisi aşağıdaki kapsamdaki ilgili özellikleri destekler.

- Extern öğelerinin statik olarak yeniden tanımları:

   ```C
   extern int clip();
   static int clip()
   {}
   ```

- Aynı kapsam içindeki zararsız typedef yeniden tanımlarının kullanımı:

   ```C
   typedef int INT;
   typedef int INT;
   ```

- İşlev bildiricileri dosya kapsamına sahiptir:

   ```C
   void func1()
   {
       extern int func2( double );
   }
   int main( void )
   {
       func2( 4 );    //  /Ze passes 4 as type double
   }                  //  /Za passes 4 as type int
   ```

- Sabit olmayan ifadeler kullanılarak başlatılan blok kapsamı değişkenlerinin kullanımı:

   ```C
   int clip( int );
   int bar( int );
   int main( void )
   {
       int array[2] = { clip( 2 ), bar( 4 ) };
   }
   int clip( int x )
   {
       return x;
   }
   int bar( int x )
   {
       return x;
   }
   ```

## <a name="data-declarations-and-definitions"></a>Veri bildirimleri ve tanımları

C derleyicisi aşağıdaki veri bildirimini ve tanım özelliklerini destekler.

- Bir başlatıcıdaki karışık karakter ve dize sabitleri:

   ```C
   char arr[5] = {'a', 'b', "cde"};
   ```

- Veya dışında temel türleri olan bit alanları **`unsigned int`** **`signed int`** .

- Türünde olmayan Bildirimciler:

   ```C
   x;
   int main( void )
   {
       x = 1;
   }
   ```

- Yapılardaki ve Birleşimlerdeki son alan olarak boyutlandırılmış diziler:

   ```C
   struct zero
   {
       char *c;
       int zarray[];
   };
   ```

- Adlandırılmamış (anonim) yapılar:

   ```C
   struct
   {
       int i;
       char *s;
   };
   ```

- Adlandırılmamış (anonim) birleşimler:

   ```C
   union
   {
       int i;
       float fl;
   };
   ```

- Adlandırılmamış Üyeler:

   ```C
   struct s
   {
      unsigned int flag : 1;
      unsigned int : 31;
   }
   ```

## <a name="intrinsic-floating-point-functions"></a>İç kayan nokta işlevleri

Hem x86 C++ derleyicisi hem de C derleyicisi `atan` , `atan2` `cos` `exp` `log` `log10` `sin` `sqrt` `tan` **/Oi** belirtildiğinde,,,,,,, ve işlevlerinin satır içi oluşturulmasını destekler. C derleyicisi için, değişken ayarlanmadığından ANSI uygunluğu bu iç bilgiler kullanıldığında kaybedilir `errno` .

## <a name="passing-a-non-const-pointer-parameter-to-a-function-that-expects-a-reference-to-a-const-pointer-parameter"></a>Const olmayan bir işaretçi parametresini bir const işaretçi parametresine başvuru bekleyen bir işleve geçirme

Bu bir C++ uzantısıdır. Bu kod, **/ze** ile derlenir:

```cpp
typedef   int   T;

const T  acT = 9;      // A constant of type 'T'
const T* pcT = &acT;   // A pointer to a constant of type 'T'

void func2 ( const T*& rpcT )   // A reference to a pointer to a constant of type 'T'
{
   rpcT = pcT;
}

T*   pT;               // A pointer to a 'T'

void func ()
{
   func2 ( pT );      // Should be an error, but isn't detected
   *pT   = 7;         // Invalidly overwrites the constant 'acT'
}
```

## <a name="iso646h-not-enabled"></a>ISO646. H etkin değil

**/Ze** altında, aşağıdaki işleçlerin metin biçimlerini kullanmak istiyorsanız iso646. h dahil etmeniz gerekir:

- && (ve)

- &= (and_eq)

- & (bitand)

- &#124; (bitor)

- ~ (compl)

- ! başlatılmadı

- ! = (not_eq)

- &#124;&#124; (veya)

- &#124;= (or_eq)

- ^ (XOR)

- ^ = (xor_eq)

## <a name="address-of-string-literal-has-type-const-char--not-const-char--"></a>Dize sabit değerinin adresi const char [] türünde, const char değil (*) []

Aşağıdaki örnek `char const (*)[4]` **/za** altında, ancak `char const [4]` **/ze** altında çıktı alacak.

```cpp
#include <stdio.h>
#include <typeinfo>

int main()
{
    printf_s("%s\n", typeid(&"abc").name());
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [/Za,/Ze (dil uzantılarını devre dışı bırak)](za-ze-disable-language-extensions.md)
- [MSVC derleyici seçenekleri](compiler-options.md)
- [MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
