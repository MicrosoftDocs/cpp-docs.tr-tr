---
description: 'Daha fazla bilgi edinin: karakter türleri'
title: Karakter Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
ms.openlocfilehash: 270c1831422d81fe88519a2aee3de8306727d0d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293540"
---
# <a name="character-types"></a>Karakter Türleri

Önünde **L** harfinin türünde olan bir tamsayı karakter sabiti türü **`int`** . Tek bir karakter içeren bir tamsayı karakter sabiti değeri, tamsayı olarak yorumlanan karakterin sayısal değeridir. Örneğin, karakterin sayısal değeri `a` 97 ' dir ve onaltılı olarak 61 ' dir.

Sözdizimi, "geniş karakter sabiti", **L** harfinin önekli bir karakter sabiti. Geniş karakterli bir sabit türünde **`wchar_t`** , STDDEF içinde tanımlanan bir tamsayı türü vardır. H üstbilgi dosyası. Örneğin:

```
char    schar =  'x';   /* A character constant          */
wchar_t wchar = L'x';   /* A wide-character constant for
                            the same character           */
```

Geniş karakter sabitleri 16 bit geniştir ve genişletilmiş yürütme karakter kümesinin üyelerini belirtir. Bunlar, tür tarafından gösterilemeyecek kadar büyük olan harflerden oluşan karakterleri ifade etmeniz için izin verir **`char`** . Geniş karakterler hakkında daha fazla bilgi için bkz. [çok baytlı ve geniş karakterler](../c-language/multibyte-and-wide-characters.md) .

## <a name="see-also"></a>Ayrıca bkz.

[C karakter sabitleri](../c-language/c-character-constants.md)
