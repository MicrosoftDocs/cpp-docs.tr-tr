---
title: C++ Sabit İfadeleri
ms.date: 11/04/2016
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
ms.openlocfilehash: 32d14650450d8047a5bc0e6cf7bb06788c9b3d81
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221763"
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
