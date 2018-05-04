---
title: Değişken bağımsız değişken listeleri (C++) işlevleriyle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], variable number of
- variable argument lists
- declarators, functions
- argument lists [C++], variable number of
- declaring functions [C++], variables
- function calls, variable number of arguments
ms.assetid: 27c2f83a-21dd-44c6-913c-2834cb944703
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14bbb56c7ae62bd7ef8c58b45704a4ba809965e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="functions-with-variable-argument-lists--c"></a>Değişken bağımsız değişken işlevleri listeler (C++)
İşlev bildirimleri son üyesini üç nokta (...) can olduğu değişken sayıda bağımsız değişken alın. Bu durumlarda, C++ tür açıkça bildirilen bağımsız değişkenleri yalnızca denetlemesini sağlar. Bir işlev sayısını ve türlerini bağımsız değişkenlerinin bile genel değişebilir şekilde yapmanız gerektiğinde değişken bağımsız değişken listeleri kullanabilirsiniz. Ailesi işlevlerini değişken bağımsız değişken listeleri kullanan işlevler örneğidir. `printf` *bağımsız değişken bildirimi listesi*  
  
## <a name="functions-with-variable-arguments"></a>Değişken bağımsız değişken işlevleri  
 Bağımsız değişkenler bildirilen olanlar sonra erişim, standart INCLUDE dosyasında yer alan makroları kullanın \<stdarg.h > aşağıda açıklandığı gibi.  
  
 **Microsoft özel**  
  
 Microsoft C++ son bağımsız değişken üç nokta ise ve üç nokta virgül koyarak bağımsız değişken olarak belirtilmesi üç nokta sağlar. Bu nedenle, bildirimi `int Func( int i, ... );` geçerli, ama `int Func( int i ... );` değil.  
  
 **SON Microsoft özel**  
  
 Değişken sayıda bağımsız değişken alan bir işlevin bildirimi kullanılmaması olsa bile en az bir yer tutucu bağımsız değişkeni gerektirir. Bu yer tutucu bağımsız değişken sağlanmazsa, kalan bağımsız değişkenleri erişmek için yolu yoktur.  
  
 Tür bağımsız değişkenleri `char` geçirilen değişken bağımsız değişken olarak, bunlar yazmak için dönüştürülür `int`. Benzer şekilde, tür bağımsız değişkenleri **float** geçirilen değişken bağımsız değişken olarak, bunlar yazmak için dönüştürülür **çift**. Her zamanki Entegral ve kayan nokta promosyonlar tabi değişkenleridir diğer türleri. Bkz: [standart dönüşümler](standard-conversions.md) daha fazla bilgi için.  
  
 Bağımsız değişken listesinde üç nokta (...) kullanarak, değişken listeleri gerektiren işlevleri bildirilir. Açıklanan makroları ve türleri kullanma \<stdarg.h > bir değişken listesi tarafından geçirilen erişim bağımsız değişkenlerini dosyasına içerir. Bu makrolar hakkında daha fazla bilgi için bkz: [va_arg, va_copy, va_end, va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md). C çalışma zamanı kitaplığı belgeleri.  
  
 Aşağıdaki örnek, makroları türü ile birlikte nasıl çalıştığını gösterir (bildirilen \<stdarg.h >): 
  
```  
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
  
1.  Değişken bağımsız değişkenlerine erişebilmek için önce `va_list` türünde bir değişken olarak bir liste işaretçisi oluşturmanız gerekir. Yukarıdaki örnekte, işaretleyici `vl` olarak adlandırılmıştır.  
  
2.  Bağımsız değişkenlere `va_arg` makrosu kullanılarak erişilir. `va_arg` makrosuna, yığından doğru bayt sayısını aktarabilmesi için alınacak bağımsız değişkenin türünü bildirmeniz gerekir. `va_arg` için çağırma program tarafından sağlanandan farklı boyutta olan hatalı bir tür belirtirseniz, sonuçlar tahmin edilemez.  
  
3.  Elde edilen sonucu `va_arg` makrosunu kullanarak istediğiniz türe açıkça atamanız gerekir.  
  
 Değişken bağımsız değişken işleme sonlandırmak için makrosu çağırmanız gerekir.`va_end`