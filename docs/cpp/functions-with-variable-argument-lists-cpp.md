---
title: Değişken bağımsız değişken işlevleri listeler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], variable number of
- variable argument lists
- declarators, functions
- argument lists [C++], variable number of
- declaring functions [C++], variables
- function calls, variable number of arguments
ms.assetid: 27c2f83a-21dd-44c6-913c-2834cb944703
ms.openlocfilehash: 1f366af6f4058ffb8356017d59a7c176a978b860
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153859"
---
# <a name="functions-with-variable-argument-lists--c"></a>Değişken bağımsız değişken işlevleri listeler (C++)

İşlev bildirimi üç nokta (...) can son üyesi olduğu, değişken sayıda bağımsız değişken alır. Bu durumlarda, C++ tür açıkça bildirilen bağımsız değişkenleri yalnızca denetlemesini sağlar. Bir işlev bağımsız değişkenlerinin türlerine ve sayı bile genel değişebilir şekilde yapmanız gerektiğinde, değişken bağımsız değişken listeleri kullanabilirsiniz. Değişken bağımsız değişken listeleri kullanan işlevler örneği işlevleri ailesidir. `printf` *bağımsız değişken bildirim listesi*

## <a name="functions-with-variable-arguments"></a>Değişken bağımsız değişken işlevleri

Bu sonra bildirilen bağımsız değişkenlerine erişmek için standart içerme dosyasında yer alan makroları \<stdarg.h > aşağıda açıklandığı gibi.

**Microsoft'a özgü**

Microsoft C++, üç nokta son bağımsız değişken ise ve üç nokta, virgül tarafından öncesinde bir bağımsız değişken olarak belirtilmesi için üç noktaya izin verir. Bu nedenle, bildirimi `int Func( int i, ... );` geçerli, ancak `int Func( int i ... );` değil.

**END Microsoft özgü**

Kullanılmadığını bile en az bir yer tutucu bağımsız değişkeni, değişken sayıda bağımsız değişken alan bir işlev bildirimi gerektirir. Bu yer tutucu bağımsız değişken sağlanmazsa, kalan bağımsız değişkenleri erişmenin hiçbir yolu yoktur.

Zaman türü bağımsız değişkenleri **char** geçirilir değişken bağımsız değişkenler olarak, bunlar türüne dönüştürülür **int**. Benzer şekilde, tür bağımsız değişkenleri **float** geçirilir değişken bağımsız değişkenler olarak, bunlar türüne dönüştürülür **çift**. Diğer tür bağımsız değişkenleri her zamanki integral ve kayan nokta yükseltmeler tabi olan. Bkz: [standart dönüştürmeler](standard-conversions.md) daha fazla bilgi için.

Değişken listeleri gerektiren İşlevler, bağımsız değişken listesinde üç nokta (...) kullanarak bildirilir. Türleri ve şurada açıklanan makroları kullanın \<stdarg.h > bir değişken listesi tarafından geçirilen erişim bağımsız bir dosyaya ekleyin. Bu makrolar hakkında daha fazla bilgi için bkz: [va_copy, olan va_arg, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). C çalışma zamanı kitaplığı belgeleri.

Aşağıdaki örnek, makroları türü ile birlikte nasıl çalıştığını gösterir (bildirilen \<stdarg.h >):

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

Değişken bağımsız değişken işlemesini sonlandırmak için makro çağırmanız gerekir.`va_end`