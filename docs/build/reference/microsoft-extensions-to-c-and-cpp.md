---
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
ms.openlocfilehash: dab8ac23be8b66ca84c57514c6c04e94dddebaae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321195"
---
# <a name="microsoft-extensions-to-c-and-c"></a>C ve C++ için Microsoft uzantıları

Visual C++, ANSI C ve ANSI C++ standartları şu şekilde genişletir.

## <a name="keywords"></a>anahtar sözcükler

Bazı anahtar sözcükler eklenir. Listede [anahtar sözcükleri](../../cpp/keywords-cpp.md), iki önde gelen altçizgilere sahip anahtar sözcükleri Visual C++ uzantılarıdır.

## <a name="out-of-class-definition-of-static-const-integral-or-enum-members"></a>Statik const tamsayı (veya numaralandırma) üyeleri sınıf tanımının dışında

Standart altında (**/Za**), burada gösterildiği gibi veri üyeleri için bir sınıf tanımı yapmalısınız:

```cpp
class CMyClass  {
   static const int max = 5;
   int m_array[max];
}
// . . .
const int CMyClass::max;   // out of class definition
```

Altında **/Ze**, sınıf çıkış tanımı için statik, const tamsayı ve const numaralandırma verisi üyelerinin isteğe bağlıdır. Yalnızca statik ve const sabit listeleri ve integraller başlatıcıları bir sınıfta olabilir; başlatma ifadesi bir sabit ifade olmalıdır.

Bir üst bilgisinde dosya ve üstbilgi dosyasını dahil sağlanan birden çok kaynak dosyalarında bir sınıf tanımı olduğunda hataları önlemek için [selectany](../../cpp/selectany.md). Örneğin:

```cpp
__declspec(selectany) const int CMyClass::max = 5;
```

## <a name="casts"></a>Yayınları

C++ derleyicisi ve C derleyicisi bu türden ANSI olmayan yayınları destekler:

- L-değerler üretmek için ANSI olmayan yayınlar. Örneğin:

   ```C
   char *p;
   (( int * ) p )++;
   ```

   > [!NOTE]
   > Bu uzantı yalnızca C dilinde kullanılabilir. C++ kodunda aşağıdaki ANSI C standart form, farklı türden bir işaretçi ise gibi bir işaretçi değiştirmek için kullanabilirsiniz.

   ANSI C standardı için uygun olması için şu şekilde bir önceki örnekte yazılması.

   ```C
   p = ( char * )(( int * )p + 1 );
   ```

- ANSI olmayan işlev işaretçisinin veri işaretçisine çevirir. Örneğin:

   ```C
   int ( * pfunc ) ();
   int *pdata;
   pdata = ( int * ) pfunc;
   ```

   Aynı tür dönüştürme gerçekleştirmek ve aynı zamanda ANSI uyumluluğu korumak için işlev işaretçisi türüne çevirebilirsiniz bir `uintptr_t` veri işaretçisi dönüştürme önce:

   ```C
   pdata = ( int * ) (uintptr_t) pfunc;
   ```

## <a name="variable-length-argument-lists"></a>Değişken uzunlukta bağımsız değişken listeleri

C++ derleyicisi ve C derleyicisi, değişken sayıda bağımsız değişken, bunun yerine bir tür sağlayan bir işlev tanımı tarafından izlenen belirten işlev bildirimcisi destekler:

```cpp
void myfunc( int x, ... );
void myfunc( int x, char * c )
{ }
```

## <a name="single-line-comments"></a>Tek satırlı açıklama

İki eğik çizgi kullanılarak kullanıma sunulan tek satırlık açıklamaları C derleyicisi destekler (/ /) karakteri:

```C
// This is a single-line comment.
```

## <a name="scope"></a>Kapsam

C derleyicisi kapsamı ile ilgili aşağıdaki özellikleri destekler.

- Extern öğesi static olarak yeniden tanımlaması:

   ```C
   extern int clip();
   static int clip()
   {}
   ```

- Zararsız typedef yeniden tanımlaması aynı kapsam dahilinde kullanın:

   ```C
   typedef int INT;
   typedef int INT;
   ```

- İşlev bildirimleri, dosya kapsamına sahip:

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

- Blok kapsamı değişkenlerin nonconstant ifadeleri kullanılarak başlatılan kullanın:

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

## <a name="data-declarations-and-definitions"></a>Veri bildirimler ve tanımlar

C derleyicisi, aşağıdaki veri bildirimi ve tanımı özellikleri destekler.

- Karma karakter ve dize sabitleri bir başlatıcıda:

   ```C
   char arr[5] = {'a', 'b', "cde"};
   ```

- Bit alanları dışındaki temel türleri olan **işaretsiz int** veya **signed int**.

- Bir tür olmayan bildiriciler:

   ```C
   x;
   int main( void )
   {
       x = 1;
   }
   ```

- Yapılar ve birleşimler içinde son alan olarak boyutsuz diziler:

   ```C
   struct zero
   {
       char *c;
       int zarray[];
   };
   ```

- Adsız (anonim) yapılar:

   ```C
   struct
   {
       int i;
       char *s;
   };
   ```

- Adsız (anonim) birleşimler:

   ```C
   union
   {
       int i;
       float fl;
   };
   ```

- Adsız Üyeler:

   ```C
   struct s
   {
      unsigned int flag : 1;
      unsigned int : 31;
   }
   ```

## <a name="intrinsic-floating-point-functions"></a>İç kayan nokta işlevleri

Her iki x86 C++ derleyicisi ve C derleyicisi destekleyen satır içi nesil `atan`, `atan2`, `cos`, `exp`, `log`, `log10`, `sin`, `sqrt`, ve `tan` işlevleri olduğunda **/Oi** belirtilir. Bu iç kullanıldığında değil ayarlandığından C derleyicisi için ANSI uyumluluğu kaybolur `errno` değişkeni.

## <a name="passing-a-non-const-pointer-parameter-to-a-function-that-expects-a-reference-to-a-const-pointer-parameter"></a>Bir const işaretçisi parametre başvurusu const olmayan işaretçi parametresi, bir işleve geçirme bekliyor

Bu C++ uzantısıdır. Bu kod ile derlenir **/Ze**:

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

Altında **/Ze**, aşağıdaki işleçleri metin biçimlerinin kullanmak istiyorsanız iso646.h eklemek zorunda:

- & & (ve)

- & = (and_eq)

- & (bitand)

- &#124;(bitor)

- ~ (compl)

- ! (not)

- ! = (not_eq)

- &#124;&#124;(veya)

- &#124;(or_eq) =

- ^ (xor)

- ^ = (xor_eq)

## <a name="address-of-string-literal-has-type-const-char--not-const-char--"></a>Dize sabitinin adresi olan türü const char [], olmayan const char (*)]

Aşağıdaki örnek çıkış `char const (*)[4]` altında **/Za**, ancak `char const [4]` altında **/Ze**.

```cpp
#include <stdio.h>
#include <typeinfo>

int main()
{
    printf_s("%s\n", typeid(&"abc").name());
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [/Za, /Ze (Dil Uzantılarını Devre Dışı Bırak)](za-ze-disable-language-extensions.md)
- [MSVC Derleyicisi Seçenekleri](compiler-options.md)
- [MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
