---
title: :::no-loc(switch):::İfade (C)
ms.date: 04/25/2020
f1_keywords:
- ':::no-loc(switch):::'
helpviewer_keywords:
- ':::no-loc(switch)::: keyword [C]'
ms.assetid: fbede014-23bd-4ab1-8094-c8d9d9cb963a
no-loc:
- ':::no-loc(switch):::'
- ':::no-loc(case):::'
- ':::no-loc(default):::'
- ':::no-loc(break):::'
ms.openlocfilehash: bdd6885f67728a3c81e395f05c33191156896ad9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220788"
---
# <a name="no-locswitch-statement-c"></a>`:::no-loc(switch):::`İfade (C)

**`:::no-loc(switch):::`** Ve **`:::no-loc(case):::`** deyimleri, karmaşık koşullu ve dallanma işlemlerini denetlemeye yardımcı olur. **`:::no-loc(switch):::`** İfade, denetimi kendi gövdesi içindeki bir ifadeye aktarır.

## <a name="syntax"></a>Sözdizimi

> *`selection-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(switch)::: (`**&nbsp;*`expression`* &nbsp;**`)`**&nbsp;*`statement`*

> *`labeled-statement`*:\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(case):::`**&nbsp;*`constant-expression`*&nbsp;**`:`**&nbsp;*`statement`*\
> &nbsp;&nbsp;&nbsp;&nbsp; **`:::no-loc(default):::`**&nbsp;**`:`**&nbsp;*`statement`*

## <a name="remarks"></a>Açıklamalar

Bir **`:::no-loc(switch):::`** ifade, denetimin *`labeled-statement`* değerine bağlı olarak deyimin gövdesinde bir öğesine aktarılmasına neden olur *`expression`* .

*`expression`* Ve değerlerinin *`constant-expression`* bir integral türü olmalıdır. *`constant-expression`* Derleme zamanında benzersiz bir sabit integral değeri olmalıdır.

Denetim **`:::no-loc(case):::`** *`constant-expression`* değeri değeri ile eşleşen ifadeye geçer *`expression`* . **`:::no-loc(switch):::`** İfade herhangi bir sayıda **`:::no-loc(case):::`** örnek içerebilir. Ancak, *`constant-expression`* aynı **`:::no-loc(switch):::`** deyimdeki iki değer aynı değere sahip olamaz. **`:::no-loc(switch):::`** Ekstre gövdesinin yürütülmesi, eşleştirmeden veya sonra ilk deyimden başlar *`labeled-statement`* . Yürütme, gövdenin sonuna kadar veya bir **`:::no-loc(break):::`** ifade denetimi gövdeden dışarı aktarana kadar devam eder.

**`:::no-loc(switch):::`** Deyimin kullanımı genellikle şuna benzer bir şekilde görünür:

```C
:::no-loc(switch)::: ( expression )
{
    // declarations
    // . . .
    :::no-loc(case)::: constant_expression:
        // statements executed if the expression equals the
        // value of this constant_expression
        :::no-loc(break):::;
    :::no-loc(default)::::
        // statements executed if expression does not equal
        // any :::no-loc(case)::: constant_expression
}
```

**`:::no-loc(break):::`** Deyimdeki belirli bir etiketli deyimin işlenmesini sonlandırmak için, ifadesini kullanabilirsiniz **`:::no-loc(switch):::`** . Deyimin sonuna dallandırır **`:::no-loc(switch):::`** . Olmadan **`:::no-loc(break):::`** , program bir sonraki etiketli ifadeye devam eder ve **`:::no-loc(break):::`** deyim bir veya sonuna ulaşılana kadar deyimlerini yürütmektedir. Bu devamlılık bazı durumlarda istenebilir.

Değeri değerine **`:::no-loc(default):::`** eşit değilse, ifade yürütülür **`:::no-loc(case):::`** *`constant-expression`* *`expression`* . Hiçbir **`:::no-loc(default):::`** deyim yoksa ve hiçbir **`:::no-loc(case):::`** eşleşme bulunmazsa, gövdedeki deyimlerden hiçbiri **`:::no-loc(switch):::`** yürütülmez. En fazla bir **`:::no-loc(default):::`** ifade olabilir. **`:::no-loc(default):::`** Deyimin sonunda olması gerekmez. Deyimin gövdesinde herhangi bir yerde görünebilir **`:::no-loc(switch):::`** . **`:::no-loc(case):::`** Or **`:::no-loc(default):::`** etiketi yalnızca bir deyimin içinde yer alabilir **`:::no-loc(switch):::`** .

Türü **`:::no-loc(switch):::`** *`expression`* ve tamsayı olmalıdır **`:::no-loc(case):::`** *`constant-expression`* . Her birinin değeri, **`:::no-loc(case):::`** *`constant-expression`* ifade gövdesi içinde benzersiz olmalıdır.

**`:::no-loc(case):::`** **`:::no-loc(default):::`** Deyimin gövdesinin ve etiketleri, **`:::no-loc(switch):::`** yalnızca yürütmenin deyimin gövdesinde başlayacağını belirleyen başlangıç testinde önemlidir. **`:::no-loc(switch):::`** deyimler iç içe olabilir. Herhangi bir statik değişken, herhangi bir deyime yürütülmeden önce başlatılır **`:::no-loc(switch):::`** .

> [!NOTE]
> Bildirimler, gövde oluşturan bileşik deyimin başlangıcında görünebilir **`:::no-loc(switch):::`** , ancak bildirimlere dahil olan başlatmalar gerçekleştirilmez. **`:::no-loc(switch):::`** İfade, denetimi, başlatma içeren satırları atlayarak gövde içindeki bir yürütülebilir ifadeye doğrudan aktarır.

Aşağıdaki örneklerde, **`:::no-loc(switch):::`** deyimleri gösterilmektedir:

```C
:::no-loc(switch):::( c )
{
    :::no-loc(case)::: 'A':
        capital_a++;
    :::no-loc(case)::: 'a':
        letter_a++;
    :::no-loc(default)::: :
        total++;
}
```

**`:::no-loc(switch):::`** `c` `'A'` **`:::no-loc(break):::`** Aşağıdakilerden önce hiçbir deyim göründüğünden, bu örnekteki gövdenin tüm üç deyimi öğesine eşitse yürütülür **`:::no-loc(case):::`** . Yürütme denetimi ilk ifadeye ( `capital_a++;` ) aktarılır ve gövdenin geri kalanı boyunca devam eder. `c`Eşitse `'a'` `letter_a` ve `total` arttırılır. Yalnızca `total` eşit olmadığında artırılır `c` `'A'` `'a'` .

```C
:::no-loc(switch):::( i )
{
    :::no-loc(case)::: -1:
        n++;
        :::no-loc(break):::;
    :::no-loc(case)::: 0 :
        z++;
        :::no-loc(break):::;
    :::no-loc(case)::: 1 :
        p++;
        :::no-loc(break):::;
}
```

Bu örnekte, bir **`:::no-loc(break):::`** ifade gövdenin her bir ifadesine uyar **`:::no-loc(switch):::`** . **`:::no-loc(break):::`** İfade, bir deyimden sonra deyimin gövdesinden çıkış zorlar. `i`-1 ' e eşitse, yalnızca `n` artırılır. **`:::no-loc(break):::`** Aşağıdaki deyim, `n++;` yürütme denetiminin geri kalan deyimleri atlayarak deyim gövdesinin dışına geçmesini sağlar. Benzer şekilde, `i` 0 ' a eşitse, yalnızca `z` artırılır; `i` 1 ' e eşitse yalnızca `p` artırılır. **`:::no-loc(break):::`** Denetim bileşik deyimin sonundaki gövdeden geçerken son ifade kesinlikle gerekli değildir. Tutarlılık için eklenmiştir.

Aşağıdaki örnekte gösterildiği gibi tek bir ifade birden çok **`:::no-loc(case):::`** etiket taşıyabilir:

```C
:::no-loc(switch):::( c )
{
    :::no-loc(case)::: 'a' :
    :::no-loc(case)::: 'b' :
    :::no-loc(case)::: 'c' :
    :::no-loc(case)::: 'd' :
    :::no-loc(case)::: 'e' :
    :::no-loc(case)::: 'f' :  convert_hex(c);
}
```

Bu örnekte, *sabit ifade* ve arasında herhangi bir harfe eşitse `'a'` `'f'` , `convert_hex` işlev çağrılır.

### <a name="microsoft-specific"></a>Microsoft'a özgü

Microsoft C, **`:::no-loc(case):::`** bir deyimdeki değer sayısını sınırlamaz **`:::no-loc(switch):::`** . Numara yalnızca kullanılabilir bellekle sınırlıdır. ANSI C **`:::no-loc(case):::`** , bir bildirimde en az 257 etikete izin verilmesini gerektirir **`:::no-loc(switch):::`** .

:::no-loc(default):::Microsoft C için, Microsoft uzantılarının etkin olması. Bu uzantıları devre dışı bırakmak için [/za](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneğini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[:::no-loc(switch):::İfade (C++)](../cpp/:::no-loc(switch):::-statement-cpp.md)
