---
title: Değişken bağımsız değişken listeleriyle işlevler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], variable number of
- variable argument lists
- declarators, functions
- argument lists [C++], variable number of
- declaring functions [C++], variables
- function calls, variable number of arguments
ms.assetid: 27c2f83a-21dd-44c6-913c-2834cb944703
ms.openlocfilehash: f456f31dec631f7d9340563a93dfafeea49a72b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178450"
---
# <a name="functions-with-variable-argument-lists--c"></a>Değişken bağımsız değişken listeleriyle işlevler (C++)

Son üyesinin üç nokta (...) olduğu işlev bildirimleri, değişken sayıda bağımsız değişken alabilir. Bu durumlarda, C++ yalnızca açıkça belirtilen bağımsız değişkenler için tür denetimi sağlar. Bağımsız değişkenlerin sayısı ve türleri farklılık gösterebileceğinden, bir işlevi yapmanız gerektiğinde değişken bağımsız değişken listelerini kullanabilirsiniz. İşlev ailesi, değişken bağımsız değişken listelerini kullanan işlevlere bir örnektir.`printf`*bağımsız değişkeni-bildirim-liste*

## <a name="functions-with-variable-arguments"></a>Değişken bağımsız değişkenleri olan işlevler

Bildirenlerden sonra bağımsız değişkenlere erişmek için, aşağıda açıklandığı gibi, \<stdarg. h > Standart içerme dosyasında bulunan makroları kullanın.

**Microsoft 'a özgü**

Üç C++ nokta en son bağımsız değişkense ve üç nokta daha önce bir virgül kullanıyorsa Microsoft üç noktanın bağımsız değişken olarak belirtilmesini sağlar. Bu nedenle bildirim `int Func( int i, ... );` geçerlidir ancak `int Func( int i ... );` değildir.

**SON Microsoft 'a özgü**

Değişken sayıda bağımsız değişken alan bir işlevin bildirimi, kullanılmasa bile en az bir yer tutucu bağımsız değişkeni gerektirir. Bu yer tutucu bağımsız değişkeni sağlanmazsa, kalan bağımsız değişkenlere erişmenin bir yolu yoktur.

**Char** türündeki bağımsız değişkenler değişken bağımsız değişken olarak geçirildiğinde, **int**türüne dönüştürülür. Benzer şekilde, **float** türündeki bağımsız değişkenler değişken bağımsız değişken olarak geçirildiğinde, **Double**türüne dönüştürülür. Diğer türlerin bağımsız değişkenleri, her zamanki integral ve kayan nokta promosyonlara tabidir. Daha fazla bilgi için bkz. [Standart dönüştürmeler](standard-conversions.md) .

Değişken listeleri gerektiren işlevler, bağımsız değişken listesindeki üç nokta (...) kullanılarak belirtilir. Bir değişken listesi tarafından geçirilen bağımsız değişkenlere erişmek için \<stdarg. h > içerme dosyasında açıklanan türleri ve makroları kullanın. Bu makrolar hakkında daha fazla bilgi için bkz. [va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). C çalışma zamanı kitaplığının belgelerinde.

Aşağıdaki örnek, makroların (\<stdarg. h > içinde belirtilen) ile birlikte nasıl çalıştığını gösterir:

```cpp
// variable_argument_lists.cpp
#include <stdio.h>
#include <stdarg.h>

//  Declaration, but not definition, of ShowVar.
void ShowVar( char *szTypes, ... );
int main() {
   ShowVar( "fcsi", 32.4f, 'a', "Test string", 4 );
}

//  ShowVar takes a format string of the form
//   "ifcs", where each character specifies the
//   type of the argument in that position.
//
//  i = int
//  f = float
//  c = char
//  s = string (char *)
//
//  Following the format specification is a variable
//  list of arguments. Each argument corresponds to
//  a format character in the format string to which
// the szTypes parameter points
void ShowVar( char *szTypes, ... ) {
   va_list vl;
   int i;

   //  szTypes is the last argument specified; you must access
   //  all others using the variable-argument macros.
   va_start( vl, szTypes );

   // Step through the list.
   for( i = 0; szTypes[i] != '\0'; ++i ) {
      union Printable_t {
         int     i;
         float   f;
         char    c;
         char   *s;
      } Printable;

      switch( szTypes[i] ) {   // Type to expect.
         case 'i':
            Printable.i = va_arg( vl, int );
            printf_s( "%i\n", Printable.i );
         break;

         case 'f':
             Printable.f = va_arg( vl, double );
             printf_s( "%f\n", Printable.f );
         break;

         case 'c':
             Printable.c = va_arg( vl, char );
             printf_s( "%c\n", Printable.c );
         break;

         case 's':
             Printable.s = va_arg( vl, char * );
             printf_s( "%s\n", Printable.s );
         break;

         default:
         break;
      }
   }
   va_end( vl );
}
//Output:
// 32.400002
// a
// Test string
```

Yukarıdaki örnekte, bu önemli kavramlar gösterilmektedir:

1. Değişken bağımsız değişkenlerine erişebilmek için önce `va_list` türünde bir değişken olarak bir liste işaretçisi oluşturmanız gerekir. Yukarıdaki örnekte, işaretleyici `vl` olarak adlandırılmıştır.

1. Bağımsız değişkenlere `va_arg` makrosu kullanılarak erişilir. `va_arg` makrosuna, yığından doğru bayt sayısını aktarabilmesi için alınacak bağımsız değişkenin türünü bildirmeniz gerekir. `va_arg` için çağırma program tarafından sağlanandan farklı boyutta olan hatalı bir tür belirtirseniz, sonuçlar tahmin edilemez.

1. Elde edilen sonucu `va_arg` makrosunu kullanarak istediğiniz türe açıkça atamanız gerekir.

Değişken bağımsız değişken işlemeyi sonlandırmak için makroyu çağırmanız gerekir.`va_end`
