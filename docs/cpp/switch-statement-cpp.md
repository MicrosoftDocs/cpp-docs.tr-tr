---
title: :::no-loc(switch):::ifade (C++)
description: :::no-loc(switch):::Microsoft Visual Studio C++ ' daki standart C++ bildirimine başvuru.
ms.date: 04/25/2020
f1_keywords:
- :::no-loc(default):::_cpp
- :::no-loc(switch):::_cpp
- :::no-loc(case):::_cpp
helpviewer_keywords:
- ':::no-loc(switch)::: keyword [C++]'
- ':::no-loc(case)::: keyword [C++], in :::no-loc(switch)::: statements'
- ':::no-loc(default)::: keyword [C++]'
no-loc:
- ':::no-loc(switch):::'
- ':::no-loc(case):::'
- ':::no-loc(default):::'
- ':::no-loc(break):::'
- ':::no-loc(while):::'
- ':::no-loc(opt):::'
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
ms.openlocfilehash: d71989b6d8af0213c4cd6d4fbd8d5a84b318701a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223596"
---
# <a name="no-locswitch-statement-c"></a>`:::no-loc(switch):::`ifade (C++)

İntegral ifadesinin değerine bağlı olarak kodun birden çok bölümü arasında seçim yapılmasına izin verir.

## <a name="syntax"></a>Sözdizimi

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp;**`:::no-loc(switch):::`**&nbsp;**`(`**&nbsp;*`init-statement`*<sub>:::no-loc(opt):::</sub> <sup>C++ 17</sup>&nbsp;*`condition`*&nbsp;**`)`**&nbsp;*`statement`*

> *`init-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression-statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`simple-declaration`*

> *`condition`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; *`expression`*\
> &nbsp;&nbsp;&nbsp;&nbsp; *`attribute-specifier-seq`*<sub>:::no-loc(opt):::</sub>&nbsp;*`decl-specifier-seq`*&nbsp;*`declarator`*&nbsp;*`brace-or-equal-initializer`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(case):::`**&nbsp;*`constant-expression`*&nbsp;**`:`**&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(default):::`**&nbsp;**`:`**&nbsp;*`statement`*

## <a name="remarks"></a>Açıklamalar

Bir **`:::no-loc(switch):::`** ifade, denetimin *`labeled-statement`* değerine bağlı olarak deyimin gövdesinde bir öğesine aktarılmasına neden olur *`condition`* .

, *`condition`* Bir integral türüne sahip olmalı veya tam sayı türüne belirsiz dönüştürmesi olan bir sınıf türü olmalıdır. Integral yükseltme, [Standart dönüşümlerde](standard-conversions.md)açıklandığı gibi gerçekleşir.

**`:::no-loc(switch):::`** İfade gövdesi bir dizi **`:::no-loc(case):::`** etiket ve bir :::no-loc(opt)::: ıonal **`:::no-loc(default):::`** etiketi içerir. *`labeled-statement`*, Bu etiketlerin ve izleyen deyimlerden biridir. Etiketli deyimler sözdizimsel gereksinimler değildir, ancak **`:::no-loc(switch):::`** deyim bu olmadan anlamsız değildir. *`constant-expression`* Deyimlerde iki değer **`:::no-loc(case):::`** aynı değere değerlendirilemiyor. **`:::no-loc(default):::`** Etiket yalnızca bir kez görünebilir. **`:::no-loc(default):::`** İfade genellikle sonuna yerleştirilir, ancak deyimin gövdesinde herhangi bir yerde görünebilirler **`:::no-loc(switch):::`** . **`:::no-loc(case):::`** Or **`:::no-loc(default):::`** etiketi yalnızca bir deyimin içinde yer alabilir **`:::no-loc(switch):::`** .

*`constant-expression`* Her etikette, **`:::no-loc(case):::`** ile aynı türde bir sabit değere dönüştürülür *`condition`* . Daha sonra eşitlik için ile karşılaştırılır *`condition`* . Denetim, **`:::no-loc(case):::`** *`constant-expression`* değeri ile eşleşen değerden sonra ilk ifadeye geçer *`condition`* . Ortaya çıkan davranış aşağıdaki tabloda gösterilmiştir.

### <a name="no-locswitch-statement-behavior"></a>`:::no-loc(switch):::`ifade davranışı

| Koşul | Eylem |
|--|--|
| Dönüştürülen değer yükseltilen denetim ifadesinin ile eşleşiyor. | Denetim, etiketini izleyen deyime aktarılır. |
| Sabitlerden hiçbiri, etiketlerdeki sabitler ile eşleşmiyor **`:::no-loc(case):::`** ; bir **`:::no-loc(default):::`** etiket var. | Denetim **`:::no-loc(default):::`** etikete aktarılır. |
| Sabitlerden hiçbiri, etiketlerdeki sabitler ile eşleşmiyor **`:::no-loc(case):::`** ; etiket yok **`:::no-loc(default):::`** . | Denetim, deyimden sonraki deyime aktarılır **`:::no-loc(switch):::`** . |

Eşleşen bir ifade bulunursa, yürütme daha sonra veya etiketlere devam edebilir **`:::no-loc(case):::`** **`:::no-loc(default):::`** . [`:::no-loc(break):::`](../cpp/:::no-loc(break):::-statement-cpp.md)Deyimin ardından, yürütmeyi durdurmak ve denetimi deyimden sonra bildirime aktarmak için kullanılır **`:::no-loc(switch):::`** . Bir deyimleri olmadan, **`:::no-loc(break):::`** eşleşen **`:::no-loc(case):::`** etiketten, **`:::no-loc(switch):::`** ve dahil olmak üzere her bir ifade **`:::no-loc(default):::`** yürütülür. Örnek:

```cpp
// :::no-loc(switch):::_statement1.cpp
#include <stdio.h>

