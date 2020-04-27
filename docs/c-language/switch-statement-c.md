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
ms.openlocfilehash: 12163e85110092e3e372fa496cf42efd7574ea8d
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167682"
---
# <a name="opno-locswitch-statement-c"></a>switchİfade (C)

Ve **switch** **case** deyimleri, karmaşık koşullu ve dallanma işlemlerini denetlemeye yardımcı olur. İfade **switch** , denetimi kendi gövdesi içindeki bir ifadeye aktarır.

## <a name="syntax"></a>Sözdizimi

*seçim-ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`switch (`***ifade* **`)`** *deyimi*

*etiketli ifade*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`case`**  *Sabit ifade*  **`:`**  *deyimi*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`default :`**  *Ekstre*

Denetim, **case** *sabit ifadesi* ** switch (** *ifade* **)** değeriyle eşleşen ifadeye geçer. **switch** İfade herhangi bir sayıda **case** örnek içerebilir. Ancak, aynı case **switch** deyimdeki iki sabit değer aynı değere sahip olamaz. Ekstre gövdesinin yürütülmesi seçili deyimden başlar. Gövde sonuna kadar veya bir **break** deyimin denetimi gövdeden dışarı aktarana kadar devam eder.

**switch** Deyimin kullanımı genellikle şuna benzer bir şekilde görünür:

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

Deyimdeki **switch** belirli bir **break** etiketli deyimin işlenmesini sonlandırmak için, ifadesini kullanabilirsiniz. **switch** Deyimin sonuna dallandırır. Olmadan **break**, program bir sonraki etiketli ifadeye devam eder ve deyim bir **break** veya sonuna ulaşılana kadar deyimlerini yürütmektedir. Bu devamlılık bazı durumlarda istenebilir.

**default** Deyim, ** switch (** *ifade* **)** değerine **case** eşit bir *sabit ifade* yoksa yürütülür. Hiçbir **default** deyim yoksa ve hiçbir **case** eşleşme bulunmazsa, **switch** gövdedeki deyimlerden hiçbiri yürütülmez. En fazla bir **default** ifade olabilir. **default** Deyimin sonunda olması gerekmez. **switch** Deyimin gövdesinde herhangi bir yerde görünebilir. **case** Or **default** etiketi yalnızca bir **switch** deyimin içinde yer alabilir.

**switch** *İfade* türü ve **case** *sabit ifadesinin* tamsayı olması gerekir. Her **case** *sabit ifadenin* değeri deyim gövdesi içinde benzersiz olmalıdır.

Deyimin gövdesinin **default** ve etiketleri, **case** yalnızca yürütmenin deyimin gövdesinde başlayacağını belirleyen başlangıç testinde önemlidir. **switch** **switch** deyimler iç içe olabilir. Herhangi bir statik değişken, herhangi bir **switch** deyime yürütülmeden önce başlatılır.

> [!NOTE]
> Bildirimler, **switch** gövde oluşturan bileşik deyimin başlangıcında görünebilir, ancak bildirimlere dahil olan başlatmalar gerçekleştirilmez. **switch** İfade, denetimi, başlatma içeren satırları atlayarak gövde içindeki bir yürütülebilir ifadeye doğrudan aktarır.

Aşağıdaki örneklerde, deyimleri **switch** gösterilmektedir:

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

**switch** Aşağıdakilerden caseönce hiçbir **break** deyim göründüğünden, bu örnekteki gövdenin tüm üç `c` deyimi öğesine `'A'`eşitse yürütülür. Yürütme denetimi ilk ifadeye (`capital_a++;`) aktarılır ve gövdenin geri kalanı boyunca devam eder. `c` `'a'`Eşitse `letter_a` ve `total` arttırılır. Yalnızca `total` eşit `c` `'A'` olmadığında artırılır `'a'`.

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

Bu örnekte, bir ifade **break** **switch** gövdenin her bir ifadesine uyar. **break** İfade, bir deyimden sonra deyimin gövdesinden çıkış zorlar. `i` -1 ' e eşitse, yalnızca `n` artırılır. **break** Aşağıdaki deyim `n++;` , yürütme denetiminin geri kalan deyimleri atlayarak deyim gövdesinin dışına geçmesini sağlar. `i` Benzer şekilde, 0 ' a eşitse, yalnızca `z` artırılır; `i` 1 ' e eşitse, yalnızca `p` artırılır. Denetim bileşik **break** deyimin sonundaki gövdeden geçerken son ifade kesinlikle gerekli değildir. Tutarlılık için eklenmiştir.

Aşağıdaki örnekte gösterildiği gibi tek bir **case** ifade birden çok etiket taşıyabilir:

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

Microsoft C, bir case **switch** deyimdeki değer sayısını sınırlamaz. Numara yalnızca kullanılabilir bellekle sınırlıdır. ANSI C, bir case **switch** bildirimde en az 257 etikete izin verilmesini gerektirir.

Microsoft default C Için, Microsoft uzantılarının etkin olması. Bu uzantıları devre dışı bırakmak için [/za](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneğini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[switchİfade (C++)](../cpp/switch-statement-cpp.md)
