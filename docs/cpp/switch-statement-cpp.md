---
title: switchdeyim (C++)
description: Microsoft Visual Studio switch C++'daki Standart C++ deyimine başvuru.
ms.date: 04/15/2020
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
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: 1f65d4699423d74be9c75a9be47e543a9a1256e2
ms.sourcegitcommit: 9266fc76ac2e872e35a208b4249660dfdfc87cba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81480829"
---
# <a name="opno-locswitch-statement-c"></a>switchdeyim (C++)

İntegral ifadesinin değerine bağlı olarak, kodun birden çok bölümü arasında seçim yapılmasına izin verir.

## <a name="syntax"></a>Sözdizimi

> **`switch (`**\[ *initialization* **`;`**] *ifadesi***`)`**\
> **`{`**\
> &nbsp;&nbsp;&nbsp;&nbsp;**`case`***sabit ifade* **`:`** *deyimi*\
> &nbsp;&nbsp;&nbsp;&nbsp;\[**`default :`***deyim*] \
> **`}`**

## <a name="remarks"></a>Açıklamalar

*İfadenin* ayrılmaz bir türü olmalı veya integral türüne kesin bir dönüştürme olan bir sınıf türü olmalıdır. İntegral [promosyonu Standart dönüşümlerde](standard-conversions.md)açıklandığı şekilde gerçekleşir.

Ekstre gövdesi bir **case** dizi etiket **default** ve isteğe bağlı bir etiketten oluşur. **switch** Etiketleri izleyen ifadelere topluca *etiketli* ifadeler denir. Etiketli ifadeler sözdiziliş gereksinimleri değildir, **switch** ancak ifade onlar olmadan anlamsızdır. İfadelerde **case** iki sabit ifade aynı değerde değerlendirilemeyebilir. Etiket **default** yalnızca bir kez görünebilir. İfade **default** genellikle sonunda yerleştirilir, ancak **switch** ifadenin gövdesinde herhangi bir yerde görünebilir. A **case** **default** veya etiket yalnızca **switch** bir deyimin içinde görünebilir.

Her *constant-expression* **case** etiketteki sabit ifade *ifade*türüne dönüştürülür. Sonra, eşitlik için *ifade* ile karşılaştırılır. Denetim, **case** *sabit ifade* *ifadesinin*değeriyle eşleşen ifadeye geçer. Ortaya çıkan davranış aşağıdaki tabloda gösterilir.

### <a name="switch-statement-behavior"></a>İfade davranışını değiştir

| Koşul | Eylem |
|--|--|
| Dönüştürülen değer, yükseltilen denetlenen ifadeyle eşleşir. | Denetim, bu etiketi izleyen bildirime aktarılır. |
| Sabitlerin hiçbiri **case** etiketlerdeki sabitlerle eşleşmez; bir **default** etiket mevcuttur. | Denetim etikete **default** aktarılır. |
| Sabitlerin hiçbiri **case** etiketlerdeki sabitlerle eşleşmez; etiket **default** yok. | **switch** Denetim, açıklamadan sonra ifadeye aktarılır. |

Eşleşen bir ifade bulunursa, yürütme **case** **default** daha sonra veya etiketler üzerinden devam edebilir. İfade, [`break`](../cpp/break-statement-cpp.md) yürütmeyi durdurmak ve bildirimden **switch** sonra beyanı besmele aktarmak için kullanılır. Bir **break** açıklama olmadan, eşleşen **case** etiketten sonuna kadar **switch** her ifade **default**, , , yürütülür. Örneğin:

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

Yukarıdaki örnekte, `uppercase_A` bir büyük harf `c` `'A'`ise artımlı. İfade, **break** `uppercase_A++` ifade gövdesinin yürütülmesini sona erdirdikten sonra döngüye **while** geçer. **switch** İfade **break** olmadan, yürütme bir sonraki etiketli deyime "düşer" `lowercase_a` `other` böylece ve aynı zamanda artımlı olacaktır. Benzer bir amaç için **break** `case 'a'`ifade tarafından sunulmaktadır. Küçük `c` bir harf `'a'` `lowercase_a` ise, artımlı **break** ve deyimi **switch** deyimi gövdesi sona erer. Bir `c` `'a'` veya `'A'`değilse, **default** deyim yürütülür.

**Visual Studio 2017 ve sonrası:** (/std:c++17 ile kullanılabilir ) Öznitelik [/std:c++17](../build/reference/std-specify-language-standard-version.md) `[[fallthrough]]` C++17 standardında belirtilir. Bir **switch** deyimde kullanabilirsiniz. Derleyiciye veya kodu okuyan herkese düşme davranışının kasıtlı olduğuna dair bir ipucu. Microsoft C++ derleyicisi şu anda fallthrough davranışı konusunda uyarmaz, bu nedenle bu öznitelik derleyici davranışı üzerinde hiçbir etkisi yoktur. Örnekte, öznitelik, sonlandırılmamış etiketli deyim içinde boş bir deyim uygulanır. Başka bir deyişle, yarı kolon gereklidir.

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

**Visual Studio 2017 sürüm 15.3 ve sonrası** [(/std:c++17](../build/reference/std-specify-language-standard-version.md)ile birlikte kullanılabilir). Bir switch deyimin *bir başlatma* yan tümcesi olabilir. Kapsamı switch deyimbloğuyla sınırlı olan bir değişkeni tanıtır ve başlatır:

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

Bir **switch** deyimin iç *bloğu, olası*tüm yürütme yolları tarafından atlanmadıkları sürece, başlangıç lı tanımlar içerebilir. Bu bildirimler kullanılarak tanıtılan adlar yerel kapsama sahiptir. Örneğin:

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

İfade **switch** iç içe olabilir. İç içe **case** geçtiğinde, **default** etiketler onları **switch** içine alan en yakın ifadeyle ilişkilendirilir.

### <a name="microsoft-specific-behavior"></a>Microsoft'a özgü davranış

Microsoft C, bir **case** **switch** deyimdeki değer sayısını sınırlamaz. Sayı yalnızca kullanılabilir bellekle sınırlıdır. ANSI C, bir **case** **switch** bildirimde en az 257 etikete izin verilmesini gerektirir.

Microsoft default C için Microsoft uzantıları etkin olmasıdır. Bu uzantıları devre dışı kullanabilirsiniz / [Za](../build/reference/za-ze-disable-language-extensions.md) derleyici sabunu kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
