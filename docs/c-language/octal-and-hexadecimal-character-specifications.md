---
title: Sekizlik ve Onaltılık Karakter Belirtimleri
ms.date: 11/04/2016
helpviewer_keywords:
- octal characters
- hexadecimal characters
ms.assetid: 9264f3ec-46b8-41a5-b21a-8f7ed0a11871
ms.openlocfilehash: bcd6eb84503b80b1e38be5d134e7506a0f490891
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229590"
---
# <a name="octal-and-hexadecimal-character-specifications"></a>Sekizlik ve Onaltılık Karakter Belirtimleri

**\\** <em>Ooo</em> sırası, ASCII karakter kümesinde üç basamaklı sekizli karakter kodu olarak herhangi bir karakter belirtebileceğiniz anlamına gelir. Sekizli tamsayının sayısal değeri, istediğiniz karakter veya geniş karakter değerini belirtir.

Benzer şekilde, **\x**<em>SSS</em> dizisi, herhangi bir ASCII karakterini onaltılık karakter kodu olarak belirtmenizi sağlar. Örneğin, ASCII geri al karakterini normal C kaçış sırası (**\b**) olarak verebilir veya bunu **\ 010** (sekizlik) veya **\x008** (onaltılı) olarak kodlayın.

Sekizli bir çıkış dizisinde yalnızca 0 ile 7 arasındaki sayıları kullanabilirsiniz. Sekizli çıkış dizileri, asla üç basamaktan uzun olamaz ve sekizlik bir rakam olmayan ilk karakterle sonlandırılır. Üç sayının tümünü kullanmanız gerekmese de, en az birini kullanmanız gerekir. Örneğin, bir ASCII grafiğinde verilen şekilde, sekizli gösterimi ASCII geri tuşu için **\ 10** ve A harfi için **\ 101** olur.

Benzer şekilde, onaltılı çıkış dizisi için en az bir sayı kullanmanız gerekir, ancak ikinci ve üçüncü sayıyı atlayabilirsiniz. Bu nedenle, geri al karakteri için, **\x8**, **\x08**veya **\x008**gibi onaltılı kaçış sırasını belirtebilirsiniz.

Sekizli veya onaltılı kaçış sırasının değeri, bir karakter sabiti türü için gösterilemeyen tablo değerleri aralığında olmalı **`unsigned char`** ve **`wchar_t`** geniş karakterli bir sabit için tür olmalıdır. Geniş karakter sabitleri hakkında bilgi için bkz. [çok baytlı ve geniş karakterler](../c-language/multibyte-and-wide-characters.md) .

Sekizli çıkış sabitlerinden farklı olarak, bir çıkış dizisinde bulunabilecek onaltılı basamaklar sınırsızdır. Onaltılı bir çıkış dizisi, onaltılı olmayan ilk karakterde sonlandırılır. Onaltılık basamaklar **a** - **f**arasındaki harfleri içerdiğinden, kaçış sırasının amaçlanan rakamla sonlandırdığından emin olmak için dikkatli olmanız gerekir. Karışıklığı önlemek için, bir makro tanımına sekizli veya onaltılı karakter tanımları koyabilirsiniz:

```
#define Bell '\x07'
```

Onaltılı değerler için, doğru değeri net şekilde göstermek üzere dize bölünebilir:

```
"\xabc"    /* one character  */
"\xab" "c" /* two characters */
```

## <a name="see-also"></a>Ayrıca bkz.

[C karakter sabitleri](../c-language/c-character-constants.md)
