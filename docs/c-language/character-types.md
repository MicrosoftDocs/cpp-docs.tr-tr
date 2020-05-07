---
title: Karakter Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
ms.openlocfilehash: f894114d4e980b11edf55c4d4b7c4e60af396fb1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312641"
---
# <a name="character-types"></a>Karakter Türleri

Önünde **L** harfinin türünde olan bir tamsayı karakter sabiti türü `int`. Tek bir karakter içeren bir tamsayı karakter sabiti değeri, tamsayı olarak yorumlanan karakterin sayısal değeridir. Örneğin, karakterin `a` sayısal değeri 97 ' dir ve onaltılı olarak 61 ' dir.

Sözdizimi, "geniş karakter sabiti", **L**harfinin önekli bir karakter sabiti. Geniş karakterli bir sabit türünde `wchar_t`, STDDEF içinde tanımlanan bir tamsayı türü vardır. H üstbilgi dosyası. Örneğin:

```
char    schar =  'x';   /* A character constant          */
wchar_t wchar = L'x';   /* A wide-character constant for
                            the same character           */
```

Geniş karakter sabitleri 16 bit geniştir ve genişletilmiş yürütme karakter kümesinin üyelerini belirtir. Bunlar, tür `char`tarafından gösterilemeyecek kadar büyük olan harflerden oluşan karakterleri ifade etmeniz için izin verir. Geniş karakterler hakkında daha fazla bilgi için bkz. [çok baytlı ve geniş karakterler](../c-language/multibyte-and-wide-characters.md) .

## <a name="see-also"></a>Ayrıca bkz.

[C Karakter Sabitleri](../c-language/c-character-constants.md)
