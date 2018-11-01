---
title: Dize Değişmez Değeri Birleştirmesi
ms.date: 11/04/2016
helpviewer_keywords:
- concatenating strings
- strings [C++], concatenating
ms.assetid: 51486b1f-4b1e-4061-9add-1aa38c6cdb3c
ms.openlocfilehash: 167ebd2cf9f7f8f2f073b5de68f36aebd1a3951a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654508"
---
# <a name="string-literal-concatenation"></a>Dize Değişmez Değeri Birleştirmesi

Bir satırdan fazla olan dize sabit değerleri oluşturmak için iki dizeyi bitiştirebilirsiniz. Bunu yapmak için ters eğik çizgi yazın, ardından RETURN tuşuna basın. Ters eğik çizgi, derleyicinin sonraki yeni satır karakterini yoksaymasına neden olur. Örneğin, dize sabit değeri

```
"Long strings can be bro\
ken into two or more pieces."
```

şu dizeyle aynıdır:

```
"Long strings can be broken into two or more pieces."
```

Dize bitiştirme, bir satırdan daha uzun dizeler girmek için ters eğik çizginin ardından yeni satır karakteri kullandığınız her yerde kullanılabilir.

Değişmez değer bir dize içinde yeni bir satırı zorlamak için yeni satır kaçış dizisini girin (**\n**) gibi kopuk satırı istediğiniz dizedeki bir noktada:

```
"Enter a number between 1 and 100\nOr press Return"
```

Dizeler kaynak kodunun herhangi bir sütununda başlayabileceği ve uzun dizeler sonraki satırın herhangi bir sütununda devam edebileceği için dizeleri kaynak kodunun okunabilirliğini artıracak şekilde konumlandırabilirsiniz. Her iki durumda da, çıktı sırasındaki ekran gösterimleri etkilenmez. Örneğin:

```
printf_s ( "This is the first half of the string, "
           "this is the second half ") ;
```

Dizenin her bölümü çift tırnak işareti içine alındığı sürece, bölümler bitiştirilir ve tek bir dize olarak çıkarılır. Bu birleştirme derleme tarafından belirtilen olay dizisine göre sistemdeki [çeviri aşamaları](../preprocessor/phases-of-translation.md).

```
"This is the first half of the string, this is the second half"
```

Yalnızca beyaz boşluk ile ayrılan iki farklı dize sabit değeri olarak başlatılan bir dize işaretçisi, tek bir dize olarak depolanır (işaretçiler açıklanmıştır [işaretçi bildirimleri](../c-language/pointer-declarations.md)). Aşağıdaki örnekte olduğu gibi düzgün bir şekilde başvurulduğunda, sonuç önceki örnekle aynı olur:

```
char *string = "This is the first half of the string, "
               "this is the second half";

printf_s( "%s" , string ) ;
```

6. çeviri aşamasında, bitişik dize sabit değerlerinin veya bitişik geniş dize sabit değerlerinin herhangi bir dizisi tarafından belirtilen çok baytlı karakter dizileri, tek çok baytlı karakter dizisi olarak bitiştirilir. Bu nedenle, programları yürütme sırasında dize sabit değerlerinin değiştirilmesine izin verilecek şekilde tasarlamayın. ANSI C standardı, bir dize değiştirme işleminin sonucunun tanımlanmamış olduğunu belirtir.

## <a name="see-also"></a>Ayrıca Bkz.

[C Dize Değişmez Değerleri](../c-language/c-string-literals.md)