---
description: 'Daha fazla bilgi edinin: dize sabit değeri birleştirme'
title: Dize Değişmez Değeri Birleştirmesi
ms.date: 11/04/2016
helpviewer_keywords:
- concatenating strings
- strings [C++], concatenating
ms.assetid: 51486b1f-4b1e-4061-9add-1aa38c6cdb3c
ms.openlocfilehash: 3486857cb0d218ea80c00252de02d9f29d58f2c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137299"
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

Bir dize sabit değeri içinde yeni bir satırı zorlamak için, satırın üzerine kopmasını istediğiniz yere aşağıdaki gibi yeni bir satır kaçış sırası (**\n**) girin:

```
"Enter a number between 1 and 100\nOr press Return"
```

Dizeler kaynak kodunun herhangi bir sütununda başlayabileceği ve uzun dizeler sonraki satırın herhangi bir sütununda devam edebileceği için dizeleri kaynak kodunun okunabilirliğini artıracak şekilde konumlandırabilirsiniz. Her iki durumda da, çıktı sırasındaki ekran gösterimleri etkilenmez. Örneğin:

```
printf_s ( "This is the first half of the string, "
           "this is the second half ") ;
```

Dizenin her bölümü çift tırnak işareti içine alındığı sürece, bölümler bitiştirilir ve tek bir dize olarak çıkarılır. Bu birleştirme, [Çeviri aşamaları](../preprocessor/phases-of-translation.md)tarafından belirtilen derleme sırasında olay dizisine göre oluşur.

```
"This is the first half of the string, this is the second half"
```

Yalnızca boşluk ile ayrılmış iki farklı dize değişmez değeri olarak başlatılan bir dize işaretçisi, tek bir dize olarak saklanır (işaretçiler [Işaretçi bildirimlerinde](../c-language/pointer-declarations.md)açıklanmaktadır). Aşağıdaki örnekte olduğu gibi düzgün bir şekilde başvurulduğunda, sonuç önceki örnekle aynı olur:

```
char *string = "This is the first half of the string, "
               "this is the second half";

printf_s( "%s" , string ) ;
```

6. çeviri aşamasında, bitişik dize sabit değerlerinin veya bitişik geniş dize sabit değerlerinin herhangi bir dizisi tarafından belirtilen çok baytlı karakter dizileri, tek çok baytlı karakter dizisi olarak bitiştirilir. Bu nedenle, programları yürütme sırasında dize sabit değerlerinin değiştirilmesine izin verilecek şekilde tasarlamayın. ANSI C standardı, bir dize değiştirme işleminin sonucunun tanımlanmamış olduğunu belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[C dize değişmez değerleri](../c-language/c-string-literals.md)
