---
description: 'Daha fazla bilgi edinin: C++ sabit Ifadeleri'
title: C++ Sabit İfadeleri
ms.date: 11/04/2016
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
ms.openlocfilehash: 9b7ca098ee5e8c41c2910f41df2031ce7320a514
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253942"
---
# <a name="c-constant-expressions"></a>C++ Sabit İfadeleri

Değişmeyen *bir değer değişmez* . C++, bir nesnenin değiştirilme amacını ifade etmek ve bu amacı zorlamak için iki anahtar sözcük sağlar.

C++, şu bildirimleri için sabit ifadeler (bir sabiti değerlendiren ifadeler) gerektirir:

- Dizi sınırları

- Case deyimlerine yönelik seçiciler

- Bit alanı uzunluk belirtimi

- Sabit Listesi başlatıcıları

Sabit deyimlerde geçerli olan tek işlenenler şunlardır:

- Değişmez Değerler

- Sabit Listesi sabitleri

- Sabit ifadelerle başlatılan const olarak belirtilen değerler

- **`sizeof`** ifadelerde

İntegral olmayan sabitlerin sabit bir ifadede yasal olması için integral türlerine dönüştürülmesi gerekir (açıkça veya örtük olarak). Bu nedenle, aşağıdaki kod geçerlidir:

```cpp
const double Size = 11.0;
char chArray[(int)Size];
```

Tamsayı türlerine açık dönüştürmeler sabit ifadelerde geçerlidir; Tüm diğer türler ve türetilmiş türler, işleç için işlenen olarak kullanılması dışında geçersizdir **`sizeof`** .

Virgül işleci ve atama işleçleri sabit ifadelerde kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Ifade türleri](../cpp/types-of-expressions.md)
