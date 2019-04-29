---
title: C Tanımlayıcıları
ms.date: 11/04/2016
helpviewer_keywords:
- identifiers, C
- naming identifiers
- identifiers
- symbols, C identifiers
- identifiers, case sensitivity
- symbols, case sensitivity
ms.assetid: d02edbbc-85a0-4118-997b-84ee6b972eb6
ms.openlocfilehash: 1f3abf304e6fda52e2571d0bccb8d4db5a414dfe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325669"
---
# <a name="c-identifiers"></a>C Tanımlayıcıları

"Tanımlayıcı" veya "simge" sağladığınız değişkenleri, türleri, işlevleri ve etiketleri programınızdaki adlarıdır. Yazım denetimi ve her anahtar sözcük çalışmasından tanımlayıcı adları farklı olmalıdır. Anahtar sözcükleri (C ya da Microsoft), tanımlayıcı olarak kullanamayacağınız; Bunlar, özel kullanım için ayrılmıştır. Bir tanımlayıcı, bir değişken, tür veya işlev bildiriminde belirterek oluşturun. Bu örnekte, `result` bir tam sayı değişkeni için bir tanımlayıcı ve `main` ve `printf` işlevleri için tanımlayıcı adları.

```
#include <stdio.h>

int main()
{
    int result;

    if ( result != 0 )
        printf_s( "Bad file handle\n" );
}
```

Bildirilen sonra sonraki program deyimlerinde tanımlayıcı ilişkili değerine başvurmak için kullanabilirsiniz.

Özel bir tür tanımlayıcı bir deyimi etiket adında, kullanılabilir `goto` deyimleri. (Bildirimleri açıklanmıştır [bildirimler ve türler](../c-language/declarations-and-types.md) deyim etiketleri açıklanmıştır [goto ve etiketli deyimleri](../c-language/goto-and-labeled-statements-c.md).)

## <a name="syntax"></a>Sözdizimi

*tanımlayıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*rakam*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *rakam*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *basamak*

*rakam*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ b c d e f g h miyim j k l mn o p q r s t u v z y x w**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**BİR B C D E F G H MİYİM J K L MN O P Q R S T U V W X, Y, Z**

*basamak*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

Bir tanımlayıcı adının ilk karakter bir `nondigit` (diğer bir deyişle, ilk karakteri bir alt çizgi veya bir büyük harf veya küçük harf olması gerekir). Dış bir tanımlayıcının adı altı önemli karakterler ve 31 adları (bir işlevde) iç tanımlayıcılar için ANSI sağlar. Dış tanımlayıcıları (olanları genel kapsamda bildirilen veya depolama sınıfı ile bildirilen `extern`) bu tanımlayıcıları linkers gibi diğer yazılımlar tarafından işlenmek üzere olduğundan ek adlandırma sınırlamalara tabi olabilir.

**Microsoft'a özgü**

Dış tanımlayıcı adları önemli 6 karakter ve 31 adları (bir işlevde) iç tanımlayıcılar için ANSI izin verir, ancak Microsoft C derleyicisi bir iç veya dış tanımlayıcı adı 247 karakter sağlar. ANSI uyumluluğu ile ilgili değilse, bu varsayılan /H kullanarak küçük veya büyük bir sayı olarak değiştirebilirsiniz (Dış adların uzunluğunu kısıtla) seçeneği.

**END Microsoft özgü**

C derleyicisi karakter farklı olacak şekilde büyük ve küçük harfler göz önünde bulundurur. "Küçük harf duyarlılığını," olarak adlandırılan bu özellik aynı benzersiz tanımlayıcıları oluşturmanıza olanak sağlar ancak farklı durumlarda, bir veya daha fazla harf için yazım denetimi. Örneğin, her biri aşağıdaki tanımlayıcıların benzersiz şöyledir:

```
add
ADD
Add
aDD
```

**Microsoft'a özgü**

İki alt çizgi veya alt çizginin tarafından bir büyük harf ile başlayan tanımlayıcı adları seçmeyin. ANSI C standardı, derleyici kullanımı için ayrılmış olması için bu bileşimler ile başlayan tanımlayıcı adları sağlar. Dosya düzeyinde kapsamlı tanımlayıcıları da alt çizgi ve bir küçük harf ile ilk iki harf adlandırılmalıdır değil. Ayrıca, bu karakterlerle başlayan tanımlayıcı adları ayrılmıştır. Kural gereği, Microsoft makro adları ve Microsoft'a özgü anahtar adları için çift alt çizgi başlamak için bir alt çizgi ve bir büyük harf kullanır. Adlandırma çakışmaları önlemek için bir veya iki alt çizgi ile başlamayan tanımlayıcı adları veya alt çizginin bir büyük harf ile başlayan bir ada her zaman seçin.

**END Microsoft özgü**

ANSI ya da Microsoft adlandırma kısıtlamaları için uygun geçerli tanımlayıcıları örnekleri şunlardır:

```
j
count
temp1
top_of_page
skip12
LastNum
```

**Microsoft'a özgü**

Kaynak dosyalarında tanımlayıcıları varsayılan olarak büyük küçük harfe duyarlı olsa da, nesne dosyalarında sembol değildir. Microsoft C, bir derleme biriminde içindeki tanımlayıcıları büyük küçük harfe duyarlı olarak değerlendirir.

Microsoft bağlayıcı büyük/küçük harfe duyarlıdır. Tüm tanımlayıcılar çalışması göre tutarlı bir şekilde belirtmeniz gerekir.

"Kaynak karakter kümesi" kaynak dosyalarında görünebilen geçerli karakterler kümesidir. Microsoft C için standart ASCII karakter kümesi kaynak kümesidir. ASCII karakterleri kaçış dizileri kullanılan kaynak karakter kümesi ve yürütme karakter kümesi içerir. Bkz: [karakter sabitleri](../c-language/c-character-constants.md) yürütme karakter hakkında bilgi için ayarlayın.

**END Microsoft özgü**

Bir tanımlayıcının "bölgesi, programın adı verilir ve"başka bir kapsamda aynı ada için aynı tanımlayıcıyı belirtir olup olmadığını belirleyen bağlantı,"kapsamı," vardır. Bu konularda açıklandığı [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md).

## <a name="see-also"></a>Ayrıca bkz.

[C Öğeleri](../c-language/elements-of-c.md)
