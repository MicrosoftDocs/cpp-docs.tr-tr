---
title: switchifade (C++)
description: switchMicrosoft Visual Studio C++ ' daki standart C++ bildirimine başvuru.
ms.date: 04/25/2020
f1_keywords:
- default_cpp
- switch_cpp
- case_cpp
helpviewer_keywords:
- switch keyword [C++]
- case keyword [C++], in switch statements
- default keyword [C++]
no-loc:
- switch
- case
- default
- break
- while
- opt
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: d43a7a64b5a74f00833093ae8999d73edd7f5753
ms.sourcegitcommit: c4cf8976939dd0e13e25b82930221323ba6f15d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83389707"
---
# <a name="switch-statement-c"></a>`switch`ifade (C++)

İntegral ifadesinin değerine bağlı olarak kodun birden çok bölümü arasında seçim yapılmasına izin verir.

## <a name="syntax"></a>Sözdizimi

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp;__`switch`__&nbsp;__`(`__&nbsp;*`init-statement`*<sub>opt</sub> <sup>C++ 17</sup>&nbsp;*`condition`*&nbsp;__`)`__&nbsp;*`statement`*

> *`init-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression-statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`simple-declaration`*

> *`condition`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`attribute-specifier-seq`*<sub>opt</sub>&nbsp;*`decl-specifier-seq`*&nbsp;*`declarator`*&nbsp;*`brace-or-equal-initializer`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; __`case`__&nbsp;*`constant-expression`*&nbsp;__`:`__&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; __`default`__&nbsp;__`:`__&nbsp;*`statement`*

## <a name="remarks"></a>Açıklamalar

Bir __`switch`__ ifade, denetimin *`labeled-statement`* değerine bağlı olarak deyimin gövdesinde bir öğesine aktarılmasına neden olur *`condition`* .

, *`condition`* Bir integral türüne sahip olmalı veya tam sayı türüne belirsiz dönüştürmesi olan bir sınıf türü olmalıdır. Integral yükseltme, [Standart dönüşümlerde](standard-conversions.md)açıklandığı gibi gerçekleşir.

__`switch`__ İfade gövdesi bir dizi __`case`__ etiket ve isteğe bağlı bir __`default`__ etiketten oluşur. *`labeled-statement`*, Bu etiketlerin ve izleyen deyimlerden biridir. Etiketli deyimler sözdizimsel gereksinimler değildir, ancak __`switch`__ deyim bu olmadan anlamsız değildir. *`constant-expression`* Deyimlerde iki değer __`case`__ aynı değere değerlendirilemiyor. __`default`__ Etiket yalnızca bir kez görünebilir. __`default`__ İfade genellikle sonuna yerleştirilir, ancak deyimin gövdesinde herhangi bir yerde görünebilirler __`switch`__ . __`case`__ Or __`default`__ etiketi yalnızca bir deyimin içinde yer alabilir __`switch`__ .

*`constant-expression`* Her etikette, __`case`__ ile aynı türde bir sabit değere dönüştürülür *`condition`* . Daha sonra eşitlik için ile karşılaştırılır *`condition`* . Denetim, __`case`__ *`constant-expression`* değeri ile eşleşen değerden sonra ilk ifadeye geçer *`condition`* . Ortaya çıkan davranış aşağıdaki tabloda gösterilmiştir.

### <a name="switch-statement-behavior"></a>`switch`ifade davranışı

| Koşul | Eylem |
|--|--|
| Dönüştürülen değer yükseltilen denetim ifadesinin ile eşleşiyor. | Denetim, etiketini izleyen deyime aktarılır. |
| Sabitlerden hiçbiri, etiketlerdeki sabitler ile eşleşmiyor __`case`__ ; bir __`default`__ etiket var. | Denetim __`default`__ etikete aktarılır. |
| Sabitlerden hiçbiri, etiketlerdeki sabitler ile eşleşmiyor __`case`__ ; etiket yok __`default`__ . | Denetim, deyimden sonraki deyime aktarılır __`switch`__ . |

Eşleşen bir ifade bulunursa, yürütme daha sonra veya etiketlere devam edebilir __`case`__ __`default`__ . [`break`](../cpp/break-statement-cpp.md)Deyimin ardından, yürütmeyi durdurmak ve denetimi deyimden sonra bildirime aktarmak için kullanılır __`switch`__ . Bir deyimleri olmadan, __`break`__ eşleşen __`case`__ etiketten, __`switch`__ ve dahil olmak üzere her bir ifade __`default`__ yürütülür. Örneğin:

```cpp
// switch_statement1.cpp
#include <stdio.h>

