---
title: switchİfade (C)
ms.date: 04/25/2020
f1_keywords:
- switch
helpviewer_keywords:
- switch keyword [C]
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
no-loc:
- switch
- case
- default
- break
ms.openlocfilehash: 5858447602a28dcc5573aa3138e869d106b5aa23
ms.sourcegitcommit: 2f9ff2041d70c406df76c5053151192aad3937ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82587368"
---
# <a name="switch-statement-c"></a>`switch`İfade (C)

Ve __`switch`__ __`case`__ deyimleri, karmaşık koşullu ve dallanma işlemlerini denetlemeye yardımcı olur. İfade __`switch`__ , denetimi kendi gövdesi içindeki bir ifadeye aktarır.

## <a name="syntax"></a>Sözdizimi

> *`selection-statement`*:<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`switch (`__&nbsp;*`expression`* &nbsp;__`)`__&nbsp;*`statement`*

> *`labeled-statement`*:<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`case`__&nbsp;*`constant-expression`*&nbsp;__`:`__&nbsp;*`statement`*<br/>
> &nbsp;&nbsp;&nbsp;&nbsp; __`default`__&nbsp;__`:`__&nbsp;*`statement`*

## <a name="remarks"></a>Açıklamalar

Bir __`switch`__ ifade, denetimin değerine bağlı olarak deyimin *`labeled-statement`* gövdesinde bir öğesine aktarılmasına neden olur *`expression`*.

*`expression`* Ve değerlerinin bir integral türü *`constant-expression`* olmalıdır. Derleme *`constant-expression`* zamanında benzersiz bir sabit integral değeri olmalıdır.

Denetim **`case`** *`constant-expression`* değeri değeri ile eşleşen ifadeye geçer *`expression`*. __`switch`__ İfade herhangi bir sayıda __`case`__ örnek içerebilir. Ancak, aynı *`constant-expression`* __`switch`__ deyimdeki iki değer aynı değere sahip olamaz. __`switch`__ Ekstre gövdesinin yürütülmesi, eşleştirmeden *`labeled-statement`* veya sonra ilk deyimden başlar. Yürütme, gövdenin sonuna kadar veya bir __`break`__ ifade denetimi gövdeden dışarı aktarana kadar devam eder.

__`switch`__ Deyimin kullanımı genellikle şuna benzer bir şekilde görünür:

```C
switch ( expression )
{
    // declarations
    // . . .
    case constant_expression:
        // statements executed if the expression equals the
        // value of this constant_expression
        break;
    default:
        // statements executed if expression does not equal
        // any case constant_expression
}
```

Deyimdeki __`switch`__ belirli bir __`break`__ etiketli deyimin işlenmesini sonlandırmak için, ifadesini kullanabilirsiniz. __`switch`__ Deyimin sonuna dallandırır. Olmadan __`break`__, program bir sonraki etiketli ifadeye devam eder ve deyim bir __`break`__ veya sonuna ulaşılana kadar deyimlerini yürütmektedir. Bu devamlılık bazı durumlarda istenebilir.

Değeri __`default`__ değerine eşit değilse, ifade __`case`__ *`constant-expression`* yürütülür *`expression`*. Hiçbir __`default`__ deyim yoksa ve hiçbir __`case`__ eşleşme bulunmazsa, __`switch`__ gövdedeki deyimlerden hiçbiri yürütülmez. En fazla bir __`default`__ ifade olabilir. __`default`__ Deyimin sonunda olması gerekmez. __`switch`__ Deyimin gövdesinde herhangi bir yerde görünebilir. __`case`__ Or __`default`__ etiketi yalnızca bir __`switch`__ deyimin içinde yer alabilir.

Türü __`switch`__ *`expression`* __`case`__ ve *`constant-expression`* tamsayı olmalıdır. Her __`case`__ *`constant-expression`* birinin değeri, ifade gövdesi içinde benzersiz olmalıdır.

Deyimin gövdesinin __`default`__ ve etiketleri, __`case`__ yalnızca yürütmenin deyimin gövdesinde başlayacağını belirleyen başlangıç testinde önemlidir. __`switch`__ __`switch`__ deyimler iç içe olabilir. Herhangi bir statik değişken, herhangi bir __`switch`__ deyime yürütülmeden önce başlatılır.

> [!NOTE]
> Bildirimler, __`switch`__ gövde oluşturan bileşik deyimin başlangıcında görünebilir, ancak bildirimlere dahil olan başlatmalar gerçekleştirilmez. __`switch`__ İfade, denetimi, başlatma içeren satırları atlayarak gövde içindeki bir yürütülebilir ifadeye doğrudan aktarır.

Aşağıdaki örneklerde, deyimleri __`switch`__ gösterilmektedir:

```C
switch( c )
{
    case 'A':
        capital_a++;
    case 'a':
        letter_a++;
    default :
        total++;
}
```

__`switch`__ Aşağıdakilerden __`case`__ önce hiçbir __`break`__ deyim göründüğünden, bu örnekteki gövdenin tüm üç `c` deyimi öğesine `'A'`eşitse yürütülür. Yürütme denetimi ilk ifadeye (`capital_a++;`) aktarılır ve gövdenin geri kalanı boyunca devam eder. `c` `'a'`Eşitse `letter_a` ve `total` arttırılır. Yalnızca `total` eşit `c` `'A'` olmadığında artırılır `'a'`.

```C
switch( i )
{
    case -1:
        n++;
        break;
    case 0 :
        z++;
        break;
    case 1 :
        p++;
        break;
}
```

Bu örnekte, bir ifade __`break`__ __`switch`__ gövdenin her bir ifadesine uyar. __`break`__ İfade, bir deyimden sonra deyimin gövdesinden çıkış zorlar. `i` -1 ' e eşitse, yalnızca `n` artırılır. __`break`__ Aşağıdaki deyim `n++;` , yürütme denetiminin geri kalan deyimleri atlayarak deyim gövdesinin dışına geçmesini sağlar. `i` Benzer şekilde, 0 ' a eşitse, yalnızca `z` artırılır; `i` 1 ' e eşitse, yalnızca `p` artırılır. Denetim bileşik __`break`__ deyimin sonundaki gövdeden geçerken son ifade kesinlikle gerekli değildir. Tutarlılık için eklenmiştir.

Aşağıdaki örnekte gösterildiği gibi tek bir __`case`__ ifade birden çok etiket taşıyabilir:

```C
switch( c )
{
    case 'a' :
    case 'b' :
    case 'c' :
    case 'd' :
    case 'e' :
    case 'f' :  convert_hex(c);
}
```

Bu örnekte, *sabit ifade* ve `'a'` `'f'`arasında herhangi bir harfe eşitse, `convert_hex` işlev çağrılır.

### <a name="microsoft-specific"></a>Microsoft'a özgü

Microsoft C, bir __`case`__ __`switch`__ deyimdeki değer sayısını sınırlamaz. Numara yalnızca kullanılabilir bellekle sınırlıdır. ANSI C, bir __`case`__ __`switch`__ bildirimde en az 257 etikete izin verilmesini gerektirir.

Microsoft default C Için, Microsoft uzantılarının etkin olması. Bu uzantıları devre dışı bırakmak için [/za](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneğini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[switchİfade (C++)](../cpp/switch-statement-cpp.md)
