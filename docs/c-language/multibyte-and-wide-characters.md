---
title: Çok baytlı ve geniş karakterler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- character data types [C]
- Unicode [C++], wide character set
- types [C], character
- characters [C++], wide
- international applications [C++], character display
- multibyte characters [C++]
- wide characters [C++]
- characters [C++], codes
- character codes [C++], wide
- character codes [C++], multibyte
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2522761389a7f97acf4157683f8fce19e94429d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100538"
---
# <a name="multibyte-and-wide-characters"></a>Birden Çok Baytlı ve Geniş Karakterler

Çok baytlı bir karakter, bir veya daha fazla bayt dizisinden oluşan bir karakterdir. Her bayt dizisi, genişletilmiş karakter kümesinde tek bir karakteri temsil eder. Çok baytlı karakterler Kanji gibi karakter kümelerinde kullanılır.

Geniş karakterler, her zaman 16 bit genişliğinde olan çok dilli karakter kodlarıdır. Karakter sabitlerinin türü `char`, geniş karakterlerin türü ise `wchar_t`'dir. Geniş karakterler her zaman sabit boyutta olduğu için geniş karakterlerin kullanılması uluslararası karakter kümeleriyle programlamayı basitleştirir.

`L"hello"` geniş karakter dize sabit değeri, `wchar_t` türünden altı tamsayı dizisi haline gelir.

```
{L'h', L'e', L'l', L'l', L'o', 0}
```

Unicode belirtimi, geniş karakterlere yönelik belirtimdir. Çok baytlı ve geniş karakterler arasında çeviriye yönelik çalışma zamanı kitaplık yordamları arasında `mbstowcs`, `mbtowc`, `wcstombs` ve `wctomb` bulunur.

## <a name="see-also"></a>Ayrıca Bkz.

[C Tanımlayıcıları](../c-language/c-identifiers.md)