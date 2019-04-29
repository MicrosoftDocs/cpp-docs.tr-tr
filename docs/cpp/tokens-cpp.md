---
title: Tokens (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- tokens [C++]
- parsing, C++ tokens
- translation units
- white space, in C++ tokens
ms.assetid: aa812fd0-6d47-4f3f-aee0-db002ee4d8b9
ms.openlocfilehash: 1606df56191ec00ffea543dedd3fd4eda98d01c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330446"
---
# <a name="tokens-c"></a>Tokens (C++)

Bir belirteç C++ programının derleyicisi için anlamlı olan en küçük öğesidir. C++ ayrıştırıcısı şu tür belirteçleri tanır: Tanımlayıcılar, anahtar sözcükler, sabitler, işleçler, noktalayıcılar ve diğer ayıraçlar. Bu belirteçlerin akışı bir çeviri birimi oluşturur.

Belirteç tarafından ayrılmış genellikle *boşluk*. Bir veya daha fazla boşluk olabilir:

- Boşluklar

- Yatay veya dikey sekmeler

- Yeni satırlar

- Form beslemeleri

- Açıklamalar

Ayrıştırıcının, anahtar sözcükler, tanımlayıcılar, değişmez değerler, işleçler ve noktalama tanır. Belirli belirteç türleri hakkında daha fazla bilgi için bkz: [anahtar sözcükleri](../cpp/keywords-cpp.md), [tanımlayıcıları](../cpp/identifiers-cpp.md), [sayısal, Boole ve işaretçi değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md), [dize ve karakter değişmez değerleri ](../cpp/string-and-character-literals-cpp.md), [Kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md), [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md), ve [noktalama](../cpp/punctuators-cpp.md). Ayırmak için gerektiği gibi belirteçler dışında boşluk yoksayılır.

Ön işleme belirteçleri, ön işleme aşamalar için derleyici geçirilen belirteç akışı oluşturmak için kullanılır. Ön işleme belirteci kategoriler, üst bilgi adları, tanımlayıcılar, ön işleme numaraları, karakter değişmez değerleri, dize değişmez değerleri, ön işleme işleçleri ve noktalama işaretçileri ve diğer kategorilerden birini eşleşmeyen tek boşluk olmayan karakterle bulunur. Karakter ve dize değişmez değerleri, kullanıcı tanımlı değişmez değerler olabilir. Ön işleme belirteci boşluk veya açıklamaları ayrılabilir.

Ayrıştırıcı, soldan sağa taramada girdi karakterlerini kullanarak olası en uzun belirteci oluşturarak, belirteçleri girdi akışından ayırır. Bu kod parçasını göz önünde bulundurun:

```cpp
a = i+++j;
```

Kodu yazan programcı bu iki deyimden birini amaçlamış olabilir:

```cpp
a = i + (++j)

a = (i++) + j
```

Ayrıştırıcı girdi akışından olası en uzun belirteci oluşturduğundan, ikinci yorumu seçer ve `i++`, `+` ile `j` belirtecini yapar.

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)