int main() {
   const char *buffer = "Any character stream";
   int upper:::no-loc(case):::_A, lower:::no-loc(case):::_a, other;
   char c;
   upper:::no-loc(case):::_A = lower:::no-loc(case):::_a = other = 0;

   :::no-loc(while)::: ( c = *buffer++ )   // Walks buffer until NULL
   {
      :::no-loc(switch)::: ( c )
      {
         :::no-loc(case)::: 'A':
            upper:::no-loc(case):::_A++;
            :::no-loc(break):::;
         :::no-loc(case)::: 'a':
            lower:::no-loc(case):::_a++;
            :::no-loc(break):::;
         :::no-loc(default)::::
            other++;
      }
   }
   printf_s( "\nUpper:::no-loc(case)::: A: %d\nLower:::no-loc(case)::: a: %d\nTotal: %d\n",
      upper:::no-loc(case):::_A, lower:::no-loc(case):::_a, (upper:::no-loc(case):::_A + lower:::no-loc(case):::_a + other) );
}
```

Yukarıdaki örnekte, `upper:::no-loc(case):::_A` `c` bir üst ise artırılır :::no-loc(case)::: `'A'` . **`:::no-loc(break):::`** After ifadesinin deyimin `upper:::no-loc(case):::_A++` ve denetimin yürütülmesi sona erer **`:::no-loc(switch):::`** **`:::no-loc(while):::`** . **`:::no-loc(break):::`** Bu ifade olmadan, yürütme bir sonraki etiketli ifadeye "geçer" `lower:::no-loc(case):::_a` ve `other` Ayrıca arttırılır. Benzer bir amaç, **`:::no-loc(break):::`** için ifadesiyle sunulur `:::no-loc(case)::: 'a'` . `c`Daha düşükse :::no-loc(case)::: `'a'` , `lower:::no-loc(case):::_a` artırılır ve **`:::no-loc(break):::`** ifade **`:::no-loc(switch):::`** gövde gövdesini sonlandırır. `c` `'a'` Veya değilse `'A'` , **`:::no-loc(default):::`** ifade yürütülür.

**Visual Studio 2017 ve üzeri:** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)Ile kullanılabilir) `[[fallthrough]]` özniteliği c++ 17 standardında belirtilir. Bunu bir **`:::no-loc(switch):::`** bildirimde kullanabilirsiniz. Derleyici veya kodu okuyan herkese yönelik bir ipucu, bu yana gelen davranış bilerek yapılır. Microsoft C++ derleyicisi Şu anda fallthrough davranışında uyarı vermiyor, bu nedenle bu özniteliğin derleyici davranışı üzerinde hiçbir etkisi yoktur. Örnekte, öznitelik Sonlandırılmamış etiketli deyimin içindeki boş bir ifadeye uygulanır. Diğer bir deyişle, noktalı virgül gereklidir.

```cpp
int main()
{
    int n = 5;
    :::no-loc(switch)::: (n)
    {

    :::no-loc(case)::: 1:
        a();
        :::no-loc(break):::;
    :::no-loc(case)::: 2:
        b();
        d();
        [[fallthrough]]; // I meant to do this!
    :::no-loc(case)::: 3:
        c();
        :::no-loc(break):::;
    :::no-loc(default)::::
        d();
        :::no-loc(break):::;
    }

    return 0;
}
```

**Visual Studio 2017 sürüm 15,3 ve üzeri** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)ile kullanılabilir). Bir **`:::no-loc(switch):::`** ifadede *`init-statement`* , noktalı virgülle biten bir yan tümcesi olabilir. Kapsamı deyimin bloğu ile sınırlı olan bir değişkeni tanıtır ve başlatır **`:::no-loc(switch):::`** :

```cpp
    :::no-loc(switch)::: (Gadget gadget(args); auto s = gadget.get_status())
    {
    :::no-loc(case)::: status::good:
        gadget.zip();
        :::no-loc(break):::;
    :::no-loc(case)::: status::bad:
        throw BadGadget();
    };
