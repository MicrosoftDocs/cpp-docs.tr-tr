---
title: Belirteçler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- tokens [C++]
- parsing, C++ tokens
- translation units
- white space, in C++ tokens
ms.assetid: aa812fd0-6d47-4f3f-aee0-db002ee4d8b9
ms.openlocfilehash: cd104b7308716ca182374bbff2df61731c84d574
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376259"
---
# <a name="tokens-c"></a>Belirteçler (C++)

Bir belirteç C++ programının derleyicisi için anlamlı olan en küçük öğesidir. C++ ayrıştırıcısı şu tür belirteçleri tanır: Tanımlayıcılar, anahtar sözcükler, sabitler, işleçler, noktalayıcılar ve diğer ayıraçlar. Bu belirteçlerin akışı bir çeviri birimi oluşturur.

Belirteçler genellikle *boşluk ile ayrılır*. Bir veya daha fazla boşluk olabilir:

- Boşluklar

- Yatay veya dikey sekmeler

- Yeni satırlar

- Form akışları

- Açıklamalar

Ayrıştırıcı, anahtar sözcükleri, tanımlayıcıları, değişmez değerleri, işleçleri ve noktacılarını tanır. Belirli belirteç türleri hakkında bilgi için bkz. [anahtar sözcükler](../cpp/keywords-cpp.md), [tanımlayıcılar](../cpp/identifiers-cpp.md), [sayısal, Boole ve işaretçi değişmez değerleri](../cpp/numeric-boolean-and-pointer-literals-cpp.md), [dize ve karakter değişmez değerleri](../cpp/string-and-character-literals-cpp.md), [Kullanıcı tanımlı sabit değerler](../cpp/user-defined-literals-cpp.md), [ C++ yerleşik işleçler, Öncelik ve Ilişkilendirilebilirlik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)ve [noktaleyiciler](../cpp/punctuators-cpp.md). Belirteçleri ayırmak için gerekli olanlar dışında boşluk yok sayılır.

Ön işleme belirteçleri, derleyiciye geçirilen belirteç akışını oluşturmak için ön işleme aşamalarda kullanılır. Ön işleme belirteç kategorileri başlık adları, tanımlayıcılar, ön işleme numaraları, karakter sabit değerleri, dize sabit değerleri, ön işleme işleçleri ve noktaleyiciler ve diğer kategorilerden biriyle eşleşmeyen tek boşluk olmayan karakterler. Karakter ve dize sabit değerleri Kullanıcı tanımlı değişmez değerler olabilir. Ön işleme belirteçleri, boşluk veya açıklamalarla ayrılabilir.

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