int main() {
   const char *buffer = "Any character stream";
   int uppercase_A, lowercase_a, other;
   char c;
   uppercase_A = lowercase_a = other = 0;

   while ( c = *buffer++ )   // Walks buffer until NULL
   {
      switch ( c )
      {
         case 'A':
            uppercase_A++;
            break;
         case 'a':
            lowercase_a++;
            break;
         default:
            other++;
      }
   }
   printf_s( "\nUppercase A: %d\nLowercase a: %d\nTotal: %d\n",
      uppercase_A, lowercase_a, (uppercase_A + lowercase_a + other) );
}
```

Yukarıdaki örnekte, `uppercase_A` `c` büyük harfli ise artırılır `'A'` . __`break`__ After ifadesinin deyimin `uppercase_A++` ve denetimin yürütülmesi sona erer __`switch`__ __`while`__ . __`break`__ Bu ifade olmadan, yürütme bir sonraki etiketli ifadeye "geçer" `lowercase_a` ve `other` Ayrıca arttırılır. Benzer bir amaç, __`break`__ için ifadesiyle sunulur `case 'a'` . `c`Küçük harfli ise `'a'` , `lowercase_a` artırılır ve __`break`__ ifade, __`switch`__ ifade gövdesini sonlandırır. `c` `'a'` Veya değilse `'A'` , __`default`__ ifade yürütülür.

**Visual Studio 2017 ve üzeri:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)Ile kullanılabilir) `[[fallthrough]]` özniteliği c++ 17 standardında belirtilir. Bunu bir __`switch`__ bildirimde kullanabilirsiniz. Derleyici veya kodu okuyan herkese yönelik bir ipucu, bu yana gelen davranış bilerek yapılır. Microsoft C++ derleyicisi Şu anda fallthrough davranışında uyarı vermiyor, bu nedenle bu özniteliğin derleyici davranışı üzerinde hiçbir etkisi yoktur. Örnekte, öznitelik Sonlandırılmamış etiketli deyimin içindeki boş bir ifadeye uygulanır. Diğer bir deyişle, noktalı virgül gereklidir.

```cpp
int main()
{
    int n = 5;
    switch (n)
    {

    case 1:
        a();
        break;
    case 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    case 3:
        c();
        break;
    default:
        d();
        break;
    }

    return 0;
}
```

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir). Bir __`switch`__ ifadede *`init-statement`* , noktalı virgülle biten bir yan tümcesi olabilir. Kapsamı deyimin bloğu ile sınırlı olan bir değişkeni tanıtır ve başlatır __`switch`__ :

```cpp
    switch (Gadget gadget(args); auto s = gadget.get_status())
    {
    case status::good:
        gadget.zip();
        break;
    case status::bad:
        throw BadGadget();
    };
```

Bir deyimin iç bloğu, __`switch`__ *erişilebilir*oldukları sürece başlatıcıları olan tanımlar içerebilir, diğer bir deyişle, tüm olası yürütme yolları tarafından atlanmaz. Bu bildirimler kullanılarak tanıtılan adların yerel kapsamı vardır. Örneğin:

```cpp
// switch_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    switch( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    case 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        break;

    case 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        break;

    default:
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        break;
    }
}
```

Bir __`switch`__ ifade iç içe olabilir. İç içe geçmiş olduğunda __`case`__ veya __`default`__ etiketleri, __`switch`__ bunları kapsayan en yakın deyimle ilişkilendirir.

### <a name="microsoft-specific-behavior"></a>Microsoft 'a özgü davranış

Microsoft C++, __`case`__ bir deyimindeki değer sayısını sınırlamaz __`switch`__ . Numara yalnızca kullanılabilir bellekle sınırlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