```

Bir deyimin iç bloğu, **`:::no-loc(switch):::`** *erişilebilir*oldukları sürece başlatıcıları olan tanımlar içerebilir, diğer bir deyişle, tüm olası yürütme yolları tarafından atlanmaz. Bu bildirimler kullanılarak tanıtılan adların yerel kapsamı vardır. Örnek:

```cpp
// :::no-loc(switch):::_statement2.cpp
// C2360 expected
#include <iostream>
using namespace std;
int main(int argc, char *argv[])
{
    :::no-loc(switch):::( tolower( *argv[1] ) )
    {
        // Error. Unreachable declaration.
        char szChEntered[] = "Character entered was: ";

    :::no-loc(case)::: 'a' :
        {
        // Declaration of szChEntered OK. Local scope.
        char szChEntered[] = "Character entered was: ";
        cout << szChEntered << "a\n";
        }
        :::no-loc(break):::;

    :::no-loc(case)::: 'b' :
        // Value of szChEntered undefined.
        cout << szChEntered << "b\n";
        :::no-loc(break):::;

    :::no-loc(default)::::
        // Value of szChEntered undefined.
        cout << szChEntered << "neither a nor b\n";
        :::no-loc(break):::;
    }
}
```

Bir **`:::no-loc(switch):::`** ifade iç içe olabilir. İç içe geçmiş olduğunda **`:::no-loc(case):::`** veya **`:::no-loc(default):::`** etiketleri, **`:::no-loc(switch):::`** bunları kapsayan en yakın deyimle ilişkilendirir.

### <a name="microsoft-specific-behavior"></a>Microsoft 'a özgü davranış

Microsoft C++, **`:::no-loc(case):::`** bir deyimindeki değer sayısını sınırlamaz **`:::no-loc(switch):::`** . Numara yalnızca kullanılabilir bellekle sınırlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Seçim Deyimleri](../cpp/selection-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
