---
title: C++ Sabit İfadeleri
ms.date: 11/04/2016
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
ms.openlocfilehash: d4d9803c7f80caba3c33d011e4df433491b9b591
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170585"
---
# <a name="c-constant-expressions"></a>C++ Sabit İfadeleri

Değişmeyen *bir değer değişmez* . C++, bir nesnenin değiştirilme amacını ifade etmek ve bu amacı zorlamak için iki anahtar sözcük sağlar.

C++' in bildirimleri için sabit ifadeler (bir sabiti değerlendiren ifadeler) gerektirir:

- Dizi sınırları

- Case deyimlerine yönelik seçiciler

- Bit alanı uzunluk belirtimi

- Sabit Listesi başlatıcıları

Sabit deyimlerde geçerli olan tek işlenenler şunlardır:

- Sabit değerler

- Sabit Listesi sabitleri

- Sabit ifadelerle başlatılan const olarak belirtilen değerler

- **sizeof** ifadeleri

İntegral olmayan sabitlerin sabit bir ifadede yasal olması için integral türlerine dönüştürülmesi gerekir (açıkça veya örtük olarak). Bu nedenle, aşağıdaki kod geçerlidir:

```cpp
const double Size = 11.0;
char chArray[(int)Size];
```

Tamsayı türlerine açık dönüştürmeler sabit ifadelerde geçerlidir; Tüm diğer türler ve türetilmiş türler, bir **sizeof** işleci için işlenen olarak kullanılması dışında geçersizdir.

Virgül işleci ve atama işleçleri sabit ifadelerde kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[İfade Türleri](../cpp/types-of-expressions.md)
