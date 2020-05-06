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

"Tanımlayıcılar" veya "semboller", programınızdaki değişkenler, türler, işlevler ve Etiketler için sağladığınız adlardır. Tanımlayıcı adları, herhangi bir anahtar kelimelerden farklı yazımla ve büyük/küçük harflere Tanımlayıcılar olarak anahtar sözcükler (C veya Microsoft) kullanamazsınız; özel kullanım için ayrılmıştır. Bir tanımlayıcıyı, bir değişken, tür veya işlev bildiriminde belirterek oluşturabilirsiniz. Bu örnekte, `result` bir tamsayı değişkeni `main` için bir tanımlayıcıdır ve işlevleri için tanımlayıcı `printf` isimleridir.

```
#include <stdio.h>

int main()
{
    int result;

    if ( result != 0 )
        printf_s( "Bad file handle\n" );
}
```

Bildirdikten sonra, sonraki program deyimleriyle ilgili tanımlayıcıyı kullanarak ilişkili değere başvurabilirsiniz.

Deyim etiketi olarak adlandırılan özel bir tür tanımlayıcı, `goto` ifadelerde kullanılabilir. (Bildirimler Bildirimler bölümünde açıklanmış [ve türler](../c-language/declarations-and-types.md) deyim etiketleri [goto ve etiketli deyimlerde](../c-language/goto-and-labeled-statements-c.md)açıklanmıştır.)

## <a name="syntax"></a>Sözdizimi

*tanımlayıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*rakam olmayan*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *basamak olmayan*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*tanımlayıcı* *sayısı*

*basamak olmayan*: biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**_ a b c d e f g h i j k l r s u p**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**A B C D E F G H I J K L R S U P Q S T**

*basamak*: aşağıdakilerden biri<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

Bir tanımlayıcı adının ilk karakteri bir `nondigit` olmalıdır (yani, ilk karakter bir alt çizgi veya büyük harf veya küçük harf olmalıdır). ANSI, dış tanımlayıcı adının ve 31 ' in iç (bir işlev içinde) tanımlayıcılarında altı önemli karaktere izin verir. Dış tanımlayıcılar (genel kapsamda belirtilen veya depolama sınıfıyla `extern`tanımlanmış olanlar), bu tanımlayıcıların Linler gibi başka yazılımlar tarafından işlenmesi gerektiğinden ek adlandırma kısıtlamalarına tabi olabilir.

**Microsoft'a Özgü**

ANSI, dış tanımlayıcı adlarında 6 önemli karakter ve iç (bir işlev içinde) tanımlayıcıları için 31 kullanılmasına izin veriyorsa, Microsoft C derleyicisi iç veya dış tanımlayıcı adında 247 karakter sağlar. ANSI uyumluluğuyla İlgilenmeyeceğiniz takdirde,/H (dış adların uzunluğunu kısıtla) seçeneğini kullanarak bu varsayılan ayarı daha küçük veya daha büyük bir sayı olarak değiştirebilirsiniz.

**SON Microsoft 'a özgü**

C derleyicisi, büyük ve küçük harfleri birbirinden farklı karakterler olacak şekilde değerlendirir. "Büyük/küçük harf duyarlılığı" olarak adlandırılan bu özellik, bir veya daha fazla harf için aynı yazım, ancak farklı servis taleplerine sahip farklı tanımlayıcılar oluşturmanıza olanak sağlar. Örneğin, aşağıdaki tanımlayıcıların her biri benzersizdir:

```
add
ADD
Add
aDD
```

**Microsoft'a Özgü**

İki alt çizgi ile başlayan veya ardından büyük harfle izlenen tanımlayıcıların adlarını seçmeyin. ANSI C standardı, bu karakter birleşimleriyle başlayan tanımlayıcı adlarının derleyici kullanımı için ayrılması için izin verir. Dosya düzeyi kapsama sahip tanımlayıcılar, ilk iki harf olarak bir alt çizgi ve küçük harf olarak adlandırılmalıdır. Bu karakterlerle başlayan tanımlayıcı adları da ayrılır. Kurala göre, Microsoft, makro adlarına başlamak için bir alt çizgi ve büyük harf, Microsoft 'a özgü anahtar sözcük adları için de çift alt çizgi kullanır. Herhangi bir adlandırma çakışmasını önlemek için, her zaman bir veya iki alt çizgiyle başlamayan tanımlayıcı adlarını veya alt çizgi ile başlayıp büyük harfle başlayan adları seçin.

**SON Microsoft 'a özgü**

Aşağıda, ANSI veya Microsoft adlandırma kısıtlamalarına uyan geçerli tanımlayıcıların örnekleri verilmiştir:

```
j
count
temp1
top_of_page
skip12
LastNum
```

**Microsoft'a Özgü**

Kaynak dosyalardaki tanımlayıcılar varsayılan olarak büyük/küçük harfe duyarlı olsa da, nesne dosyalarındaki semboller değildir. Microsoft C, derleme birimi içindeki tanımlayıcıları büyük/küçük harfe duyarlı olarak değerlendirir.

Microsoft Bağlayıcısı büyük/küçük harfe duyarlıdır. Tüm tanımlayıcıları büyük/küçük harfe göre tutarlı bir şekilde belirtmeniz gerekir.

"Kaynak karakter kümesi", kaynak dosyalarda görünebilen yasal karakter kümesidir. Microsoft C için, kaynak kümesi standart ASCII karakter kümesidir. Kaynak karakter kümesi ve yürütme karakter kümesi, kaçış dizileri olarak kullanılan ASCII karakterlerini içerir. Yürütme karakter kümesi hakkında bilgi için bkz. [karakter sabitleri](../c-language/c-character-constants.md) .

**SON Microsoft 'a özgü**

Bir tanımlayıcı, bilinen programın bölgesi olan "kapsam" ve başka bir kapsamdaki aynı adın aynı tanımlayıcıya başvuruda bulunup olmadığını belirleyen "bağlantı" anlamına gelir. Bu konular [ömür, kapsam, görünürlük ve bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)konularında açıklanmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[C Öğeleri](../c-language/elements-of-c.md)
