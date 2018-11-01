---
title: Karakter Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
ms.openlocfilehash: 7ca87ec1cb11f8a00beb6f5eb670b3e292bb1f70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619342"
---
# <a name="character-types"></a>Karakter Türleri

Harfinin öncesinde olmayan bir tamsayı karakter sabitinin **L** türünde `int`. Tek bir karakter içeren tamsayı karakter sabitinin değeri bir tamsayı olarak yorumlanır karakterin sayısal değerdir. Örneğin, karakterin sayısal değerini `a` 97 ondalık ve 61 onaltılık.

Sözdizimi, "geniş karakter sabiti" harfi ile önek olarak kullanılan bir karakter sabiti olduğunu **L**. Türü bir geniş karakter sabitinin `wchar_t`, STDDEF içinde tanımlanan bir tamsayı türü. H üst bilgi dosyası. Örneğin:

```
char    schar =  'x';   /* A character constant          */
wchar_t wchar = L'x';   /* A wide-character constant for
                            the same character           */
```

Geniş karakter sabitleri, 16 bit genişliğinde olan ve genişletilmiş yürütme karakter kümesi üyeleri belirtin. Karakter türüne göre gösterilemeyecek kadar çok büyük harfler express izin `char`. Bkz: [çok baytlı ve geniş karakterler](../c-language/multibyte-and-wide-characters.md) geniş karakterler hakkında daha fazla bilgi.

## <a name="see-also"></a>Ayrıca Bkz.

[C Karakter Sabitleri](../c-language/c-character-constants.md)