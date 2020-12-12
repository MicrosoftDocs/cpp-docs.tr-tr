---
description: 'Daha fazla bilgi edinin: `switch` (C)'
title: switch  İfade (C)
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
ms.openlocfilehash: f6089505ac47c657e151a60d6061a79ee0fd3cb8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114448"
---
# <a name="no-locswitch-statement-c"></a>`switch` İfade (C)

**`switch`** Ve **`case`** deyimleri, karmaşık koşullu ve dallanma işlemlerini denetlemeye yardımcı olur. **`switch`** İfade, denetimi kendi gövdesi içindeki bir ifadeye aktarır.

## <a name="syntax"></a>Syntax

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`switch (`**&nbsp;*`expression`* &nbsp;**`)`**&nbsp;*`statement`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`case`**&nbsp;*`constant-expression`*&nbsp;**`:`**&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; **`default`**&nbsp;**`:`**&nbsp;*`statement`*

## <a name="remarks"></a>Açıklamalar

Bir **`switch`** ifade, denetimin *`labeled-statement`* değerine bağlı olarak deyimin gövdesinde bir öğesine aktarılmasına neden olur *`expression`* .

*`expression`* Ve değerlerinin *`constant-expression`* bir integral türü olmalıdır. *`constant-expression`* Derleme zamanında benzersiz bir sabit integral değeri olmalıdır.

Denetim **`case`** *`constant-expression`* değeri değeri ile eşleşen ifadeye geçer *`expression`* . **`switch`** İfade herhangi bir sayıda **`case`** örnek içerebilir. Ancak, *`constant-expression`* aynı **`switch`** deyimdeki iki değer aynı değere sahip olamaz. **`switch`** Ekstre gövdesinin yürütülmesi, eşleştirmeden veya sonra ilk deyimden başlar *`labeled-statement`* . Yürütme, gövdenin sonuna kadar veya bir **`break`** ifade denetimi gövdeden dışarı aktarana kadar devam eder.

**`switch`** Deyimin kullanımı genellikle şuna benzer bir şekilde görünür:

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

**`break`** Deyimdeki belirli bir etiketli deyimin işlenmesini sonlandırmak için, ifadesini kullanabilirsiniz **`switch`** . Deyimin sonuna dallandırır **`switch`** . Olmadan **`break`** , program bir sonraki etiketli ifadeye devam eder ve **`break`** deyim bir veya sonuna ulaşılana kadar deyimlerini yürütmektedir. Bu devamlılık bazı durumlarda istenebilir.

Değeri değerine **`default`** eşit değilse, ifade yürütülür **`case`** *`constant-expression`* *`expression`* . Hiçbir **`default`** deyim yoksa ve hiçbir **`case`** eşleşme bulunmazsa, gövdedeki deyimlerden hiçbiri **`switch`** yürütülmez. En fazla bir **`default`** ifade olabilir. **`default`** Deyimin sonunda olması gerekmez. Deyimin gövdesinde herhangi bir yerde görünebilir **`switch`** . **`case`** Or **`default`** etiketi yalnızca bir deyimin içinde yer alabilir **`switch`** .

Türü **`switch`** *`expression`* ve tamsayı olmalıdır **`case`** *`constant-expression`* . Her birinin değeri, **`case`** *`constant-expression`* ifade gövdesi içinde benzersiz olmalıdır.

**`case`** **`default`** Deyimin gövdesinin ve etiketleri, **`switch`** yalnızca yürütmenin deyimin gövdesinde başlayacağını belirleyen başlangıç testinde önemlidir. **`switch`** deyimler iç içe olabilir. Herhangi bir statik değişken, herhangi bir deyime yürütülmeden önce başlatılır **`switch`** .

> [!NOTE]
> Bildirimler, gövde oluşturan bileşik deyimin başlangıcında görünebilir **`switch`** , ancak bildirimlere dahil olan başlatmalar gerçekleştirilmez. **`switch`** İfade, denetimi, başlatma içeren satırları atlayarak gövde içindeki bir yürütülebilir ifadeye doğrudan aktarır.

Aşağıdaki örneklerde, **`switch`** deyimleri gösterilmektedir:

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

**`switch`** `c` `'A'` **`break`** Aşağıdakilerden önce hiçbir deyim göründüğünden, bu örnekteki gövdenin tüm üç deyimi öğesine eşitse yürütülür **`case`** . Yürütme denetimi ilk ifadeye ( `capital_a++;` ) aktarılır ve gövdenin geri kalanı boyunca devam eder. `c`Eşitse `'a'` `letter_a` ve `total` arttırılır. Yalnızca `total` eşit olmadığında artırılır `c` `'A'` `'a'` .

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

Bu örnekte, bir **`break`** ifade gövdenin her bir ifadesine uyar **`switch`** . **`break`** İfade, bir deyimden sonra deyimin gövdesinden çıkış zorlar. `i`-1 ' e eşitse, yalnızca `n` artırılır. **`break`** Aşağıdaki deyim, `n++;` yürütme denetiminin geri kalan deyimleri atlayarak deyim gövdesinin dışına geçmesini sağlar. Benzer şekilde, `i` 0 ' a eşitse, yalnızca `z` artırılır; `i` 1 ' e eşitse yalnızca `p` artırılır. **`break`** Denetim bileşik deyimin sonundaki gövdeden geçerken son ifade kesinlikle gerekli değildir. Tutarlılık için eklenmiştir.

Aşağıdaki örnekte gösterildiği gibi tek bir ifade birden çok **`case`** etiket taşıyabilir:

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

Bu örnekte, *sabit ifade* ve arasında herhangi bir harfe eşitse `'a'` `'f'` , `convert_hex` işlev çağrılır.

### <a name="microsoft-specific"></a>Microsoft'a özgü

Microsoft C, **`case`** bir deyimdeki değer sayısını sınırlamaz **`switch`** . Numara yalnızca kullanılabilir bellekle sınırlıdır. ANSI C **`case`** , bir bildirimde en az 257 etikete izin verilmesini gerektirir **`switch`** .

defaultMicrosoft C için, Microsoft uzantılarının etkin olması. Bu uzantıları devre dışı bırakmak için [/za](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneğini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[switch İfade (C++)](../cpp/switch-statement-cpp.md)
